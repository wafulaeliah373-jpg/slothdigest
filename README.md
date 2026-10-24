# SlothDigest 🦥

Rest. We’ll catch you up. SlothDigest turns a pasted group chat into a short morning brief with decisions, action items, and open questions. It runs Gemma 3 locally through Ollama, so your messages stay on your machine.

## Run it

1. Install Python 3.10 or newer and [Ollama](https://ollama.com/download).
2. Download Gemma 3 4B:

       ollama pull gemma3:4b

   The model download is about 3.4 GB. Change the model field to any model installed in Ollama.
3. Start the app:

       python server.py

4. Open http://127.0.0.1:8000, paste a chat, and make your morning brief.

No Python packages or cloud API keys are required. After the model download, inference can run offline. OLLAMA_URL and PORT can be set as environment variables if needed.

## Why open-source AI?

Group chats can hold plans, personal details, and unfinished decisions. Running Gemma locally keeps the conversation on the user's device, works offline after the model download, avoids a paid API, and lets people switch to another Ollama model that fits their hardware. The open model is what makes this private, low-cost catch-up possible.

## Current limits

- Paste a text export manually; there is no chat-platform integration.
- Chat length is limited to 60,000 characters in this first version.
- The model can miss or misclassify tasks. Each extracted item shows source text to review, and a local rule flags uncited first-person offers such as “I can bring…”; check important decisions and tasks against the original conversation.

## Hacktoberfest

Built for the DEV Hacktoberfest Open-Source AI Challenge: Week 3, “Slow and Steady.” A submission needs a DEV post using the challenge submission template and the #devchallenge and #hf26challenge tags. See the [challenge page](https://dev.to/challenges/hacktoberfest-week3-2026-10-19) for current rules and deadline.


