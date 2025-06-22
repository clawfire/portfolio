---
layout: post
title: Automate Netlify Rebuilds Using GitHub Actions
description: How to automatically rebuild your Netlify site only when future-dated content needs to be published, while keeping your build minutes under control.
date: 2025-06-22T16:21:34.776Z
featured_image: img/2025/06/Build Digital Image.jpg
published: true
tags:
  - Netlify
  - GitHub Actions
  - Automation
  - Static Site Generators
categories: []
fmContentType: Blog Post
lastmod: 2025-06-22T18:01:38.523Z
---
Static site generators like Jekyll or Eleventy support scheduling content via the `date:` field in the YAML frontmatter. But these future-dated posts won’t appear on your site unless it’s rebuilt — and Netlify only rebuilds when a new commit is pushed.

This can be a problem when you're scheduling posts for the future: unless something triggers a new build on the right day, those posts won't go live.

## Why an automated (but smart) rebuild?

Rebuilding the site every day is one option, but that can quickly consume your **300 monthly build minutes** on Netlify's free tier. If a rebuild takes ~4 minutes, a daily schedule eats up 40% of your budget.

The smarter approach? **Only rebuild when a post is actually due.**

## 🧠 The smarter strategy: conditional scheduling

Here’s how the workflow works:

1. On each commit that modifies a Markdown file, GitHub Actions checks if a future `date:` is present in the file (even if it's in full ISO 8601 format).
2. If it finds one, the next scheduled date is extracted and saved into a `next-build.txt` file.
3. Instead of committing this file (which would trigger a Netlify rebuild), it’s stored as a **GitHub artifact**.
4. A lightweight scheduled workflow runs daily, downloads the artifact, and checks whether today matches the date.
5. If it matches, it triggers a Netlify build via webhook.

### 🔧 Netlify: Setup a build webhook

1. Go to your Netlify site dashboard.
2. Navigate to **Site settings > Build & deploy > Build hooks**.
3. Click **Add build hook**, give it a name (e.g. “Scheduled rebuild”), and choose your deploy branch (e.g. `main`).
4. Copy the webhook URL and save it as a GitHub secret named `NETLIFY_BUILD_HOOK`.

---

## Workflow 1: Detect future dates (on push)

```yaml
name: Prepare next Netlify build date

on:
  push:
    paths:
      - "_posts/**.md"

jobs:
  extract-next-build-date:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Extract future post date
        run: |
          TODAY=$(date '+%Y-%m-%d')
          FUTURE_DATES=()
          for FILE in $(git diff --name-only HEAD^ HEAD | grep '\.md$'); do
            [ -f "$FILE" ] || continue
            POST_DATE=$(grep '^date:' "$FILE" | head -n1 | sed -E 's/date: *"?([0-9]{4}-[0-9]{2}-[0-9]{2}).*/\1/')
            if [[ "$POST_DATE" > "$TODAY" ]]; then
              FUTURE_DATES+=("$POST_DATE")
            fi
          done

          if [ ${#FUTURE_DATES[@]} -gt 0 ]; then
            NEXT_DATE=$(printf "%s\n" "${FUTURE_DATES[@]}" | sort | head -n1)
            echo "$NEXT_DATE" > next-build.txt
          else
            echo "none" > next-build.txt
          fi

      - name: Upload next build date
        uses: actions/upload-artifact@v4
        with:
          name: next-build
          path: next-build.txt
````

## Workflow 2: Daily check and trigger

```yaml
name: Trigger Netlify build if today matches

on:
  schedule:
    - cron: '5 0 * * *'
  workflow_dispatch:

jobs:
  check-and-trigger:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Download next build date
        uses: actions/download-artifact@v4
        with:
          name: next-build
          path: .

      - name: Trigger build if date matches
        run: |
          if [ ! -f next-build.txt ]; then
            echo "No next-build.txt found"
            exit 0
          fi

          NEXT=$(cat next-build.txt)
          TODAY=$(date '+%Y-%m-%d')

          if [ "$NEXT" == "none" ]; then
            echo "No build scheduled."
            exit 0
          fi

          if [ "$NEXT" == "$TODAY" ]; then
            echo "✅ Triggering Netlify build for today."
            curl -X POST -d '{}' "${{ secrets.NETLIFY_BUILD_HOOK }}"
          else
            echo "⏳ Not today. Next scheduled build is $NEXT."
```

## 🧾 Final result

This setup ensures your Netlify site only rebuilds when a scheduled post becomes due. It:

* ⚡ Avoids unnecessary builds or dummy commits
* 🧠 Respects Netlify’s build time budget
* 🧼 Keeps your repo clean and logic isolated

---
💡 This can be extended to multi-site, multi-branch setups, or even date queues using more advanced scheduling logic. But for a simple editorial workflow, it’s more than enough.

Photo by [Tai Bui](https://unsplash.com/fr/@agforl24?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/fr/photos/un-ecran-dordinateur-pose-sur-un-bureau-IMYU7kmPLwI?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)
