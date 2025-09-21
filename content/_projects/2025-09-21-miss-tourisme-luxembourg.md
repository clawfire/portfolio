---
title: Miss Tourisme Luxembourg
subtitle: Securing a public voting system in 48 hours with real-time, trustworthy results
date: 2019-06-18
skills:
  - Vibecoding
techs:
  - Supabase
  - Lovable
  - Postmark
industry:
  - Event
description: "For the Miss Tourisme Luxembourg election, I designed and delivered a robust, secure, real-time online voting system in just two days. By migrating from a low-code base (Glide) to a custom Lovable + Supabase + Postmark stack, we eliminated manual post-processing (disposable emails, alias abuse), locked down API access, and achieved immediately usable results. Outcome: a smooth public experience, vote integrity, and a calm organization team on event night."
featured_image: /img/2025/09/Miss_Tourisme_Candidates_Admin.jpeg
accent_color: ""
gallery_images:
  - /img/2025/09/Miss_Tourisme_Main_Screen.jpeg
  - /img/2025/09/Miss_Tourisme_Detail_View.jpeg
  - /img/2025/09/Miss_Tourisme_Admin.jpeg
  - /img/2025/09/Miss_Tourisme_Candidates_Admin.jpeg
  - /img/2025/09/Miss_Tourisme_User_management.jpeg
fmContentType: Projet
lastmod: 2025-09-21T13:04:25.736Z
---
Yesterday was the Miss Tourisme Luxembourg election. Like previous years, I handled the online voting system — but this time I rebuilt it from the ground up. I moved away from a low‑code base (Glide) to a custom build on Lovable + Supabase + Postmark, “vibe‑coded” in two days. The goal wasn’t just to ship fast; it was to make the vote trustworthy, observable, and immediately usable on stage without any manual cleanup.
Why change what “worked”? Because what “works” for a prototype can break under real‑world behavior. Over the years, we’ve had to scrub votes after the fact: disposable emails, “+alias” tricks, and creative ways to poke at Glide’s API, which is surprisingly permissive by default. This time, we put integrity in the spec from day one and moved the critical logic server‑side.

## TL;DR

* Rebuilt the voting system in 48 hours
* Stack: Lovable (Tailwind) + Supabase (Postgres, RLS, Edge Functions) + Postmark (magic link)
* Cut “soft fraud” at the source (disposable domains, aliasing, dot‑variants)
* Locked down API access and enforced rules server‑side
* Real‑time, trustworthy results with zero post‑processing

## The stack that enabled speed without shortcuts

**Lovable + Tailwind for the frontend**
Clean design system, fast componentization, easy to ship something that looks and feels solid.
**Supabase for data and server logic**
Postgres with Row‑Level Security, plus Edge Functions to keep sensitive logic off the client.
**Postmark for transactional email at scale**
Reliable magic link authentication, no passwords to manage, less friction, fewer attack vectors.

### Passwordless by design

No reset flows. No password storage. Fewer ways for bad actors to get creative. Users enter an email, receive a magic link, and they’re in. It’s simpler for everyone and removes a whole category of risk.

## Cutting out “soft fraud” at the source

The devil is in the details: disposable domains, aliasing with “+”, and dot‑variants (hello Gmail) can quietly skew results unless you deal with them upfront. This year, I:

* Normalized emails
* Filtered disposable domains
* Blocked alias abuse
* Validated before any vote hits the database

No “we’ll clean it later.” If data is clean at the door, you don’t have to run a laundromat backstage.

## Locking down the API (because anyone could hit it)

One lesson learned with Glide: their API can be hit by, well, anyone who knows where to look. That’s fine for prototypes, less fine for a public vote. I added strict API caller control and moved the vote path entirely into Supabase Edge Functions. The client never writes a vote directly; the server enforces rules: voting window, user state, uniqueness, and rate limits. Row‑Level Security does the rest to ensure users only see what they should.

## What this looked like operationally

**Real‑time results without the ritual post‑mortem**
No last‑minute scrubbing, no “give us 20 minutes to adjust.” The numbers were clean by design and ready as soon as voting closed.
**A lightweight back office with the essentials**
Validation vs. rejection rates, error signals, latency. Enough observability to trust what we’re seeing, not a bloated dashboard.
**An experience that felt simple**
One‑click login, clear UI, quick feedback. Security shouldn’t feel like paperwork to the user.

## Why two days were enough

The constraints were clear, the scope was tight, and the tools did their job. Edge Functions let me encapsulate the sensitive bits fast. Tailwind and a small pattern library made the UI straightforward. Postmark delivered reliably. Supabase gave me RLS, SQL views, and a sane place to aggregate results without inventing a custom backend on deadline.

## Would I use Glide again?

Absolutely — for the right thing. Glide is great for prototypes and internal tools. But when integrity is the product, you need control: caller restrictions, server‑side rules, and a data model that can enforce reality. For public voting with real outcomes, low‑code becomes a liability faster than you think.

## What I’d would add next (for next year maybe)

* Smarter anti‑bot checks (lightweight proof‑of‑work, device attestation, or Turnstile)
* Anomaly alerts on voting patterns (bursts, geographic clustering, device reuse)
* A/B tests on the auth flow to shave a few seconds off the experience. Probably trying social login. But then, how to guarantee uniqueness?

## The takeaway
Under tight deadlines, vibe‑coding gave me speed without sacrificing ownership. Here’s why it beat low‑code for this project:

* Control and portability: the code is mine. I can deploy it anywhere, evolve it, and audit every layer (auth, API, data). No dependency on a platform’s roadmap, pricing changes, or opaque limits.
* No throwaway work: nothing here gets trashed in six months. Every component (Tailwind UI, Supabase schemas/RLS, Edge Functions, Postmark flows) is durable and reusable.
* Faster for the hard parts: when you need strict API caller control, server‑side rules, and clean data by design, bending a low‑code tool costs time. A lean custom stack let me implement exactly what was required—once—without wrestling the platform.

Low‑code still has a place for less technical folks, but for people with a bit of development background, vibe‑coding is a powerful way to ship fast without cutting corners on integrity, control, or future‑proofing.
