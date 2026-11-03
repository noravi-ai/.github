# Noravi

**One mind, many bodies.** A personal AI operating system: a single-user assistant that lives on its own
cloud server, remembers context across every channel, works through 116 tools, speaks English, Urdu and
Punjabi, and controls a Windows laptop by voice.

Noravi (no-RAH-vee) was called Atlas until November 2026. It is designed, built and run daily by
[Fahad Bilal Saleem](https://fahadbilal.com).

**→ The full write-up, architecture and demo video: [fahadbilal.com/work/noravi](https://fahadbilal.com/work/noravi/)**

---

### What it does

- **Talks wherever its owner is.** Telegram (text and voice notes), a private web dashboard with a live voice
  tab, and a desktop companion on the laptop, all sharing one conversation and one memory.
- **Acts, not just answers.** 116 tools across 15 Model Context Protocol servers: email, calendar, Google
  Sheets and Docs, notes, web research, a job-search tracker, finance, a code sandbox and its own database.
- **Controls the laptop by voice.** Up to three actions planned in one model call and carried out in order;
  dangerous ones wait for a physical key press on the laptop itself.
- **Keeps its own books.** Every API call is recorded with its cost; past a weekly limit, paid calls move to a
  free model and the reply says so.

### How it is engineered

- **Safety as engineering, not prompting.** Each laptop action's tier is fixed in the laptop's code, never by a
  model. Only the laptop's own voice can command it: chat and the dashboard cannot. Devices reach the server
  over a private network only, each with its own revocable token.
- **Private by design.** Laptop output never reaches a model; what is said about it is made by plain code, as
  counts, never file or folder names. No outside AI service collects which apps are used, or the files and
  folders on the machine.
- **Measured, not assumed.** The laptop's action model won a head-to-head on 36 synthetic requests run five
  times each; prompt changes are re-measured before they ship, and "obvious" speed-ups that didn't pay were
  rejected on the numbers.
- **Honest about itself.** About 1,430 automated tests across four repositories. Every known defect carries a
  command that shows whether it is still live, and nothing is marked fixed until it is seen working in production.
- **AI-assisted, human-governed.** Claude Code audits, designs, builds and re-verifies; every commit, restart
  and defect close is a human decision.

### Stack

Node.js · Python · FastAPI · PostgreSQL + pgvector · Docker · Electron · Model Context Protocol · DeepSeek ·
Claude · Groq · Ollama · Deepgram · Prometheus · Grafana · Vitest · a private mesh VPN · Cloudflare

---

The repositories are private because Noravi runs real email, calendar, files and a real laptop.
Happy to walk through the code in an interview: [get in touch](https://fahadbilal.com/#contact).
