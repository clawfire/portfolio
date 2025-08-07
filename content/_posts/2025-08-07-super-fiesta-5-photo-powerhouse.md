---
layout: post
title: "Super Fiesta: $5 Photo Powerhouse"
description: |
  How I turned a quick script inspired by @roast.london.roast into a photo Swiss‑army knife — for the price of a latte!
date: 2025-08-07T13:11:33.443Z
featured_image: img/2025/08/image12.png
published: true
tags: []
categories: []
fmContentType: Blog Post
lastmod: 2025-08-07T14:05:21.677Z
---
> **TL;DR** : With just **US $5** worth of Claude Code prompts I rewrote the README, patched obvious security holes, and added watermarking + bulk‑renaming to my open‑source photo batcher [Super Fiesta](https://github.com/clawfire/super-fiesta/). Now it replaces both Photoshop macros and my beloved Squash GUI.

## The original pain point

Except when I'm working with [the great Pit Reding](https://studiopitreding.com), every party left me with hundreds of pictures that were too heavy, not square, unbranded, and badly named. I spent more time juggling Photoshop actions and Squash than enjoying the memories. My tiny Python script—hacked together in an afternoon and inspired by [@roast.london.roast](https://www.instagram.com/roast.london.roast/?hl=fr)'s clean aesthetic—only did a basic resize and … that was it.


## What Super Fiesta does today

* **Resizes** to a neat 1080‑px square, centers the photo, fills the background.
* **Batches** an entire folder (optional macOS tag filter).
* **Adjustable** JPEG quality.
* **PNG** watermark (size, position, opacity, margins).
* **Smart** renaming — original, sequential, or Event‑Date with conflict detection.
* **Persistent** config in sf_config.ini.
* **Chattier** CLI with input validation.

## Why I brought Claude Code on board

I’m not a full‑time Python dev; I wanted to move fast, stay clean, and learn along the way. Claude Code bills per token, so with a handful of focused prompts I:

* **Rewrote the README** to be genuinely onboarding‑friendly.
* **Hardened the script** (error handling, RGB/quality checks, context managers).
* **Implemented watermarking** end‑to‑end.
* **Added pattern‑based renaming** with a preview step.

Total chat: ~5 800 tokens  ⇒ ~ US $5.

## Two signature upgrades at a glance

| Feature | Before | After Claude Code |
| ------- | ------ | ------------------ |
| Watermark | 🛑 *None – I relied on Squash* | ✅ **PNG overlay** – six preset positions, 1‑50 % size, 10‑100 % opacity (default: bottom‑center at 14 %) |
| Renaming | 🔢 Batch renamming from MacOS | 🚀 **Automatic**: Original / Sequential (`Party_001`) / Event‑based (`Birthday_2025‑08‑07_001`) with preview + conflict detection |

## What working with an AI felt like

* **Iterative prompting** – start with context → ask for a plan → zoom into code.
* **Git co‑authoring** – each commit is clearly co‑signed, perfect for traceability.
* **Security awareness** – Claude flagged unvalidated inputs and potential batch crashes and proposed tested fixes.
* **Cost efficiency** – pay‑as‑you‑go beats a monthly subscription for small OSS bursts.

## Wrap‑up & call‑to‑action
If you want to …

* **Automate your photo pipeline** without a heavyweight GUI,
* **Super‑charge a side‑project** on a shoestring budget,
* **Learn by reading AI‑assisted code**, 

clone [the repo](https://github.com/clawfire/super-fiesta/), run `pip install -r requirements.txt` and `python sf.py`. Your shots will be Instagram‑ready in seconds!

> 💡 **Next step**: a tiny Tkinter GUI and Windows support. Feel free to open an issue or send a PR.

Happy fiestas – and keep those cameras clicking! 📸🥳
