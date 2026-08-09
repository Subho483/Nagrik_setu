# 🏛️ Nagrik Setu (CivicTwin AI)

> **Benefits Found. Voices Heard. Problems Solved.**
> 
> 🌐 **Live Demo:** [https://nagrik-setu-ruddy.vercel.app](https://nagrik-setu-ruddy.vercel.app)

**Nagrik Setu** is an intelligent, high-fidelity civic-technology platform designed for **IEM HACKS 4.0 (Problem Statement 05)**. It serves as a digital bridge between citizens and administrative bodies, addressing two core civic challenges:
1. Discovering unclaimed government welfare benefits through an AI-powered eligibility gap detector.
2. Transforming disjointed civic complaints into transparent, community-verified action.

---

## 🎯 1. Problem Statement

Citizens frequently struggle to access government support because they lack awareness of existing welfare schemes, their qualification status, or the required documentation. 

Concurrently, reporting local municipal problems (such as broken streetlights, water pipeline leakages, and waste accumulation) is highly fragmented. This leads to:
- Duplicate complaints and ticket spam.
- Lack of accountability from municipal bodies.
- Tickets being marked as "resolved" without actual citizen verification.

---

## ✨ 2. Signature Innovations

- 🤖 **AI Benefit Gap Detector:** Builds a lightweight, private citizen profile and dynamically matches schemes. It estimates annual payouts (e.g., ₹36,000/year), generates document checklists, and assesses application readiness.
- 🗺️ **Civic Cluster Intelligence:** Automatically merges duplicate, nearby complaints (within a ~220m radius) of the same category into single, high-priority "Civic Clusters" on maps. This avoids ticket spam and highlights issues with widespread community impact.
- ✅ **Citizen-Verified Resolution:** Restricts administrative case closure. A complaint marked as resolved by the authority remains open until citizens physically check the site and confirm ("Yes, it is fixed"). If the citizen selects "No", the ticket reopens, escalates to higher vigilance officers, and sets SLA timers.
- 📊 **Explainable Civic Health Score:** Computes Ward scores (0-100) based on unresolved complaint volume, SLA response delays, citizen confirmation rates, and recurring issue occurrences, detailing the math transparently to the public.

---

## 💻 3. Tech Stack

- **Framework:** Next.js (App Router, Server Actions compatible)
- **Language:** TypeScript (Strict Typings)
- **Styling:** Tailwind CSS (Premium warm tones and accessible font hierarchies)
- **Maps:** Leaflet & OpenStreetMap (GeoJSON circle overlaps and HTML markers)
- **Charts:** Recharts (Dynamic Bar and Pie charts)
- **Icons:** Lucide React
- **Animations:** Framer Motion / Tailwind Micro-transitions
- **Accessibility:** WCAG 2.1 AA principles (Text scaling, high contrast toggle, screen reader read-aloud simulation)

---

## 📁 4. Project Structure

```text
NAGRIK SETU/
├── src/
│   ├── app/
│   │   ├── about/            # About IEM Hacks 4.0 metadata
│   │   ├── benefits/
│   │   │   ├── check/        # Onboarding multi-step wizard form
│   │   │   └── results/      # Matches and gaps breakdown
│   │   ├── civic-health/     # Ward metrics & Recharts graphs
│   │   ├── community/        # Public-safe updates stream
│   │   ├── grievances/[id]/  # Workflow timeline & verification logs
│   │   ├── map/              # Map screen with details side panels
│   │   ├── privacy/          # PII minimization declarations
│   │   ├── report/           # 60s reporting form with AI preview
│   │   ├── globals.css       # Tailwind 4 & Leaflet CSS overrides
│   │   ├── layout.tsx        # Wraps AppProvider, Navbar & Footer
│   │   └── page.tsx          # Premium landing page layout
│   ├── components/
│   │   ├── AccessibilityMenu.tsx  # High contrast & text scales
│   │   ├── CivicMap.tsx           # Dynamic client-only Leaflet map
│   │   ├── CivicSaathiAI.tsx      # Pre-scripted chatbot assistant
│   │   ├── DemoTour.tsx           # Floating walkthrough guide
│   │   ├── Footer.tsx
│   │   ├── Navbar.tsx             # Sticky header with role switchers
│   │   └── VoiceInput.tsx         # Microphone speech simulator
│   ├── context/
│   │   └── AppContext.tsx    # State management database
│   ├── services/
│   │   ├── schemeService.ts       # Welfare calculations
│   │   ├── grievanceService.ts    # Clustering & SLA timers
│   │   └── civicHealthService.ts  # Ward scoring matrices
│   └── types/
│       └── index.ts          # Core TypeScript models
├── package.json
└── tsconfig.json
```

---

## 🎭 5. Preloaded Demo Credentials & States

The application features a complete **Demo Mode (`DEMO_MODE=true`)** which runs locally without requiring live API keys. 

- **Demo Citizen Profile:** 
  - **Name:** Amit Das (Location: Kolkata, West Bengal)
  - **Details:** 42 years old, Farmer, Kutcha housing, annual income < ₹1.5 Lakhs.
- **Seed Complaints:** ~30 grievances seeded around the Kolkata center.
  - *Streetlight Failure Cluster (Ward 12):* 15 complaints, 220m radius.
  - *Garbage Accumulation (Ward 10):* 8 complaints, 120m radius.
  - *Water Pipeline Leakage (Ward 8):* 7 complaints, 180m radius.

---

## 🚀 6. Local Installation & Development

Follow these commands to deploy the project locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/Subho483/nagrik_setu.git
   ```
2. Navigate to the project directory:
   ```bash
   cd nagrik_setu
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Start the local development server:
   ```bash
   npm run dev
   ```
5. Open your browser and navigate to `http://localhost:3000`.

---

## 🧭 7. How to run the Judge Demo Tour

When you load the landing page, a floating black button appears in the bottom right corner: **"Start Judge Demo Tour"**. Clicking it launches a guided 5-step walkthrough:

1. **Step 1:** Leads to the **Welfare Wizard** -> click the **Autofill Amit Das** button to prepopulate details in one click or click the **Microphone** to dictate.
2. **Step 2:** Leads to the **Eligibility Snapshot** -> shows an estimated value of ₹36,000/year and explains why Amit qualifies.
3. **Step 3:** Redirects to the **Civic Map** -> shows Ward Health Score zones and lets you click the Streetlight Cluster.
4. **Step 4:** Redirects to **Grievance ID CT-KOL-2026-1042** -> logs the complete timeline (Reported -> Work Started -> Marked Resolved).
5. **Step 5:** Renders the verification action card -> click **"No, problem still exists"** to trigger dispute, automatic escalation to vigilance deputy, and reopening timelines. Toggle **"Yes, it is resolved"** to verify closing.

> 💡 **Tip:** To inspect administrative actions, toggle the role selector in the navbar from **Citizen** to **Officer** to access the live administrative priority queue.
