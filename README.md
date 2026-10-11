# portfolio
Here is a bunch of projects that I have done in my free time (the portfolio included)

## Projects

### [A.R.T.H.U.R.](https://github.com/thecozycod3r/arthur) — a JARVIS-style personal assistant for macOS

[![Arthur dashboard](https://raw.githubusercontent.com/thecozycod3r/arthur/main/docs/dashboard.png)](https://github.com/thecozycod3r/arthur)

Every morning and evening Arthur scans Gmail, Calendar, Slack, WhatsApp, iMessage and the weather, works out what
actually matters, and briefs me out loud. Any time, I can say **"Hey Arthur…"**, hold a key, or type, and he answers
questions or acts — replies on WhatsApp/Slack/email/iMessage, books and moves meetings, sets reminders and timers,
calls people, plays music, remembers things, and runs Claude Code agents — always reading back and waiting for my
"yes" before anything leaves the Mac.

**What makes it interesting**
- **On-device speech stack** — Vosk wake word (silence-gated, sleeps after 10 idle minutes), Whisper large-v3-turbo on
  the Apple GPU, Silero VAD, Kokoro neural voice with a JARVIS "in-suit" effect, answers streamed sentence by sentence.
- **Voiceprint-gated approvals** — a speaker-embedding fingerprint means only my voice can wake it *or* approve a send.
- **WhatsApp sending without an API** — drives the desktop app through macOS Accessibility, presses Send only if the
  box holds exactly the approved text, then verifies delivery in WhatsApp's own database.
- **Real conversations** — follow-ups without the wake word, pronoun resolution ("reply to them"), ignores TV chatter.
- **Security-first local API** — localhost-only, DNS-rebinding and CSRF protection, token auth, no actions while the
  Mac is locked, never deletes anything, prompt-injection resistant.
- **Tested** — 180+ automated checks across 12 suites (brain, skills, security, resilience, conversation, UI incl. XSS
  payloads, wake-word accuracy on 10 voices, typed commands), all passing.

`Python` `FastAPI` `Whisper (MLX)` `Vosk` `sherpa-onnx` `Kokoro` `PyObjC` `Claude Code` `Playwright`
