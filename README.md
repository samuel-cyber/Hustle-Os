# Hustle OS

**Team Members**
[Ojo Samuel Oluwasemilore] | [Aweda Farouk] | [Faisal Lukmon-Olajide Olamide]

---

## 🚀 Live Demo

- **Live Application:**  https://hustle-os-1-vrsq.onrender.com
- **Backend API:** https://hustle-os-p6jt.onrender.com
- **Recorded Demo:** [Link to your Loom video]

---

## 🎯 The Problem

**How might we seamlessly capture alternative financial data to bank and underwrite Nigeria's 40 million informal micro-businesses, without disrupting their daily operations?**

Over 90% of Nigerian SMEs operate informally, missing out on credit because they rely on paper notebooks. Traditional bookkeeping apps fail because a market vendor cannot pause serving 50+ customers a day to type into complex web forms.

Hustle OS solves this adoption barrier by eliminating manual data entry. We turn casual WhatsApp chats into a structured, bank-ready credit pipeline.

---

## ✨ Our Solution & Core Features

- **Zero-Friction WhatsApp Ingestion** — Vendors log transactions in natural Nigerian Pidgin via WhatsApp (e.g., *"I sell 2 bags of garri for 30000"*). The system parses the text, updates the database, and texts back a receipt in under 2 seconds.
- **The Wema "Business Passport"** — A deterministic API built specifically for Wema Bank's ALAT lending engine. It transforms raw daily trades into a structured credit payload, automatically generating a Risk Tier (A–D) and a recommended Naira credit limit.
- **"Ask Your Hustle" AI Chat** — An AI copilot powered by Claude 3.5 Haiku that reads real database metrics and narrates personalized financial insights in warm Nigerian Pidgin.
- **"Type or Talk" Web Input** — A native Web Speech API integration allowing users to dictate sales directly into the web dashboard for instant form pre-filling.
- **Fintech-Grade UI** — A sleek, ALAT-inspired interface featuring staggered Framer Motion animations and skeleton loaders, delivering a premium seed-stage startup experience.

---

## 🛠️ Tech Stack

**Frontend:** React, Vite, Tailwind CSS, Framer Motion, Lucide Icons, Web Speech API

**Backend:** FastAPI (Python) on Render, python-multipart, Twilio SDK, secure HMAC-SHA256 webhook signature verification

**Database & AI:** PostgreSQL via Supabase (featuring multi-tenant UUID mapping and indexed phone lookups), Anthropic Claude 3.5 Haiku

---

## ⚙️ How to Set Up Locally

1. **Clone the repository**
   ```bash
   git clone [your-repo-link]
   cd [project-directory]
   ```

2. **Run the Database Migration**
   In your Supabase SQL Editor, execute:
   ```sql
   ALTER TABLE businesses ADD COLUMN phone_number VARCHAR;
   CREATE UNIQUE INDEX ix_businesses_phone_number ON businesses (phone_number);
   ```

3. **Start the Backend**
   ```bash
   cd backend
   python -m venv venv
   source venv/bin/activate   # Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```
   Create a `.env` file containing your credentials:
   ```
   DATABASE_URL=
   ANTHROPIC_API_KEY=
   TWILIO_AUTH_TOKEN=
   DEMO_BUSINESS_ID=
   ```
   Then launch it:
   ```bash
   uvicorn app.main:app --reload
   ```

4. **Start the Frontend**
   ```bash
   cd src
   npm install
   npm run dev
   ```