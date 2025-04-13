---
layout: post
title: Automating Context Reminders Before Meetings (When You're Managing 15 Projects with an ADHD Brain)
description: |
  How to automate meeting context reminders to stay focused and efficient, even with a packed schedule.
date: 2025-04-13T13:39:07.758Z
featured_image: img/2025/04/calendar.png
published: true
tags:
  - productivity
  - ADHD
  - n8n workflow
  - neurodivergence
categories: []
fmContentType: Blog Post
---

As a neurodivergent person with an **ADHD profile**, one of my biggest challenges at work isn't skill or motivation — it's **managing attention and cognitive load**.

Each week, I juggle **over fifteen different projects**, spread across multiple clients and agencies. Even when I’ve prepared my meetings in advance, I often find myself wondering at the last minute:
> “What was that meeting about again? Did I forget something critical? Was I supposed to bring something?”

This need for **last-minute contextual reassurance** is common among people with ADHD: even when everything is in place, the brain seeks to reassemble key details just before an interaction to feel secure. When repeated 5 to 10 times a day, this becomes a serious productivity drain.

👉 If you’re interested in broader strategies for managing meetings with ADHD, I also wrote about that here: [Mindful meeting management: planning meetings with ADHD](https://thibaultmilan.com/blog/2024/11/21/mindful-meeting-management-planning-meeting-with-adhd/)

## 🤖 Automating Away the Friction

Rather than creating more reminders or to-dos for myself, I built a small **automated workflow using n8n**.
It helps **relieve the mental load** of having to chase context manually.

## 🎯 The Goal

> Automatically send a short message to the organizer of meetings **without a description**, **where I’m just a participant**, the **day before** the meeting.

## ⚙️ How It Works

Here’s how the **n8n workflow** is structured:

1. **Trigger every morning at 7:30am**
   → To scan for the next day’s meetings.

2. **Read my Google Calendar**
   → Retrieve all events between tomorrow 00:00 and 23:59.

3. **Smart Filtering**
   → Keep only meetings:
   - where I’m **not the organizer**,
   - that are **non-recurring** (to avoid weekly check-ins),
   - that have **no description** (since the description usually provides enough context).

4. **Send an automatic email to the organizer**
   → Politely asking for a bit of context if it hasn’t been shared yet.

5. **Send a Telegram notification to myself**
   → So I know the message went out.

## 📧 Sample Email Sent

Here's the automated message my colleagues receive:

```html
Hi there 👋🏻<br><br>
🤖 I'm Thibault’s friendly email bot, reaching out to gather a bit of context about our upcoming meeting — it seems there’s no description provided.<br><br>
If the title is self-explanatory, feel free to ignore this message. But if it’s just a project or client name, a short overview would be super helpful 🙏<br><br>
Thibault is currently juggling meetings across ~15 different clients for various agencies, so a quick reminder of what this one’s about would make his prep much smoother ✨<br><br>
Thanks a lot in advance!<br><br>
– Thibault’s email automation bot 🤖
```

## 🎁 Benefits

- ✅ Less mental overhead
- ✅ Lower risk of forgetting something important
- ✅ No more procrastination about reaching out
- ✅ Better mental readiness for meetings

## 💡 What About You?

If you’re neurodivergent — or simply juggling too much context — this kind of automation can **make a real difference in your daily comfort**.
I’d be happy to share the full n8n workflow or help you adapt it to your stack (Slack, Outlook, Notion, etc.). Feel free to reach out!
