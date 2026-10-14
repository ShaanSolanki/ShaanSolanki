# Shaan Solanki

Final-year B.E. Information Technology student in Amravati, India. I ship production software for paying clients rather than coursework.

Currently at **Synckraft Technologies**, building and maintaining five live client systems end to end: React and Next.js front ends, Python and Node REST services, PostgreSQL and Firestore behind them. Most of my work is the integration layer, and most of what I learn comes from what breaks after release.

Most of this is in private client repos, so the commit counts are there to say what share was actually mine.

### What I work with

**Languages** Python · TypeScript · JavaScript · SQL
**Frontend** React · Next.js (App Router) · Tailwind · TanStack Query
**Backend** FastAPI · Pydantic · SQLAlchemy · Node.js · Express
**Data** PostgreSQL · SQLite · MongoDB · Firestore · Redis
**Testing** pytest · Hypothesis · Vitest · fast-check · mypy strict · Ruff
**Infra** Docker · GitHub Actions · Linux

### Things I have built

**Pragati Bakery** — warehouse and outlet system for a bakery chain, one warehouse and ten outlets on a single deployment. The client's problem was staff overcharging at the counter, so the whole system is built around one rule: the warehouse sets prices and an outlet has no write permission on the price column in Postgres. Hiding the field in the UI would not have been enough. Billing also has to survive the internet dropping, so the POS is an Android app over Capacitor, billing into on-device SQLite and syncing through an outbox. *112 of 357 commits mine, across the POS app, the API and the database.*

**Ordrji Desktop** — Windows point of sale that runs a restaurant's entire billing counter with the internet unplugged, prints on thermal hardware and serves the shop's tablets and kitchen screen over local WiFi. I built billing, discounts behind a manager PIN, hold and resume, refund notes, and a table board with locking and shift, merge and split. Also the fault-injection harness that kills the server mid-bill and asserts what survived. *95 of 192 commits mine.*

**Carbon-Aware Compute Scheduler** — LightGBM forecasts grid carbon 48 hours ahead and an OR-Tools CP-SAT solver picks the cleanest slot inside each job's deadline: 7.88% lower emissions and zero deadline violations over an 840-job week. The part I would defend in review is that the deadline guard never consults the model, so feeding a deliberately inverted forecast drives the saving to -15.3% and still produces zero violations. 21,900 lines under Ruff and mypy strict, 58 pytest modules.

**PaySheet** — payroll and income-tax suite running on 6,700+ real payslips. Parses government portal HTML into a structured schema, then flags duplicate records and net-pay mismatches before anything is disbursed. Started as a PySide6 desktop tool and grew into a multi-user FastAPI app with a TDS engine.

**[Voicera](https://github.com/ShaanSolanki/Voicera)** — an inbound voice agent on LiveKit, so a WebRTC audio path, with Sarvam for speech-to-text and text-to-speech and an LLM deciding the reply, grounded in the business's own records. Built for callers who switch between Hindi, Marathi and English inside one sentence, which generic models transcribe into nonsense.

**[CivicFlow](https://github.com/ShaanSolanki/CIVICFLOW)** — MERN civic grievance platform. Express and Mongoose with JWT and role-based access, two React front ends (a citizen reporting app with a Leaflet map picker, and a staff console with analytics and a density heat map), and a Python service that classifies and prioritises complaints.

### Open source

**[bolna-ai/bolna#1130](https://github.com/bolna-ai/bolna/pull/1130)** — a multilingual voice agent went mute for the rest of a call whenever its TTS websocket closed and reconnected, because the synthesizer pool read the socket only once. Fixed the forwarder to re-enter, with a cap so a dead provider cannot spin it, plus four regression tests.

### Reach me

[shaansolanki.dev](https://shaansolanki.dev) · [LinkedIn](https://www.linkedin.com/in/shaansolanki) · shaansolanki17@gmail.com
