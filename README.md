# LISA — Personal AI Assistant

A mobile-first installable web app starter, using the dark navy / violet visual direction from your reference screenshot.

## What's included
- Chat screen with message history saved locally in the browser
- Voice input where the browser supports speech recognition
- Read-aloud responses using browser speech synthesis
- Chat, Voice, History, and Settings tabs
- PWA manifest and service worker for installation/offline app shell
- Small Node.js backend that keeps the AI provider API key on the server

## Requirements
- Node.js 20+
- An AI provider endpoint compatible with the OpenAI Chat Completions API
- An API key from a provider whose terms permit your intended use

## Run locally
1. Extract this ZIP.
2. Open a terminal in the extracted `lisa-ai-app` folder.
3. Copy `.env.example` to `.env` and fill in the provider settings.
4. Run `npm install`
5. Run `npm start`
6. Open `http://localhost:3000`

For phone testing, deploy the app over HTTPS or use a secure local development tunnel. PWA installation generally requires HTTPS (localhost is allowed for development).

## Configure the AI provider
Set these values in `.env`:
- `AI_BASE_URL`: provider API base URL, e.g. `https://api.openai.com/v1`
- `AI_MODEL`: model identifier supported by your provider
- `AI_API_KEY`: private API key (never put this in `public/` or browser JavaScript)

The server calls `${AI_BASE_URL}/chat/completions`. Providers differ, so check your provider's current API documentation. Do not commit `.env` to GitHub.

## Important limitations
This is a working app foundation, not a finished production service. AI replies require valid provider credentials and network access. Browser voice recognition availability varies by browser/device and may send audio to the browser's speech service. Local chat history stays in that browser on that device; it is not cloud-synced. There is no account system or cross-device memory yet.

Before public launch, add authentication, rate limiting, abuse protection, secure database storage, privacy disclosures, deletion/export controls, monitoring, and a reviewed safety policy. Follow applicable laws and the AI provider's terms. No app can promise unrestricted or unlimited AI use.

## Project layout
- `public/` — app interface, styles, icons, PWA files
- `server/` — backend API
- `server.js` — starts the server
