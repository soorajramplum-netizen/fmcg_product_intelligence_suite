# FMCG Product Intelligence Suite [tested on Snacks]

Product intelligence tool for South Indian snacks & sweets innovation.

## What it does (Segment 1)

Enter any product name and get:

1. **South or Not** — Is it South Indian? Product-led or Flavor-led?
2. **SI Proxy** — If it's not South Indian, what's the closest South Indian equivalent?
3. **State & Story** — Which state it belongs to, cultural significance, and marketing storytelling
4. **Positioning** — Brand Ladder range fit + Functional / Emotional Benefits and RTBs
5. **Functional Callouts** — Packaging-ready claims (protein, fiber, no palm oil, etc.)
6. **Ingredients** — Full breakdown with proportions, role, and functional highlights (or AI-generated)
7. **Product Descriptors** — 3 behavioral science-informed product descriptions
8. **Competition** — Top 5 competition products with pricing and positioning

---

## Setup

### 1. Clone and install

```bash
git clone <your-repo>
cd south-indian-or-not
npm install
```

### 2. Set up your API key

Copy `.env.example` to `.env.local`:

```bash
cp .env.example .env.local
```

Edit `.env.local` and add your Anthropic API key:

```
ANTHROPIC_API_KEY=sk-ant-...
```

Get your key from: https://console.anthropic.com

### 3. Run locally

```bash
npm run dev
```

Open http://localhost:3000

---

## Deploy to Vercel

### Option A: Via Vercel CLI

```bash
npm i -g vercel
vercel
```

Follow the prompts. When asked about environment variables, add `ANTHROPIC_API_KEY`.

### Option B: Via GitHub + Vercel Dashboard

1. Push this repo to GitHub
2. Go to https://vercel.com → New Project → Import your repo
3. In **Environment Variables**, add:
   - Key: `ANTHROPIC_API_KEY`
   - Value: `sk-ant-...`
4. Click Deploy

---

## Changing the AI model

The model is set in `pages/api/analyze.js`:

```js
model: 'claude-sonnet-4-6',
```

Options:
- `claude-sonnet-4-6` — default (fast, high quality)
- `claude-opus-4-6` — best quality, slower and more expensive
- `claude-haiku-4-5-20251001` — fastest, cheapest

---

## Coming next

- **Segment 2: Explore** — Browse 200+ South Indian products by state, season, category
- **Segment 3: Advisor** — AI chatbot for product launch, positioning, functional, storytelling
- **Segment 4: Flavor Library** — Massive flavor repository with filters

---

## Notes

- Competition pricing data is approximate and AI-generated — always verify before strategic use
- The tool is optimized for a particular brand context and the four ranges of the Brand Offerings Ladder
