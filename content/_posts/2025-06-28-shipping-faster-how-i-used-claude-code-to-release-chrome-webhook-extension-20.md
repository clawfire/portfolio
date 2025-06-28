---
layout: post
title: "Shipping Fast(er): How I Used Claude Code to Release Chrome Webhook Extension 2.0"
description: ""
date: 2025-06-28T14:01:12.710Z
featured_image: /img/2025/06/Caption 01.png
published: true
tags:
  - AI-assisted-development
  - chrome-extension
  - Claude Code
  - developer tools
  - productivity
  - side projects
  - webhooks
  - MCP-protocol
categories:
  - Development
fmContentType: Blog Post
lastmod: 2025-06-28T14:20:37.784Z
---
## A Tale of Side Projects and Speed

There’s a unique satisfaction in shipping something you built for yourself. That feeling gets even better when you manage to revive a side project after a long pause—and ship not just a fix, but a full version bump.

This post is about [Chrome Webhook Extension](https://github.com/clawfire/chrome-webhook-extension), a small tool I first wrote to make it easier to send browser data to a webhook (like a Discord channel, a Notion automation, or anything you can connect). It sat untouched for a while—until I decided to pick it up again with the help of Claude Code, an AI-powered coding agent. The result? A productive two-day burst that gave life to version 1.2 and then, less than 24 hours later, version 2.0.

Here’s what changed, and how AI helped me build faster.

## What’s New in v2.0

If you were using the extension before, you might not notice radical UI changes—but under the hood, v2.0 introduces a more robust foundation and thoughtful improvements to workflows. Here’s a quick breakdown:

- **Webhook test mode**: You can now test your webhook without sending real data. Super handy for debugging.
- **Improved error handling**: Webhook requests now catch and display error messages more transparently.
- **Cleaner UI alignment**: Better alignment and spacing across popup views.
- **Code refactoring**: The codebase is cleaner and easier to maintain, especially around popup logic and validation.
- **Safer UX**: Edge cases are now handled more gracefully when URLs or payloads are missing.

You can find the full release notes for [v2.0 here](https://github.com/clawfire/chrome-webhook-extension/releases/tag/v2.0.0), and [v1.2 here](https://github.com/clawfire/chrome-webhook-extension/releases/tag/v1.2).

{% include post-components/gallery.html
	columns = 2
	images = "/img/2025/06/Screenshot-2025-06-28-15.31.00.png,/img/2025/06/Caption%2002.png"
%}

## Working With Claude Code: The Real Productivity Boost

Both the 1.2 and 2.0 versions were built using **Claude Code**, a development assistant built on top of Anthropic’s Claude 3.5 family. I primarily used **Claude 3.5 Haiku**, with some calls handled by **Sonnet** and **Opus**, depending on the complexity of the task. But most of the time, I didn’t have to choose—Claude Code’s agent handled that.

Here’s a fun stat:

- **v1.2** took me **1h15** to build — and cost me **\$3.02** of tokens
- **v2.0** took me **1h40** — and cost me **\$4.63** of tokens

That’s under 3 hours total for two solid updates to a production-ready extension, at a price point that’s cheaper than a decent lunch. What’s more interesting is *how much* Claude Code actually handled:

- Debugging issues I had previously written (but not committed yet)
- Suggesting clearer code structures overall
- Reworking event listener placement and associated logic
- Managing edge use cases and improving input sanitisation
- Handling a complete UX refactoring, moving from basic to polished while keeping PureCSS
- Helping draft the release notes and Chrome Web Store description
- Writing the GitHub logic to treat issues as a lightweight support ticketing system

In short: it felt like having a reliable mid-level dev on my team—one that needed some oversight, but consistently offered solid structure, relevant suggestions, and kept things moving forward. Definitely not junior-level like what IDE autocomplete or tools like Lovable tend to provide.

## Making Side Projects Realistic Again

Before this update, this extension had been sitting mostly untouched. Like many devs, I have a backlog of ideas or half-finished tools that I *want* to complete but can’t justify sinking hours into after work. But pairing with Claude Code made the time investment feel much more feasible:

- The feedback loop is *fast*. Ask, try, tweak, ship.
- It doesn't get stuck or tired—or need you to write full spec docs.
- It helps re-enter old codebases by explaining and cleaning up context.
- It can even execute bash instructions, with per-command approval or predefined permission scopes. I let it handle `git commit`, `push`, and `pull`, but kept `tag` and `rebase` under manual control.
- This means it doesn’t just write code—it can ship the whole cycle if you let it.

What would have taken a full weekend of grumbling and Googling ended up being an evening project with real output.

## What’s Next?

I’m planning a few more internal improvements, and maybe support for templating common payloads. But what really excites me is diving deeper into what Claude Code can do. I haven’t even tried connecting it to tools via the MCP protocol yet—imagine it working on my database, managing Netlify functions, or integrating directly with other cloud-native services.

There’s a lot more I want to explore, and I’ll definitely share if it turns into something interesting.

If you try it and have feedback, [open an issue](https://github.com/clawfire/chrome-webhook-extension/issues) or ping me.

## Final Thoughts

If you’re juggling a busy schedule and a drawer full of side projects, consider giving Claude Code or a similar AI dev tool a try. It won’t *replace* your judgement, but it will absolutely make it easier to get over the hump and just ship.

🔗 [Chrome Webhook Extension on Chrome Web Store](https://chromewebstore.google.com/detail/webhook-manager/bgmeeebkokmefcfafnhfjgbemifefbno)
🔗 [Chrome Webhook Extension on GitHub](https://github.com/clawfire/chrome-webhook-extension)
📦 [Download v2.0](https://github.com/clawfire/chrome-webhook-extension/releases/tag/v2.0.0)
