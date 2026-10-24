---
title: "I made my group chats wait for me with local AI"
published: false
tags: devchallenge, hf26challenge
---

*This is a submission for the [Hacktoberfest Open-Source AI Challenge Week 3: Slow and Steady](https://dev.to/challenges/hacktoberfest-week3-2026-10-19).*

## What I Built

SlothDigest turns a pasted group chat into a calm morning brief: a short recap, decisions, action items with owners and dates when stated, and questions that still need an answer. Each extracted decision, task, and question carries a source line so people can verify it.

It is for anyone who opens a busy chat and ends up scrolling through dozens of messages just to find the plan. Paste a text export, choose a local model, and get the catch-up in one click. The app does not connect to your chat account or archive messages.

## Demo

[Add a short screen recording or hosted demo link here after we run the app.]

To try it locally, follow the setup in the project README. The sample garden-planning chat is included for a quick walkthrough.

## Code

[Add the public GitHub repository link here after publishing the new repo.]

## How I Built It

SlothDigest is a small Python standard-library web server with a plain HTML, CSS, and JavaScript interface. It sends the text to a local Ollama server, which runs Gemma 3 and returns structured JSON for the recap, decisions, tasks, and open questions.

To run it, install Ollama and Python 3.10 or newer, download the model with ollama pull gemma3:4b, start the app with python server.py, and open http://127.0.0.1:8000. Once the model is downloaded, inference can run offline.

## Why Does Open Innovation Matter?

Group chats can hold personal details and unfinished plans. The default setup keeps inference local: the app forwards the text to Ollama on the same device, where Gemma 3 runs. There is no per-message API bill, and people can switch to another Ollama model that fits their hardware.

This makes the trade-off clear: a little setup and local compute in exchange for keeping the conversation on your own machine.

## The Lazy Payoff

The workflow is one paste and one click instead of rereading the chat. I have not measured the time saved yet. In an end-to-end sample run, Gemma 3 4B missed two offers to bring supplies. I kept each extracted item tied to a source line and added a local rule that surfaces uncited first-person offers, so obvious omissions are easier to spot. This prototype still needs more evaluation before I would rely on it for task tracking.

## Prize Categories

- Best Use of Gemma

---

The first version takes pasted text instead of connecting to a messaging platform. It is a starting point for a useful local-first catch-up tool; summaries can still miss context, so check important tasks against the original messages.



