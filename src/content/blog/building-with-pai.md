---
title: 'I Built a Personal AI Infrastructure — Here is What I Learned'
description: 'How I set up Daniel Miessler''s PAI framework and used it to ship a blog in one session.'
pubDate: 'Apr 02 2026'
---

I've been working in IT for a while, and like most people in tech, I've been watching the AI space closely. I've used ChatGPT, played with different models, read plenty of takes on where things are headed. But I kept feeling like I was on the outside looking in — consuming AI instead of building with it.

So I decided to change that.

## Finding PAI

A few weeks ago I came across [Daniel Miessler's](https://danielmiessler.com/) PAI framework — short for Personal AI Infrastructure. Daniel built and open-sourced the whole system. It's not a chatbot or a wrapper around an API. It's a structured framework that turns Claude into a working partner: it has memory that persists between sessions, a library of skills it can invoke, a structured algorithm for working through complex tasks, and it learns how you like to work over time.

I didn't build PAI. Daniel did, and he deserves the credit. What I did was set it up, learn how it works, and start using it to ship real things.

## Setting It Up

I'm running PAI through Claude Code on WSL (Windows Subsystem for Linux). The setup involved getting the framework installed, configuring the memory system, and getting comfortable with how it thinks through problems.

The thing that struck me immediately is how different this feels from a normal chat with an AI. PAI doesn't just answer questions — it breaks work into phases, creates verifiable criteria for what "done" looks like, selects the right tools for the job, and checks its own work. It's closer to pair programming with a very fast colleague than it is to Googling things.

## What I Shipped in One Session

Here's the part that convinced me this was worth writing about.

In a single conversation, PAI and I:

- **Scaffolded a full blog** using Astro, a modern static site generator, with Tailwind CSS for styling
- **Set up the toolchain** — it discovered my Node.js version was too old, installed a version manager, upgraded to Node 22, and installed the GitHub CLI, all without me having to look up how to do any of it on Linux
- **Configured deployment** — Cloudflare Pages adapter, wrangler config, the whole pipeline
- **Created a GitHub repo**, committed the code, and pushed it — including wiring up credential helpers when the first push failed
- **Connected it to my domain** — markburke.io, registered on Cloudflare, auto-deploys from the main branch
- **Ran a code review** — it launched three parallel review agents that checked for reuse opportunities, code quality issues, and efficiency problems, then fixed what they found
- **Wrote the README** with a complete workflow for creating new posts

The blog you're reading this on right now is the result. It has dark mode, RSS, a sitemap, SEO metadata, and a clean minimal design. And I didn't write a single line of the Astro config, CSS, or deployment pipeline by hand.

## What Surprised Me

**The back-and-forth is real.** PAI asked me questions when it needed decisions — what domain, where to put the project, what my about page should say. It didn't just guess. When it hit a problem (Node too old, git push failing), it diagnosed the issue and fixed it without me having to step in.

**Memory changes everything.** PAI remembers who I am, what I'm working on, and decisions we've made in past sessions. I don't start from zero every time. It knows my GitHub username, my project structure, my preferences. This is fundamentally different from a stateless chat.

**It does the boring parts fast.** The amount of time I would have spent looking up Astro docs, figuring out the Cloudflare adapter config, debugging the git credential helper on WSL, setting up Tailwind 4's new Vite plugin — PAI just handled all of it. I got to focus on what I actually cared about: what the blog says and how it looks.

**It checks its own work.** After building everything, it ran a structured verification against every requirement it had set at the start. Then it ran the code review on top of that. I've worked with people who are less thorough.

## What's Next

I'm planning to move PAI off WSL and onto a dedicated Linux box. The framework will transfer over — it's really just a directory of config files and a few tool installations. After that, more writing, more building, and going deeper with AI tooling.

If you're in tech and you've been meaning to get hands-on with AI beyond just chatting with it, I'd recommend looking into what Daniel Miessler has built. PAI turned "I should learn more about AI" into a deployed blog in an afternoon.
