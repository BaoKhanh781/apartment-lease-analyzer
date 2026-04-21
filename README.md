# FairLease 🏠
### AI-Powered Apartment Lease Analyzer

> **Know what you're signing before you sign it.**

FairLease is a single-page web app that helps first-time renters — especially college students and older adults with limited legal knowledge — understand their apartment lease agreements using AI.

---

## The Problem

Every year, millions of renters sign leases they don't fully understand. Hidden auto-renewal clauses, buried early termination fees, and unclear guest policies cost tenants thousands of dollars. Legal language is designed to be unreadable — FairLease fixes that.

---

## What It Does

- **📄 Upload your lease PDF** — drag and drop or click to browse
- **🤖 AI analysis** — Claude reads the entire document and flags important clauses
- **🚨 Red flag detection** — automatically categorizes clauses as High Risk, Watch Out, or Tenant-Friendly
- **💬 Plain English explanations** — every clause explained like a text from a helpful friend, not a lawyer
- **👤 Personal impact** — tells you exactly what each clause means *for you* with real dollar amounts
- **📊 "How common is this?"** — shows what percentage of leases typically include each clause
- **💡 Negotiation tips** — actionable advice on what to push back on
- **🗨️ AI Chat agent** — ask any question about your lease and get an instant answer based on your actual document

---

## How to Use

### Option 1 — Run Locally
1. Download `fairlease_final2.html`
2. Open it in a text editor
3. Go to **line 535** and replace `YOUR_KEY_HERE` with your [Anthropic API key](https://console.anthropic.com)
4. Open the file in **Chrome**
5. Upload a lease PDF and get your analysis

### Option 2 — GitHub Pages (Live URL)
```bash
git init
git add fairlease_final2.html README.md
git commit -m "Add FairLease app"
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git branch -M main
git push -u origin main
```
Then go to **Settings → Pages → Deploy from main branch** in your GitHub repo.

Your live URL: `https://YOUR_USERNAME.github.io/YOUR_REPO/fairlease_final2.html`

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML, CSS, Vanilla JavaScript |
| AI Model | Claude Sonnet (Anthropic API) |
| PDF Processing | Base64 encoding via FileReader API |
| Hosting | GitHub Pages (static) |
| Dependencies | None — single HTML file, no frameworks |

---

## API

This app uses the [Anthropic Messages API](https://docs.anthropic.com/en/api/messages) with the `claude-sonnet-4-5` model.

The lease PDF is sent as a base64-encoded document block. Claude returns a structured JSON analysis including:
- Document metadata (title, lease dates)
- Overall verdict (fair / mixed / risky)
- Clause-by-clause breakdown with severity, plain-English explanation, normalcy score, and negotiation tips

**Estimated cost:** ~$0.02 per lease analysis · ~$0.001 per chat message

---

## Target Users

- 🎓 **College students** signing their first apartment lease
- 👴 **Older adults** with limited legal or tech experience
- 🌍 **International students** unfamiliar with US rental laws

---

## Project Structure

```
fairlease_final2.html   ← entire app (single file)
README.md               ← this file
tricky_lease.pdf        ← sample risky lease for demo
good_lease.pdf          ← sample fair lease for demo
```

---

## Demo

Upload either of the included sample leases to see FairLease in action:
- **`tricky_lease.pdf`** — a landlord-unfriendly lease with 8 hidden red flags
- **`good_lease.pdf`** — a fair, tenant-friendly lease for comparison

---

## Hackathon Rubric

| Criterion | How FairLease addresses it |
|-----------|---------------------------|
| **Prompt Engineering** | Structured JSON schema prompt with 15+ product terms, explicit output format, severity classifications, and 6th-grade reading level instruction |
| **Innovation** | Specialized lease reader with red-flag detection, normalcy scoring, and negotiation tips — not a generic chatbot |
| **Impact** | Addresses a real pain point for millions of first-time renters; every design choice reduces legal confusion |
| **Presentation** | Live PDF upload demo, visible clause highlighting, floating chat agent, clean modal UI |

---

## Built With

Built at a 5-hour hackathon using Claude AI as both the development assistant and the runtime intelligence powering the app.

---

*FairLease — Built for renters, not landlords.*
