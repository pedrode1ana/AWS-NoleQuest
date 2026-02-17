# 🎯 NoleQuest
### *Your Experience. Your Future. Your Way.*

> **AI-powered internship marketplace that translates real-world student experience into career opportunities.**  
> Built at the **AWS Design Sprint** · Florida State University · February 2026 · 🏆 Team 6

---

## 🔗 Quick Links

| Resource | Link |
|----------|------|
| 🎨 **Live Figma Prototype** | [View Interactive Prototype](#) ← https://www.figma.com/make/W9UaBEEPUgosjxxDgGgBnG/NoleQuest?t=imVw2fUUNgk7J3Rl-1 |


---

## 💡 The Problem

Every year, thousands of talented university students get **auto-rejected** by Applicant Tracking Systems (ATS) — not because they lack skills, but because their resumes don't contain the right corporate keywords.

A student who managed a 10-person team at Starbucks has **operational management** skills.  
A Finance Club treasurer who balanced a $15K budget has **financial planning** capabilities.  
ATS systems never see it. Recruiters never get the chance.

**Meanwhile**, recruiters are drowning in hundreds of keyword-matched resumes, unable to identify the high-potential candidates buried in the noise.

---

## ✨ The Solution

**NoleQuest** is a two-sided AI marketplace — built entirely on AWS — that bridges this gap:

### For Students 🎓
- **AI Skill Translation** — Upload your resume and transcript. Amazon Bedrock reads your real experience and maps it to corporate language recruiters understand
- **Smart Match Scoring** — See every internship ranked by actual skill fit, not keyword overlap
- **One-Click Resume Optimization** — AI rewrites your bullet points using professional framing. You review and approve every change. No fabrication, ever.
- **Alumni Networking** — Automatically finds FSU alumni at your target company and drafts a personalized connection message for you to send

### For Recruiters 🏢
- **High-Signal Dashboard** — Candidates ranked by fit score, not application date
- **"Why They Fit" Cards** — AI-generated plain-language explanations of why each candidate is a strong match despite unconventional backgrounds
- **Blind Screening by Default** — Demographics hidden until a recruiter signals interest, reducing unconscious bias
- **Reverse Recruiting Alerts** — Get notified the moment a high-potential student matching your criteria joins the platform

---

## 🖥️ Prototype Screens

> This repository contains the full Figma prototype built during the AWS Design Sprint. Below is an overview of every screen designed.

### Student Platform
| Screen | Description |
|--------|-------------|
| 🏠 Landing Page | Hero, features, student testimonial (Maya Chen), CTA |
| 📝 Onboarding (3 screens) | Sign up → Resume upload → AI analysis results |
| 🧭 Dashboard | NoleNetwork-inspired card layout with 6 action tiles |
| 🔍 Job Search | Listings ranked by match %, filter sidebar, skill indicators |
| ✨ AI Career Guide | Suggested career paths based on transferable skills |
| 📋 Job Detail View | Match score, gap analysis, company intel, sticky action panel |
| 🔄 Resume Optimizer | Before/after comparison, transparent AI explanations |
| 📬 Application + Network | Submission confirmation, alumni list, AI-drafted messages |
| 📊 Applications Tracker | Status dashboard, stats, success rate vs. industry average |

### Recruiter Platform
| Screen | Description |
|--------|-------------|
| 🥇 High-Signal Dashboard | Leaderboard view, fit scores, "Why They Fit" cards |
| 👤 Candidate Detail | Full profile, skill translation reasoning, blind mode |
| 🔔 Reverse Recruiting Alert | Real-time notification for new high-potential matches |
| 📝 Job Posting | Create/manage listings with AI-suggested matching criteria |

---

## 🏗️ Architecture

NoleQuest is designed to be **fully serverless on AWS**, built for cost-efficiency and scale from day one.

```
┌─────────────────────────────────────────────────────────┐
│                    FRONTEND                             │
│  React.js → Amazon S3 + CloudFront CDN                 │
│  Real-time updates via AWS AppSync (GraphQL)           │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│                    BACKEND                              │
│  AWS Lambda (serverless compute)                        │
│  Amazon API Gateway (REST endpoints)                    │
│  Amazon DynamoDB (user profiles, jobs, applications)   │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│                   AI / ML LAYER                         │
│  🤖 Amazon Bedrock / Claude Sonnet                      │
│     → Skill translation, resume optimization,           │
│       career recommendations, recruiter summaries       │
│  📄 Amazon Textract                                     │
│     → Resume & transcript parsing                       │
│  🎯 Amazon Personalize                                  │
│     → Match scoring & candidate ranking                 │
│  💬 Amazon Comprehend                                   │
│     → Sentiment analysis for company reviews           │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│              SECURITY & INTEGRATIONS                    │
│  Amazon Cognito · AWS KMS · AWS WAF                     │
│  Amazon SES (email) · Google Custom Search API          │
│  FERPA-compliant · SOC 2 Type II                        │
└─────────────────────────────────────────────────────────┘
```

---

## 🎨 Design System

| Element | Value |
|---------|-------|
| **Primary Color** | Garnet `#782F40` (FSU heritage) |
| **AI Accent Color** | Calm Blue `#6B9BD1` (soothing, trustworthy) |
| **Background** | Warm Cream `#F5F1ED` (student-friendly) |
| **Gold Accent** | `#CEB888` (FSU tradition) |
| **Font** | Inter — Medium weight for soft, approachable feel |
| **Design Philosophy** | Calm & supportive — reduces job search anxiety |
| **Inspiration** | FSU NoleNetwork — clean, minimal, card-based layout |

---

## 🧠 Built Using Amazon's Working Backwards Methodology

This project was designed using Amazon's **Working Backwards** framework — starting with the customer and working back to the solution, not the other way around.

**The 5 key questions we answered first:**
1. 👤 **Who is the customer?** — FSU students with non-traditional backgrounds (retail, clubs, volunteer work)
2. 🔴 **What is the problem?** — Real skills are invisible to ATS keyword filters, causing talented students to be auto-rejected
3. 💡 **What is the solution?** — AI that translates real experience into corporate language and surfaces hidden potential
4. 📰 **How do we describe it?** — We wrote a full Press Release + FAQ *before* designing a single screen
5. ✅ **How do we measure success?** — 15% application-to-interview rate vs. the 2–3% industry average

> *"The Working Backwards process is not designed to be easy; it's designed to save huge amounts of work on the backend, and to make sure we're actually building the right thing."*  
> — Jeff Bezos

---

## 📁 Repository Structure

```
NoleQuest/
│
├── 📁 docs/
│   ├── NoleQuest_PRFAQ.pdf          # Full Press Release + FAQ document
│   └── NoleQuest_Figma_Prompt.md    # Complete design brief used to build prototype
│
├── 📁 designs/
│   ├── exports/                     # Exported PNG screens from Figma
│   │   ├── student/                 # All student platform screens
│   │   └── recruiter/              # All recruiter platform screens
│   └── assets/                      # Icons, logos, brand assets
│
├── 📁 architecture/
│   └── aws_architecture.png         # System architecture diagram
│
└── README.md                        # You are here
```

---

## 🚀 How to View the Prototype

**Option 1 — Figma (Recommended)**
1. Click the [Live Figma Prototype](#) link above
2. Press the **▶ Play** button in the top right to enter presentation mode
3. Click through the interactive flows

**Option 2 — Static Screenshots**
Browse the `/designs/exports/` folder for PNG exports of every screen, organized by platform (student / recruiter).

---

## 📊 Key Metrics & Goals

| Metric | Target | Industry Average |
|--------|--------|-----------------|
| Application-to-Interview Rate | **15%** | 2–3% |
| Time to First Interview | **< 14 days** | 45–60 days |
| Recruiter Review Time (per batch) | **< 10 min** | 45 min |
| Non-Traditional Background Hires | **+40%** | baseline |
| AI Resume Processing | **< 5 sec** | N/A |
| Platform Uptime | **99.9%** | N/A |

---

## 👥 Team

**NoleQuest — Team 6**  
Built at the AWS Design Sprint · Florida State University · February 2026

> *"Talent is everywhere. Opportunity isn't. NoleQuest is the bridge."*

---

## 📜 License

This project was created for the **AWS Design Sprint at FSU (February 2026)** as an academic prototype. All rights reserved by the NoleQuest Team. The prototype and documentation are shared for portfolio and educational purposes.

---

<div align="center">

**Built with ❤️ at FSU · Powered by AWS · Designed for every student whose experience counts**

`#GoNoles` · `#NoleQuest` · `#AWS` · `#AmazonBedrock` · `#WorkingBackwards`

</div>
