---
title: "I made my group chats wait for me with local AI"
published: false
tags: devchallenge, hf26challenge
---

*This is a submission for the [Hacktoberfest Open-Source AI Challenge Week 3: Slow and Steady](https://dev.to/challenges/hacktoberfest-week3-2026-10-19).* 

## What I Built

SlothDigest turns a pasted group chat into a short morning brief: a recap, decisions, action items with owners and dates when they are stated, and questions that still need an answer. It keeps each extracted item tied to its source text, so you can check the model's reading against the original chat.

The goal is to replace a slow scroll through yesterday's messages with one paste and one click. SlothDigest never connects to a messaging account or stores a chat archive.

## Demo

**Run it locally:** clone the repository below, follow the Quick Start in its README, click **Try a sample**, then **Make my morning brief**. The first run downloads Gemma 3 4B (about 3.4 GB). This prototype runs inference on your own computer; there is no shared hosted demo because private chats should not need to leave your device.

## Code

[SlothDigest on GitHub](https://github.com/wafulaeliah373-jpg/slothdigest)

## How I Built It

SlothDigest uses Python's standard library for a small local web server and a plain HTML, CSS, and JavaScript interface. The server sends the pasted chat to Ollama on the same machine. Gemma 3 returns structured data for the recap, decisions, tasks, and open questions. Once the model is downloaded, inference can work offline. You can switch to another model already installed in Ollama.

## Why Does Open Innovation Matter?

Group chats can contain personal details, plans, and unfinished decisions. Running an open-weight model locally means a user can keep that context on their own machine, inspect the code, work offline after setup, and change models to fit their hardware. No per-message cloud API bill or external chat integration is required.

That choice has a real cost: the first model download is large, and local inference uses the computer's own resources. For a private catch-up tool, I think that trade-off is useful.

## The Lazy Payoff

The intended payoff is a quick scan instead of rereading the thread. I have not measured time saved, and I would not trust this prototype with important tasks without checking its evidence. In a sample garden-planning chat, Gemma 3 4B missed two offers to bring supplies. SlothDigest shows source text for extracted items and adds a local rule to flag uncited first-person offers such as “I can bring…” so a possible omission is easier to spot.

## Prize Categories

- Best Use of Gemma

The first version accepts a pasted text export and has a 60,000-character limit. It is a small local-first start; check important tasks against the original conversation.
