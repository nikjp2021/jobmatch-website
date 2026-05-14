# PRD: JobMatch — Student Part-Time Job Platform

> **Document Version:** 5.0 (Phase 2 — Platform Donation & Gratitude System)
> **Last Updated:** 2026-05-15
> **Author:** Opencode Workspace
> **Status:** Functional HTML/CSS/JS Prototype — Phase 2 Documented, Donation/Gratitude System Designed, Extended Application Pipeline, Legal Compliance Framing
> **Legend:** ✅ DONE | 🟡 Partial | ❌ PENDING | 📐 DESIGNED

---

## Table of Contents

1. [Executive Brief](#1-executive-brief)
2. [PHASE 1: Core Platform](#2-phase-1-core-platform)
   - [A. Functional & Concept](#a-functional--concept)
   - [B. Logic & Design](#b-logic--design)
   - [C. Mockups & Wireframes](#c-mockups--wireframes)
   - [D. Technicals](#d-technicals)
3. [PHASE 2: Donation & Gratitude System](#3-phase-2-donation--gratitude-system)
   - [A. Functional & Concept](#a-functional--concept-1)
   - [B. Logic & Design](#b-logic--design-1)
   - [C. Mockups & Wireframes](#c-mockups--wireframes-1)
   - [D. Technicals](#d-technicals-1)
4. [Appendix: Implementation Audit](#4-appendix-implementation-audit)

---

## 1. Executive Brief

### Vision

A centralized, mobile-first platform connecting university students with local businesses for part-time employment. JobMatch eliminates door-to-door job searching by providing a single digital marketplace where businesses can post opportunities and students can discover, apply for, and manage roles — all filtered by skills, schedule availability, proximity, and compensation.

### Problem

- **Students** waste 5–10 hours/week physically visiting shops asking about openings — with no guarantee of available positions
- **Local businesses** lack an efficient channel to reach university talent pools, relying on handwritten signs or word-of-mouth
- **No platform** focuses specifically on the intersection of university proximity, part-time flexibility, and student-friendly scheduling

### Value Proposition

| Stakeholder | Value |
|---|---|
| **Students** | Discover all campus-area part-time jobs in one place; apply in minutes; track applications; build work history and reviews |
| **Businesses** | Reach motivated student workers instantly; manage hiring pipeline digitally; scale posting volume based on business needs |

### Current Status

- **Phase 1 (Core Platform):** Fully functional HTML/CSS/JS prototype — 4 roles, bilingual EN/JA, weighted matching, messaging, reviews, guided demo, 13 routes, 10 mock users, 9 sample jobs, 7 seeded applications. **78 features implemented.**
- **Phase 2 (Donation & Gratitude):** Fully designed and documented. **0 features implemented** — ready for development.
- **Total features tracked:** 148 (78 DONE, 2 PARTIAL, 58 PENDING, 10 DESIGNED)

---

## 2. PHASE 1: Core Platform

---

### A. Functional & Concept

#### A1. Problem Statement & Market Opportunity

> "I spent my entire Saturday walking around downtown visiting 12 shops asking if they were hiring. I got one callback." — Typical student experience

**Quantified pain:**
- Average student spends **3–5 hours/week** searching for part-time work
- **68%** of student workers find jobs through word-of-mouth or walking in
- Small business owners report spending **4+ hours/week** on hiring when using general platforms

**Market opportunity:**
| Factor | Insight |
|---|---|
| **Market Size** | ~20M college students; ~70% seek part-time work |
| **Local Focus Gap** | Indeed, LinkedIn focus on enterprise; gig platforms (Fiverr, Upwork) focus on freelancers — none specialize in local student part-time |
| **Seasonal Demand** | Back-to-school, holiday retail, summer surges create predictable hiring spikes near campuses |
| **Demographic Fit** | Gen Z expects mobile-first, chat-based, review-driven UX |
| **Network Effects** | Each new business attracts students; each new student makes the platform more valuable to businesses |

#### A2. User Research & Personas

**Student Persona: "Budget-Conscious Brenda"**
```
Name:       Brenda Chen
Age:        20
Year:       Junior, Marketing (BBA)
University: City University, Downtown Campus
Income:     $0 from part-time (seeking $15–20/hr)
Available:  Tues/Thurs 2–6pm, All day Saturday
Skills:     Social Media, Canva, Excel, Copywriting, Bilingual (English/Spanish)

Goals:
  - Earn $800–$1,200/month to cover rent
  - Flexible hours that don't conflict with classes
  - Gain marketing experience for her resume

Frustrations:
  - Generic job boards return full-time or remote-only roles
  - No way to filter by "student-friendly schedules"
  - Previous applications disappeared into a "black hole"

Tech Habits:
  - Mobile-first (checks phone 96x/day)
  - Prefers chat over email/phone
  - Trusts peer reviews and star ratings heavily
```

**Business Persona: "Overwhelmed Owner Oleg"**
```
Name:       Oleg Petrov
Age:        38
Business:   FreshSlice Pizza (1 location near campus)
Employees:  3 full-time, needs 2–3 part-timers
Revenue:    $450K/year (peaks during academic year)

Pain Point: Can never find reliable student workers on short notice
            for lunch rushes and weekend shifts

What He Wants:
  - Post a job in under 5 minutes
  - See only students near his location
  - Filter by availability and relevant skills
  - Chat immediately with applicants to assess fit
  - Track hiring pipeline without spreadsheets

Budget:     Willing to pay $30–50/month for a reliable hiring tool
```

**Secondary Persona: "Side-Hustle Sam" (Graduate Student)**
```
Name:       Sam Nguyen
Age:        26
Program:    MS Computer Science (2nd year)
Income:     Teaching assistantship ($1,200/month)
Goal:       Earn extra $500–$800/month doing freelance Dev work
Skills:     JavaScript, React, Python, Git, AWS basics
Prefers:    Project-based or contract work over traditional part-time
```

#### A3. User Roles & Feature Matrix

| Feature | Student | Business | Admin (Future) |
|---|---|---|---|
| Register / Login | ✅ | ✅ | ❌ |
| Profile management | ✅ | ✅ | — |
| Browse job feed | ✅ | — | ❌ |
| Search & filter jobs | ✅ | — | ❌ |
| Apply to jobs | ✅ | — | — |
| Skill‑based job recommendations | ✅ | — | — |
| Application tracking | ✅ | — | — |
| Post new job | — | ✅ | — |
| View applicants per job | — | ✅ | ✅ |
| Approve / reject applicant | — | ✅ | ✅ |
| Messaging | ✅ | ✅ | — |
| Write reviews | ✅ | ✅ | — |
| View reviews | ✅ | ✅ | — |
| Manage subscriptions | — | ✅ (self-serve) | ✅ |

#### A4. Feature Inventory — Phase 1

**Authentication & Accounts**
| # | Feature | Status | Notes |
|---|---|---|---|
| 1 | Student registration | ✅ DONE | Name, email, password, skills, location, bio |
| 2 | Business registration | ✅ DONE | Business name, description, location, email |
| 3 | Role toggle (tabs) | ✅ DONE | "I'm a Student" / "I'm a Business" |
| 4 | Duplicate email check | ✅ DONE | Validates before creating account |
| 5 | Login form | ✅ DONE | Email + password |
| 6 | Demo credentials shown | ✅ DONE | On login page |
| 7 | Session persistence | ✅ DONE | localStorage |
| 8 | Logout | ✅ DONE | Clears session, redirects to home |
| 9 | Password hashing | ❌ PENDING | Plain text in localStorage |
| 10 | Email verification | ❌ PENDING | No backend email infrastructure |
| 11 | Forgot password flow | ❌ PENDING | Not implemented |
| 12 | Social login (OAuth) | ❌ PENDING | Google, maybe Apple |
| 13 | Account deletion | ❌ PENDING | No self-service delete |
| 14 | Rate limiting on auth | ❌ PENDING | No brute force protection |
| 15 | CAPTCHA | ❌ PENDING | Not needed for MVP, needed at scale |
| 16 | Password strength meter | 🟡 PARTIAL | Only `minlength="4"` |

**Job Management**
| # | Feature | Status | Notes |
|---|---|---|---|
| 17 | Post job form | ✅ DONE | Title, category, description, location, pay, hours, skills |
| 18 | Browse job cards | ✅ DONE | With match % for students |
| 19 | Job detail view | ✅ DONE | Full info + apply button |
| 20 | Keyword search | ✅ DONE | Live filter on title/description/location/category |
| 21 | Category filter | ✅ DONE | 6 visible categories in dropdown |
| 22 | Sort jobs | ✅ DONE | Newest, pay high→low, pay low→high |
| 23 | Match % badge | ✅ DONE | On cards and detail view |
| 24 | "Other" category in filter | 🟡 PARTIAL | Exists in post form but missing from browse filter |
| 25 | Job editing | ❌ PENDING | No edit UI for business |
| 26 | Job deletion | ❌ PENDING | No delete option |
| 27 | Mark job as filled | ❌ PENDING | Status exists but no UI toggle |
| 28 | Job expiration | ❌ PENDING | No `expiresAt` field or auto-expiry |
| 29 | Save/bookmark jobs | ❌ PENDING | Heart/bookmark icon needed |
| 30 | Applied badge on browse | 🟡 PARTIAL | Shows on matching page but not browse jobs |

**Applications**
| # | Feature | Status | Notes |
|---|---|---|---|
| 31 | Apply with cover letter | ✅ DONE | Modal form |
| 32 | Student application list | ✅ DONE | With status badges, dates, view job link |
| 33 | Business application list | ✅ DONE | Grouped by job, with applicant info |
| 34 | Accept application | ✅ DONE | Status → accepted |
| 35 | Reject application | ✅ DONE | Status → rejected |
| 36 | Status badges | ✅ DONE | Yellow/green/red |
| 37 | Message link from accepted | ✅ DONE | Quick link to chat |
| 38 | Withdraw application | ❌ PENDING | Student cannot undo |
| 39 | Reapply after rejection | ❌ PENDING | Blocked by hasApplied |

**Matching & Recommendations**
| # | Feature | Status | Notes |
|---|---|---|---|
| 40 | Student job recommendations | ✅ DONE | Weighted composite: skills 60%, language 40%, noExp bonus (+10) |
| 41 | "Best Matches" section | ✅ DONE | Jobs with score > 0 |
| 42 | "Other Open Jobs" section | ✅ DONE | All jobs including 0% match |
| 43 | Business student matches | ✅ DONE | Top 10 per open job |
| 44 | Skill overlap scoring | ✅ DONE | Substring-based Jaccard 0–100% |
| 45 | Language matching score | ✅ DONE | Student languages vs job required languages |
| 46 | Weighted composite scoring | ✅ DONE | 60/40 weights + No-Experience bonus (+10) |
| 47 | "No Experience Required" badge + bonus | ✅ DONE | Badge on cards, +10 match bonus |
| 48 | Match score breakdown bars | ✅ DONE | Skills/Lang (2 bars) on job detail and matching page |

**Messaging**
| # | Feature | Status | Notes |
|---|---|---|---|
| 49 | Conversation list | ✅ DONE | Avatar, name, last message, time, unread badge |
| 50 | Chat view | ✅ DONE | Sent/received bubbles with timestamps |
| 51 | Send message | ✅ DONE | Text input + Enter/button |
| 52 | Auto-create conversation | ✅ DONE | From `?with=userId` with welcome msg |
| 53 | Mark as read | ✅ DONE | On conversation open |
| 54 | Unread count badge | ✅ DONE | On nav item |
| 55 | Relative timestamps | ✅ DONE | "now", "Xm", "Xh", date |
| 56 | Real-time via WebSocket | ❌ PENDING | Currently poll-on-refresh |

**Reviews & Ratings**
| # | Feature | Status | Notes |
|---|---|---|---|
| 57 | Students review businesses | ✅ DONE | After accepted hire |
| 58 | Businesses review students | ✅ DONE | Same mechanism |
| 59 | Interactive star selector | ✅ DONE | Hover + click, 5-star |
| 60 | Review cards display | ✅ DONE | Stars, name, role, comment, date |
| 61 | "Reviews by You" section | ✅ DONE | |
| 62 | "Reviews About You" section | ✅ DONE | |
| 63 | Prevents duplicate reviews | ✅ DONE | One review per job+reviewer |
| 64 | Aggregate / average rating | ❌ PENDING | Not displayed anywhere |

**User Profile**
| # | Feature | Status | Notes |
|---|---|---|---|
| 65 | View profile | ✅ DONE | Avatar, name, role badge |
| 66 | Edit student profile | ✅ DONE | Name, location, bio, skills |
| 67 | Edit business profile | ✅ DONE | Name, owner name, location, description |
| 68 | Save changes | ✅ DONE | Persists to localStorage |
| 69 | Profile photo / logo upload | ❌ PENDING | Initials-only currently |
| 70 | Reset demo data | ✅ DONE | Wipes localStorage, reloads seed |

**Demo System**
| # | Feature | Status | Notes |
|---|---|---|---|
| 71 | Landing "Experience Platform" role cards | ✅ DONE | 4 color-coded cards |
| 72 | One-click demo entry | ✅ DONE | From role cards |
| 73 | Dashboard demo switcher bar | ✅ DONE | 4 avatar cards |
| 74 | 5-step guided tour | ✅ DONE | Prev/Next/Skip/Finish |
| 75 | Demo exit | ✅ DONE | Returns to landing |

**Internationalization**
| # | Feature | Status | Notes |
|---|---|---|---|
| 76 | English translations (~200 keys) | ✅ DONE | Full UI coverage |
| 77 | Japanese translations (~200 keys) | ✅ DONE | Full UI coverage |
| 78 | Language toggle | ✅ DONE | Sidebar globe button + mobile |
| 79 | Language persistence | ✅ DONE | localStorage |
| 80 | Plural-aware strings | ✅ DONE | `_tn()` function |

#### A5. Monetization Plan

**Revenue Streams:**
```
Revenue Stream          Priority     Estimated % of Revenue (Yr 2)
Employer Subscriptions│ 🔴 High   │    60%
Resume Boost Service  │ 🟡 Medium │    20%
Skill Certifications  │ 🟡 Medium │    10%
Job Post Urgent Badge │ 🟢 Low    │     5%
Premium Profile       │ 🟢 Low    │     5%
```

**Employer Subscription Tiers:**
| Feature | Free | Basic ($29/mo) | Premium ($79/mo) |
|---|---|---|---|
| Active job listings | 1 | Unlimited | Unlimited |
| Applicant views per month | 5 | 100 | Unlimited |
| Candidate screening tools | ❌ | ✅ | ✅ Advanced |
| "Urgent Hire" badge | ❌ | ✅ | ✅ With highlight |
| Analytics dashboard | ❌ | Basic | Full |
| Featured placement | ❌ | ❌ | ✅ Top of search |

**Student pricing always free** — charging employers is standard in job board economics.

**Student Upsells:**
| Feature | Price | Target |
|---|---|---|
| Resume Boost | One-time $14.99 | Competitive roles |
| Skill Certification | Per-course $9.99–$29.99 | Stand out |
| Profile Highlight | $4.99/week | More visibility |
| Interview Prep Kit | One-time $7.99 | All students |

**Partner Revenue:**
| Partner | Model | Revenue Share |
|---|---|---|
| Resume writing services | Affiliate per lead | $5–15/lead |
| Online training platforms | Affiliate per sale | 10–20% |
| Student bank accounts / credit cards | Affiliate per sign-up | $25–100/signup |

#### A6. Competitive Analysis

| Platform | Strengths | Weaknesses | Our Advantage |
|---|---|---|---|
| **Indeed** | Massive reach, brand trust | Not college-specific, spammy | Hyper-local, student-focused |
| **LinkedIn Jobs** | Professional network, recruiter tools | Overkill for part-time | Lighter, privacy-first |
| **Snagajob** | Hourly work, mobile-first | Blue-collar focus | White + blue, university partnerships |
| **Handshake** | University partnerships | Limited to career services | Open marketplace |
| **WayUp** | College focus | Small selection | Open posting, broader base |
| **Craiglist** | Free, massive reach | No quality control, scams | Curated, verified |
| **Campus bulletin boards** | Free, trusted | Limited reach, manual | Digital first, trackable |

**Our sweet spot:** Focused job board with quality matching, specifically for campus-adjacent part-time work.

**Competitive Moat:**
| Moat | Description | Defensibility |
|---|---|---|
| University partnerships | Official integration with career centers | High — requires relationships |
| Review system | Bidirectional ratings create trust network | High — compounds over time |
| Scheduling engine | Availability matching is complex to copy | Medium |
| Local density | More users → more jobs → more users | High — network effects |

---

### B. Logic & Design

#### B1. User Journeys & Flow Diagrams

**Student Journey: Discover → Apply → Hired**
```
┌──────────┐    ┌──────────┐    ┌─────────────┐    ┌───────────┐    ┌────────────┐
│  LANDING  │───▶│  BROWSE  │───▶│   JOB DETAIL │───▶│  APPLY    │───▶│  TRACK APP  │
│  PAGE     │    │  JOBS    │    │   VIEW       │    │  MODAL    │    │  DASHBOARD  │
└──────────┘    └──────────┘    └─────────────┘    └───────────┘    └────────────┘
     │                  │              │                 │                  │
     │                  │              │                 │                  │
     │              Search/Filter    Read            Fill form           Status
     │              Sort by pay       details         Submit              updates
     │              Check reviews     See match        Await response      Chat w/
     │              Save bookmark     %                Employer reply       employer
     ▼
┌──────────┐    ┌──────────┐    ┌────────────┐    ┌───────────┐    ┌────────────┐
│  MATCHING│───▶│   CHAT   │───▶│  INTERVIEW │───▶│  ACCEPTED │───▶│  LEAVE     │
│  RECS    │    │  BUSINESS│    │  (in-app)  │    │  + START  │    │  REVIEW    │
└──────────┘    └──────────┘    └────────────┘    └───────────┘    └────────────┘
```

**Business Journey: Post → Review → Hire**
```
┌──────────┐    ┌──────────┐    ┌─────────────┐    ┌───────────┐
│ REGISTER │───▶│  POST A  │───▶│  REVIEW      │───▶│  MANAGE   │
│ BUSINESS │    │  JOB     │    │  APPLICATIONS│    │  PIPELINE │
└──────────┘    └──────────┘    └─────────────┘    └───────────┘
     │                  │              │                 │
     │              Fill details      Review apps      Accept/Reject
     │              Set pay          Read cover        Chat
     │              Set hours        Score match       Mark filled
     ▼
┌──────────┐    ┌──────────┐    ┌────────────┐
│  MATCHED │───▶│   CHAT   │───▶│  HIRE +    │
│STUDENTS  │    │ STUDENT  │    │  REVIEW    │
└──────────┘    └──────────┘    └────────────┘
```

**Detailed Screen-by-Screen Flow (Student):**
```
Guest State:
  Landing → [Register CTA] → Choose Role → Registration Form → Verify → Dashboard
  Landing → [Login CTA] → Email/Password → Dashboard

Logged In (Student):
  Dashboard → [Browse Jobs] → Jobs Feed
    Jobs Feed → [Filter/Sort] → Filtered Results
    Jobs Feed → [Job Card] → Job Detail → [Apply] → Cover Letter Modal → Submitted!
    Jobs Feed → [Matching Tab] → Recommended Jobs (sorted by match %)

  Dashboard → [My Applications] → Application List
    Application Card → [View Job] → Job Detail
    Application Card → (Status: Pending / Accepted / Rejected)

  Dashboard → [Messages] → Conversation List
    Select Conversation → Chat View → Send/Receive Messages

  Dashboard → [Reviews] → Write Review (if accepted for a job)
             → My Reviews → List of reviews I wrote
             → Reviews About Me → What businesses said about me

  Dashboard → [Profile] → Edit Information / Skills
             → [Logout] → Back to Guest State
```

#### B2. Alternate & Error Flows

**Flow A: Work-Permission Gate (International Student Without Permission)**
```
Guest → Register (student-foreign, workPermission: "no")
     → Dashboard → Browse Jobs → Job Card → [Apply]
         ↓
    ┌───────────────────────────────────┐
    │ ⚠ Work Permission Required        │
    │ You need 資格外活動許可 to apply.  │
    │ [Update Profile] [Cancel]         │
    └───────────────────────────────────┘
         │
         ├─ [Cancel] → Back to Job Detail
         │
         └─ [Update Profile] → Profile Form
              → Set workPermission = "yes"
              → Return to Job Detail
              → [Apply] → Success ✓
```

**Flow B: Business Reviews & Rejects Applicant**
```
Dashboard → Applications → [Review: Pending]
    ↓
Application Detail (student profile + cover letter)
    ├─ [Accept] → Status → "accepted"
    │              → Student notified on next dashboard load
    │
    └─ [Reject] → Confirmation: "Reject this applicant?"
         ├─ [No] → Back
         └─ [Yes] → Status → "rejected"
                     → Optional message field appears:
                       "Send feedback to the student"
                     → Student sees "Rejected" badge
                     → Student cannot re-apply to same job
```

**Flow C: Error & Edge Case Paths**
```
C1 — Duplicate Registration
    Register → Email already in use
         → Show inline error: "This email is already registered"
         → Keep form fields populated
         → User can change email or go to login

C2 — Session Expired (localStorage cleared)
    Any action → Session user is null
         → App redirects to login page
         → Toast: "Session expired. Please log in again."
         → No data loss — mock DB persists in localStorage

C3 — Job No Longer Available
    Browse Jobs → Click job that was filled/deleted
         → Show 404 state: "This job listing is no longer available"
         → [Back to Jobs] → Return to jobs feed

C4 — Empty States
    No applications → "You haven't applied to any jobs yet"
                     → [Browse Jobs] CTA button
    No messages    → "No messages yet. Apply to a job to start chatting!"
    No reviews     → "No reviews yet. Complete a job to get reviewed."
```

**Flow D: Demo Experience Journey**
```
Guest → Landing Page
     → [Try Demo — Japanese Student]
         ↓
    Dashboard loads as Tanaka Yuki (s1)
    → Pre-populated: applications (a1 accepted, a2 pending), 1 unread message
    → User can explore all features with realistic data
    → [Switch Demo Role] → Dropdown shows 4 options
         ├─ Japanese Student (Tanaka Yuki)
         ├─ International Student (James Wilson)
         ├─ Japanese Business (Sarah Miller — Campus Cafe)
         └─ International Business (Demo Business Co)
    → [Reset Demo Data] → Confirm → All data re-seeded from data.js
    → [Logout] → Back to Guest landing page
```

#### B3. Matching Algorithm Specification

**Current Implementation (V4 — Simplified Skill+Language):**
```
finalScore = (
    skillScore × 0.60 +
    languageScore × 0.40
) + noExperienceBonus
```

| Component | Weight | Range | Description |
|---|---|---|---|
| **skillScore** | 60% | 0–100 | Substring-based Jaccard similarity on student.skills vs job.skills |
| **languageScore** | 40% | 0–100 | Fraction of job.languagesRequired matched by student.languages |
| **noExperienceBonus** | +10 | 0–10 | Added if job.noExperience and student has ≤3 skills |

**skillScore (60%):**
```
S_lower = student.skills.map(lowercase)
J_lower = job.skills.map(lowercase)
intersection = count of S items where any J item includes S or vice versa
union = |S_lower ∪ J_lower|
score = round(intersection / union × 100)
```

**languageScore (40%):**
```
If job has no language requirement → 100
else: fraction of job languages matched by student languages
```

**Work Permission Gate:**
International students (`student-foreign`) must have `workPermission === 'yes'` to apply. Those without work permission see a warning and cannot submit applications. Japanese national students bypass this check.

**Score Display:**
- **Match badges**: Colored percentage badges on job cards and detail view (3-tier)
- **Breakdown bars**: 2 horizontal progress bars (Skills/Language) on job detail and matching page
- **Matching page**: "Best Matches" section (score > 0) + "Other Open Jobs" section (score = 0)

**Future Targets:**
| Version | Enhancement | When |
|---|---|---|
| V5 | Location-based scoring (distance decay) | Backend migration |
| V6 | Pay expectation matching | Backend migration |
| V7 | Availability/schedule overlap | Calendar feature |
| V7 | ML collaborative filtering | Scale |

#### B4. Design System & Brand Guidelines

**B4.1 Brand Personality**

JobMatch's design is inspired by a **warm, curated coffee-shop experience** — like Coffee Meets Bagel but for part-time student jobs.

| Attribute | Application |
|---|---|
| Warm | Amber (#F59E0B) accent, cream backgrounds, soft shadows |
| Curated | Match % is the hero metric everywhere |
| Encouraging | "Perfect match! ⭐" / "Great fit! 🤝" / "Give it a try 💪" |
| Trustworthy | Indigo (#4F46E5) anchor color for CTAs |

**B4.2 Color System**
| Token | Value | Usage |
|---|---|---|
| `--primary` | #4F46E5 | CTAs, nav accents, trust anchor |
| `--warm-accent` | #F59E0B | Warm highlights, badges, secondary CTAs |
| `--warm-accent-light` | #FEF3C7 | Warm card backgrounds |
| `--warm-cream` | #FFF8F0 | Page background tint |
| `--coffee` | #92400E | Warm text accents |
| `--bg` | #F5F2F0 | Page background (warm gray) |
| `--border` | #E8E0DA | Subtle warm border |
| `--success` | #10B981 | High match badges |
| `--warning` | #F59E0B | Medium match badges |
| `--text-light` | #94A3B8 | Low match badges |

Role-card accent colors: Blue (#3B82F6) for JP students, Purple (#8B5CF6) for intl students, Amber (#F59E0B) for JP businesses, Green (#10B981) for intl businesses.

**B4.3 Typography**
- **Font stack:** `-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif`
- **Scale:** 11px (hints) → 13px (secondary) → 14px (body) → 16px (titles) → 20px (sections) → 24px (page titles) → 28-40px (hero)
- **Weights:** 500 (body), 600 (buttons/labels), 700 (headings), 800 (hero)
- **Line height:** 1.5 (body), 1.15-1.2 (headings)

**B4.4 Spacing & Layout**
- **Base unit:** 4px (4, 8, 12, 16, 20, 24, 32, 48)
- **Content max-width:** 1000px
- **Card padding:** 20px
- **Section gaps:** 32-48px

**B4.5 Border Radius**
| Token | Value | Usage |
|---|---|---|
| `--radius-sm` | 8px | Inputs, small cards |
| `--radius` | 16px | Cards, modals |
| `--radius-lg` | 24px | Hero container |
| `--radius-pill` | 999px | Buttons, badges, tags |

**B4.6 Animation System**
| Token | Value |
|---|---|
| `--anim-fast` | 150ms |
| `--anim-base` | 250ms |
| `--anim-slow` | 500ms |
| `--ease-bounce` | `cubic-bezier(0.34, 1.56, 0.64, 1)` |

| Keyframe | Trigger | Element |
|---|---|---|
| `fadeIn` | Page transition | `#view-container` |
| `float` | Continuous | Hero sparkles, decorative icons |
| `pop` | Hover | Match badges (high tier) |
| `popIn` | Mount | Today's Picks widget |
| `wiggle` | Hover | Role card icons |
| `sparkle` | Continuous | Hero decoration |
| `shimmer` | Loading | Skeleton loaders |

**Accessibility:** All animations disabled via `prefers-reduced-motion: reduce`.

**B4.7 Copy Tone of Voice**
| Context | Tone | Example |
|---|---|---|
| Hero/CTA | Warm, encouraging | "Your daily batch of hand-matched jobs 🎯" |
| Empty states | Reassuring, helpful | "Your perfect match is waiting! 🌟" |
| Success | Celebratory | "Application sent! Fingers crossed 🤞" |
| Error | Gentle | "Oops! Try again? 🫶" |
| Work permission block | Informative, supportive | "Almost there! Update your profile 📝" |
| Match high (80%+) | Confident | "⭐ Perfect match!" |
| Match medium (50-79%) | Positive | "🤝 Great fit!" |
| Match low (<50%) | Encouraging | "💪 Give it a try" |

**B4.8 Match Badge System**
| Tier | Threshold | Class | Background | Label |
|---|---|---|---|---|
| High | ≥80% | `match-high` | Mint #D1FAE5 | "Perfect match! ⭐" |
| Medium | 50-79% | `match-medium` | Amber #FEF3C7 | "Great fit! 🤝" |
| Low | <50% | `match-low` | Gray `var(--bg)` | "Give it a try 💪" |

**B4.9 Icon & Emoji Usage**
- **Emoji-only** — no icon library dependency
- **Inline:** 1em (within text)
- **Standalone:** 20-28px (badges, tags)
- **Decorative:** 32-48px (card icons, hero)
- **Animated:** Only `float` and `sparkle` — never more than 3 per page

**B4.10 Responsive Breakpoints**
| Breakpoint | Width | Changes |
|---|---|---|
| Desktop | ≥769px | Full sidebar, max-width content |
| Tablet | 481-768px | Sidebar hidden, bottom nav visible |
| Mobile | ≤480px | Single column, hero compact, modals full-width |

Key responsive behaviors:
- Sidebar hidden at ≤768px, bottom nav shown with scroll-snap
- Chat container: `calc(100vh - 260px)` with 300px min and 600px max
- Modals at ≤480px: reduced padding (20px 16px)
- Toast notifications move from top-right to bottom-center on mobile

---

### C. Mockups & Wireframes

#### C1. Complete Route Map (13 Routes + Demo Overlays)

| # | Route | Screen | Status | Auth Required |
|---|---|---|---|---|
| 1 | `#home` | Landing / Hero + 4 role demo cards | ✅ DONE | No |
| 2 | `#register` | Registration (4 tabs: local/foreign student, JP/intl business) | ✅ DONE | No |
| 3 | `#login` | Login form + 4 demo role quick-buttons | ✅ DONE | No |
| 4 | `#dashboard` | Role-aware dashboard + demo switcher bar + tour entry | ✅ DONE | Yes |
| 5 | `#jobs` | Browse & search jobs with filter/no-exp filter | ✅ DONE | Optional |
| 6 | `#job-detail?id=X` | Job detail + match breakdown bars (2-bar) + apply with work-permission gate | ✅ DONE | Optional |
| 7 | `#post-job` | Create job listing (lang requirement + tooltip, no-exp toggle) | ✅ DONE | Business only |
| 8 | `#applications` | Applications list (language badges, student-type badge removed) | ✅ DONE | Yes |
| 9 | `#matching` | Weighted matching (skills/lang — 2 bars) | ✅ DONE | Yes |
| 10 | `#messaging` | Conversations list with language + role indicators | ✅ DONE | Yes |
| 11 | `#messaging?with=X` | Chat with specific user (lang label in header) | ✅ DONE | Yes |
| 12 | `#reviews` | Reviews with role-specific labels | ✅ DONE | Yes |
| 13 | `#profile` | Edit profile (nationality, visa, skills, languages) | ✅ DONE | Yes |
| 14 | `#settings` | App settings / preferences | ❌ PENDING | — |
| 15 | `#admin` | Admin dashboard | ❌ PENDING | Admin only |

**Non-route screens (overlays):**
| Component | Trigger | Status |
|---|---|---|
| Experience Platform demo card grid | Landing page (`#home`) | ✅ DONE |
| Demo role switcher bar | All authenticated pages when `isDemoMode()` | ✅ DONE |
| 5-step guided tour overlay | Dashboard "Start Tour" button | ✅ DONE |
| Apply modal | Job detail "Apply Now" | ✅ DONE |
| Review form modal | Reviews page "Write a Review" | ✅ DONE |
| Toast notifications | Various actions (apply, message, review) | ✅ DONE |
| Profile completeness meter | Dashboard and profile | ✅ DONE |

#### C2. Wireframe Descriptions (ASCII)

**Landing Page:**
```
┌─────────────────────────────────────────────────────┐
│  ╔══════════════════════════════════════════════════╗ │
│  ║  [Gradient hero: primary-light → white → sec]   ║ │
│  ║  Find <span>Part-Time Work</span> Near Campus    ║ │
│  ║                                                  ║ │
│  ║  JobMatch connects university students with      ║ │
│  ║  local businesses hiring for part-time roles.    ║ │
│  ║                                                  ║ │
│  ║  [ 🎓 I'm a Student ]  [ 🏪 I'm a Business ]    ║ │
│  ║  Already have an account? Log in                 ║ │
│  ╚══════════════════════════════════════════════════╝ │
│                                                        │
│  Experience Platform                                   │
│  Try any role instantly — no signup required            │
│                                                        │
│  [4] Role Grid (2x2, color-coded):                     │
│  ┌─────────────┐  ┌─────────────┐                      │
│  │ 🎓 Japanese  │  │ ✈️ Intl     │                      │
│  │   Student    │  │   Student   │                      │
│  │ [blue bar]   │  │ [purple bar]│                      │
│  │ [Try Demo]   │  │ [Try Demo]  │                      │
│  └─────────────┘  └─────────────┘                      │
│  ┌─────────────┐  ┌─────────────┐                      │
│  │ 🏪 Japanese  │  │ 🌐 Intl     │                      │
│  │   Business   │  │   Business  │                      │
│  │ [amber bar]  │  │ [green bar] │                      │
│  │ [Try Demo]   │  │ [Try Demo]  │                      │
│  └─────────────┘  └─────────────┘                      │
│                                                        │
│  How It Works                                           │
│  ┌───┐  ┌───┐  ┌───┐  ┌───┐                           │
│  │ 1 │  │ 2 │  │ 3 │  │ 4 │                            │
│  │ 👤│  │ 🔍│  │ 📩│  │ ⭐│                           │
│  │Creat│ │Brows│ │Apply│ │Revie│                        │
│  └───┘  └───┘  └───┘  └───┘                           │
│                                                        │
│  ╔══════════════════════════════════════════════════╗  │
│  ║  [Purple gradient bar]  Why JobMatch?           ║  │
│  ║    9+ Active Jobs · 5 Local Businesses          ║  │
│  ╚══════════════════════════════════════════════════╝  │
│  🛡️ Free for students  ✅ Verified businesses         │
│  💬 Direct messaging  🔒 No commitment                │
└─────────────────────────────────────────────────────────┘
```

**Job Listing Cards:**
```
┌─────────────────────────────────────────────────┐
│ 📍 Campus Cafe              🟢 63% MATCH        │
│                                                │
│ Barista                                          │
│ 💰 $15/hr · 🕐 Part-time (20hrs/wk) · 📍 Campus │
│ Make coffee, take orders, keep cafe clean...    │
│ Tags: [Customer Service] [Multitasking]          │
│ [View Job →]                                📌  │
└─────────────────────────────────────────────────┘
```

**Chat Interface:**
```
┌──────────────────────────────────────────────────┐
│ ← Back   💬 Sarah Miller (Campus Cafe)           │
├──────────────────────────────────────────────────┤
│         Hi Alex, thanks for your interest...      │
│              - Sarah, 10:30 AM                   │
│     Hi Sarah! I can come in anytime after 2pm.  │
│            - You, 11:00 AM                       │
│  Thursday at 3pm sounds perfect!                 │
│            - Sarah, 11:15 AM                     │
│ ┌──────────────────────────────────────────┐     │
│ │ Type a message...                        │     │
│ └──────────────────┬───────────────────────┘     │
│                    │➤                           │
└──────────────────────────────────────────────────┘
```

**Application Card (Business Review View):**
```
┌─────────────────────────────────────────────────┐
│ 👤 Alex Chen                                   │
│ [JavaScript] [Python] [React]                   │
│ Applied to: Web Developer Intern  ·  Pending    │
│ Cover letter: "I have built several React..."  │
│ [Accept] [Reject] [Message]                    │
└─────────────────────────────────────────────────┘
```

#### C3. Annotated Wireframes (Interaction Zones + Logic)

**Landing Page — Interactive Zones:**
```
┌─────────────────────────────────────────────────┐
│                    JobMatch                      │ ← [1] App title (home-nav)
│          Student Part-Time Jobs                  │
│  ╔═══════════════════════════════════════════╗    │
│  ║  Find Part-Time Work Near Campus          ║    │
│  ║  [2] [I'm a Student] [I'm a Business]     ║    │ ← CTA buttons
│  ╚═══════════════════════════════════════════╝    │
│  How It Works — 4-step icon row [3]               │
│  Stats Bar [4]                                    │
│  Demo Role Cards [5]                              │
│  ┌──────────────┐ ┌──────────────┐               │
│  │ 🇯🇵 Japanese │ │ 🌍 Intl     │               │ ← Click → setSession
│  │   Student    │ │   Student   │               │    + redirect to dashboard
│  ├──────────────┤ ├──────────────┤               │
│  │ 🇯🇵 Japanese │ │ 🌍 Intl     │               │
│  │   Business   │ │   Business   │               │
│  └──────────────┘ └──────────────┘               │
└─────────────────────────────────────────────────┘

Zone logic:
  [1] Title           → decorative, serves as home-nav
  [2] CTA buttons     → onClick → navigate('#register', { tab: 0|2 })
  [3] How it works    → decorative; numbered circles (1-4)
  [4] Stats section   → dynamic counts from DB
  [5] Role cards      → onClick(i) → enterDemo(roleKey)
```

**Job Detail Page — Annotated:**
```
┌─────────────────────────────────────────────────────┐
│ ← [1] Back to Jobs               ╔══════╗ [2] 63%   │
│                                  ╚══════╝           │
│  Campus Cafe  (🏪)                                   │
│  Barista      💰 ¥1,100/hr  🕐 20hrs/wk              │
│  📍 Shibuya, Tokyo   [Food Service]                  │
│  [3] [Japanese] ℹ️   ← lang-tag with tooltip         │
│  [4] Match Breakdown:                                │
│  Skills  ████████████░░ 80%  (60% weight)            │
│  Lang    ████████░░░░░░ 50%  (40% weight)            │
│  [5] [Apply Now] → workPermissionGate() → form       │
│  [6] Job Description                                 │
└─────────────────────────────────────────────────────┘
```

**Apply Modal — State Machine:**
```
┌─────────────────────────────────────────────┐
│  Apply for: Barista at Campus Cafe           │
│  Cover Letter:                               │
│  ┌─────────────────────────────────────┐     │
│  │ I love coffee and have great        │     │
│  │ customer service skills!            │     │
│  └─────────────────────────────────────┘     │
│  [Submit Application]  [Cancel]              │
└─────────────────────────────────────────────┘
        │  onClick(Submit)
        ▼
    ┌──────────────────────────┐
    │ Validate coverLetter    │
    │ > 0 ?                    │
    │ ├─ Yes → create app     │
    │ │      → toast + close  │
    │ │      → redirect #apps │
    │ └─ No  → inline error   │
    └──────────────────────────┘
```

**Dashboard — Student View:**
```
┌─────────────────────────────────────────────────────┐
│ Dashboard                    [Demo Switcher ▼] [1]  │
│ Welcome, Tanaka Yuki  [Japanese Student]             │
│ Profile Completeness: ████████░░ 80%     [2]        │
│ [3] ⚠ Work Permission Required (foreign only)       │
│ Quick Actions: [Browse Jobs] [Apps] [Messages]  [4] │
│ Recent Activity: [5]                                 │
│   ✅ Accepted: Barista at Campus Cafe               │
│   ⏳ Pending: Web Dev at TechFix                    │
│   📩 1 unread message from Sarah Miller             │
│ Matching Suggestions [6]   ╔════╗                   │
│   Campus Cafe - Barista    ║93% ║                   │
│   TechFix - Web Dev        ║88% ║                   │
└─────────────────────────────────────────────────────┘
```

---

### D. Technicals

#### D1. Data Model & Database Schema

**D1.1 Entity-Relationship (Phase 1)**
```
┌─────────────────────────────────┐       ┌─────────────────────────────────┐
│   USER (Student)                │       │   USER (Business)               │
│                                 │       │                                 │
│ id (PK), type='student'         │       │ id (PK), type='business'        │
│ role (local|foreign)            │       │ role (jp|intl)                  │
│ name, email, password           │       │ name, businessName              │
│ nationality (if foreign)        │       │ email, password                 │
│ visaType (if foreign)           │       │ industry                        │
│ workPermission (yes/no/na)      │       │ languagesNeeded[]               │
│ universityName, major           │       │ location, description           │
│ languages[], skills[]           │       │ avatar, createdAt                │
│ location, bio, avatar           │       │                                 │
│ createdAt                       │       │                                 │
└──────────┬──────────────────────┘       └────────────────┬────────────────┘
           │                                              │
           │              ┌─────────────────────┐          │
           │              │       JOB           │          │
           │              │ id (PK)             │◄─────────┘
           │              │ businessId (FK)     │
           │              │ title, description  │
           │              │ category, location  │
           │              │ pay, hours, type    │
           │              │ skills[], postedAt  │
           │              │ status, noExperience│
           │              └─────────┬───────────┘
           │                        │
           │              ┌─────────▼───────────┐
           │              │    APPLICATION      │
           ├──────────────┤ id (PK), jobId (FK) │
           │              │ studentId (FK)      │
           │              │ coverLetter, status │
           │              │ appliedAt           │
           │              └─────────────────────┘
           │
           │         ┌─────────────────────────────────────────┐
           │         │ MESSAGE                                 │
           └─────────┤ id (PK), conversationId                 │
                     │ senderId (FK), receiverId (FK)          │
                     │ text, timestamp, read                   │
                     └─────────────────────────────────────────┘
```

```
┌──────────────┐       ┌──────────────┐       ┌──────────────┐
│   USER       │       │   JOB        │       │   REVIEW     │
│ id (PK)      │       │ id (PK)      │       │ id (PK)      │
│ type, name   │       │ businessId   │◄──────│ fromId (FK)  │
│ email, bio   │       │ title, desc  │       │ toId (FK)    │
│ skills[]     │       │ category     │       │ jobId (FK)   │
│ location     │       │ location,pay │       │ rating 1-5   │
│ avatar       │       │ skills[]     │       │ comment      │
│ createdAt    │       │ postedAt     │       │ createdAt    │
└──────────────┘       │ status       │       └──────────────┘
       │               └──────────────┘
       │                     │
       │                     ▼
┌──────┴──────────────────────────────────┐
│ MESSAGE                                 │
│ id (PK), conversationId                 │
│ senderId (FK), receiverId (FK)          │
│ text, timestamp, read                   │
└─────────────────────────────────────────┘
```

**D1.2 Field-Level Schema (JS Mock Objects)**

**Student Object:**
| Field | Type | Required | Default | Description |
|---|---|---|---|---|
| `id` | string | yes | auto `sN` | Primary key |
| `type` | `"student"` | yes | — | Entity discriminator |
| `role` | `"local"` \| `"foreign"` | yes | — | Role discriminator |
| `name` | string | yes | — | Display name |
| `email` | string | yes | — | Login email |
| `password` | string | yes | — | Plaintext (MVP only) |
| `bio` | string | no | `""` | Self-description |
| `skills` | string[] | no | `[]` | Selected skill tags |
| `location` | string | no | `""` | Campus area |
| `avatar` | string | yes | initials | 2-char initials |
| `nationality` | string | no | `"Japanese"` | Required for foreign students |
| `universityName` | string | no | `""` | School name |
| `major` | string | no | `""` | Field of study |
| `yearOfStudy` | string | no | `""` | `"1st"`–`"4th"` or `"Graduate"` |
| `languages` | string[] | no | `[]` | Spoken languages |
| `langLevel` | string | no | `""` | JLPT N1–N5 or `"Native"` |
| `visaType` | string | no | `"student"` | Visa category (foreign only) |
| `workPermission` | `"yes"` \| `"no"` \| `"na"` | no | `"na"` | Work eligibility gate |
| `createdAt` | string (ISO date) | yes | today | Account creation date |

```json
// Student — Japanese National
{
  "id": "s1", "type": "student", "role": "local",
  "name": "Tanaka Yuki", "email": "tanaka@uni.ac.jp", "password": "pass123",
  "bio": "CS student looking for part-time tech work near campus",
  "skills": ["JavaScript", "Python", "React", "Node.js"],
  "location": "Shibuya, Tokyo", "avatar": "TY",
  "major": "Computer Science", "yearOfStudy": "3rd",
  "languages": ["Japanese", "English"], "langLevel": "JLPT N1",
  "visaType": "student", "nationality": "Japanese",
  "universityName": "Tokyo University",
  "createdAt": "2025-08-01"
}

// Student — International
{
  "id": "s3", "type": "student", "role": "foreign",
  "name": "James Wilson", "email": "james@uni.ac.jp", "password": "pass123",
  "bio": "International student passionate about UI/UX design",
  "skills": ["Figma", "Photoshop", "UI/UX Design", "Illustrator"],
  "location": "Meguro, Tokyo", "avatar": "JW",
  "major": "Media Design", "yearOfStudy": "2nd",
  "languages": ["English", "Basic Japanese"], "langLevel": "JLPT N3",
  "visaType": "student", "nationality": "American",
  "universityName": "Musashino Art University", "workPermission": "yes",
  "createdAt": "2025-08-03"
}
```

**Business Object:**
| Field | Type | Required | Default | Description |
|---|---|---|---|---|
| `id` | string | yes | auto `bN` | Primary key |
| `type` | `"business"` | yes | — | Entity discriminator |
| `role` | `"jp"` \| `"intl"` | yes | — | Role discriminator |
| `name` | string | yes | — | Owner/contact name |
| `businessName` | string | yes | — | Display business name |
| `email` | string | yes | — | Login email |
| `password` | string | yes | — | Plaintext (MVP only) |
| `description` | string | no | `""` | Business profile |
| `location` | string | no | `""` | Business address/area |
| `avatar` | string | yes | initials | 2-char initials |
| `industry` | string | no | `""` | e.g. Food Service, Tech, Retail |
| `languagesNeeded` | string[] | no | `[]` | Languages used in workplace |
| `createdAt` | string (ISO date) | yes | today | Account creation date |

```json
{
  "id": "b1", "type": "business", "role": "jp",
  "name": "Sarah Miller", "businessName": "Campus Cafe Shibuya",
  "email": "sarah@campuscafe.com", "password": "pass123",
  "description": "Popular coffee shop near university campus",
  "location": "Shibuya, Tokyo", "avatar": "CC",
  "industry": "Food Service", "languagesNeeded": ["Japanese", "English"],
  "createdAt": "2025-07-01"
}
```

**Job Object:**
| Field | Type | Required | Default | Description |
|---|---|---|---|---|
| `id` | string | yes | auto `jN` | Primary key |
| `businessId` | string | yes | — | FK → Business.id |
| `title` | string | yes | — | Job title |
| `description` | string | yes | — | Full job description |
| `category` | string | yes | — | Food Service, Tech, Outdoor, etc. |
| `location` | string | yes | — | Work location |
| `pay` | number | yes | — | Hourly wage in JPY |
| `hours` | string | yes | — | e.g. "Part-time (20hrs/wk)" |
| `type` | `"part-time"` | yes | `"part-time"` | Employment type |
| `skills` | string[] | no | `[]` | Required skills |
| `languagesRequired` | string[] | no | `[]` | Languages needed |
| `langTooltip` | string | no | `""` | Contextual tooltip |
| `noExperience` | boolean | no | `false` | Entry-level friendly |
| `postedAt` | string (ISO date) | yes | today | Listing date |
| `status` | `"open"` \| `"filled"` | yes | `"open"` | Listing status |

```json
{
  "id": "j1", "businessId": "b1", "title": "Barista",
  "description": "Make coffee, take orders, keep cafe clean.",
  "category": "Food Service", "location": "Shibuya, Tokyo",
  "pay": 1100, "hours": "Part-time (20hrs/wk)", "type": "part-time",
  "skills": ["Customer Service", "Cash Handling", "Basic Japanese"],
  "languagesRequired": ["Japanese"],
  "langTooltip": "Daily customer interaction with Japanese-speaking patrons.",
  "noExperience": true, "postedAt": "2025-09-01", "status": "open"
}
```

**Application Object:**
| Field | Type | Required | Default | Description |
|---|---|---|---|---|
| `id` | string | yes | auto `aN` | Primary key |
| `jobId` | string | yes | — | FK → Job.id |
| `studentId` | string | yes | — | FK → Student.id |
| `coverLetter` | string | yes | — | Application message |
| `status` | `"pending"` \| `"accepted"` \| `"rejected"` | yes | `"pending"` | Lifecycle state |
| `appliedAt` | string (ISO date) | yes | today | Submission date |

```json
{
  "id": "a1", "jobId": "j1", "studentId": "s1",
  "coverLetter": "I love coffee and have great customer service skills!",
  "status": "accepted", "appliedAt": "2025-09-02"
}
```

**Message Object:**
| Field | Type | Required | Default | Description |
|---|---|---|---|---|
| `id` | string | yes | auto `mN` | Primary key |
| `conversationId` | string | yes | auto `cN` | Groups messages |
| `senderId` | string | yes | — | FK → User.id |
| `receiverId` | string | yes | — | FK → User.id |
| `text` | string | yes | — | Message body |
| `timestamp` | string (ISO datetime) | yes | now | When sent |
| `read` | boolean | no | `false` | Read receipt |

**Review Object:**
| Field | Type | Required | Default | Description |
|---|---|---|---|---|
| `id` | string | yes | auto `rN` | Primary key |
| `fromId` | string | yes | — | FK → reviewer User.id |
| `toId` | string | yes | — | FK → reviewed User.id |
| `jobId` | string | yes | — | FK → Job.id (context) |
| `rating` | number (1–5) | yes | — | Star rating |
| `comment` | string | no | `""` | Review text |
| `createdAt` | string (ISO date) | yes | today | Review date |

```json
{
  "id": "r1", "fromId": "s1", "toId": "b1", "jobId": "j1",
  "rating": 5, "comment": "Great workplace! Sarah is super friendly!",
  "createdAt": "2025-10-01"
}
```

**D1.3 Seed Data (Current Prototype)**

| Entity | Count | Status |
|---|---|---|
| Local Students | 3 | ✅ Seeded |
| Foreign Students | 2 | ✅ Seeded |
| Japanese Businesses | 3 | ✅ Seeded |
| International Businesses | 2 | ✅ Seeded |
| Jobs | 9 | ✅ Seeded |
| Applications | 7 | ✅ Seeded |
| Messages | 12 | ✅ Seeded |
| Reviews | 6 | ✅ Seeded |
| Demo Profiles | 4 | ✅ Seeded |

**D1.4 SQL Schema (PostgreSQL — Target)**

```sql
-- Users
CREATE TYPE user_type AS ENUM ('student', 'business');
CREATE TABLE users (
    id VARCHAR(20) PRIMARY KEY,
    type user_type NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    name VARCHAR(255) NOT NULL,
    bio TEXT, location VARCHAR(255),
    avatar VARCHAR(10), created_at TIMESTAMP DEFAULT NOW(),
    school VARCHAR(255), year_of_study SMALLINT,
    major VARCHAR(255), skills TEXT[],
    business_name VARCHAR(255), description TEXT,
    industry VARCHAR(100), subscription_tier VARCHAR(20) DEFAULT 'free',
    is_verified BOOLEAN DEFAULT FALSE,
    last_login_at TIMESTAMP
);
CREATE INDEX idx_users_type ON users(type);
CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_skills ON users USING GIN(skills);

-- Jobs
CREATE TYPE job_status AS ENUM ('open', 'filled', 'expired');
CREATE TYPE pay_type AS ENUM ('hourly', 'fixed', 'daily');
CREATE TABLE jobs (
    id VARCHAR(20) PRIMARY KEY,
    business_id VARCHAR(20) NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    title VARCHAR(255) NOT NULL, description TEXT NOT NULL,
    category VARCHAR(50) NOT NULL, location VARCHAR(255) NOT NULL,
    pay NUMERIC(8,2) NOT NULL, pay_type pay_type DEFAULT 'hourly',
    hours_type VARCHAR(100), required_skills TEXT[],
    type VARCHAR(20) DEFAULT 'part-time',
    status job_status DEFAULT 'open',
    posted_at TIMESTAMP DEFAULT NOW(), expires_at TIMESTAMP
);
CREATE INDEX idx_jobs_business ON jobs(business_id);
CREATE INDEX idx_jobs_status ON jobs(status) WHERE status = 'open';

-- Applications
CREATE TYPE application_status AS ENUM ('pending','accepted','rejected','withdrawn','interviewing');
CREATE TABLE applications (
    id VARCHAR(20) PRIMARY KEY,
    job_id VARCHAR(20) NOT NULL REFERENCES jobs(id) ON DELETE CASCADE,
    student_id VARCHAR(20) NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    cover_letter TEXT NOT NULL,
    status application_status DEFAULT 'pending',
    applied_at TIMESTAMP DEFAULT NOW(),
    UNIQUE(job_id, student_id)
);

-- Messages
CREATE TABLE conversations (
    id VARCHAR(20) PRIMARY KEY, created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW(), job_id VARCHAR(20) REFERENCES jobs(id)
);
CREATE TABLE messages (
    id VARCHAR(20) PRIMARY KEY,
    conversation_id VARCHAR(20) NOT NULL REFERENCES conversations(id) ON DELETE CASCADE,
    sender_id VARCHAR(20) NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    text TEXT NOT NULL, created_at TIMESTAMP DEFAULT NOW()
);

-- Reviews
CREATE TABLE reviews (
    id VARCHAR(20) PRIMARY KEY,
    author_id VARCHAR(20) NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    target_id VARCHAR(20) NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    job_id VARCHAR(20) NOT NULL REFERENCES jobs(id) ON DELETE CASCADE,
    rating SMALLINT NOT NULL CHECK (rating BETWEEN 1 AND 5),
    comment VARCHAR(2000), created_at TIMESTAMP DEFAULT NOW(),
    UNIQUE(author_id, job_id)
);

-- V2 Tables
CREATE TABLE availability (
    id SERIAL PRIMARY KEY, student_id VARCHAR(20) NOT NULL REFERENCES users(id),
    day_of_week SMALLINT CHECK (day_of_week BETWEEN 0 AND 6),
    start_time TIME NOT NULL, end_time TIME NOT NULL
);
CREATE TABLE subscriptions (
    id SERIAL PRIMARY KEY, business_id VARCHAR(20) NOT NULL REFERENCES users(id),
    tier VARCHAR(20) DEFAULT 'free', starts_at TIMESTAMP DEFAULT NOW(),
    ends_at TIMESTAMP NOT NULL, is_active BOOLEAN DEFAULT TRUE
);
CREATE TABLE notifications (
    id SERIAL PRIMARY KEY, user_id VARCHAR(20) NOT NULL REFERENCES users(id),
    type VARCHAR(50) NOT NULL, title VARCHAR(255) NOT NULL,
    body TEXT NOT NULL, is_read BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT NOW()
);
```

#### D2. Technology Stack

**Current Prototype:**
| Layer | Technology | Justification |
|---|---|---|
| Layout | Semantic HTML5 | Accessible, SEO-friendly |
| Styling | CSS3 (custom properties) | Mobile-first, no frameworks |
| Logic | Vanilla ES6 JavaScript | No build tools, runs in browser |
| Data | In-memory + localStorage | Zero backend dependency |
| i18n | Custom engine (js/i18n.js) | 2 languages, 200+ keys |
| Routing | Hash-based SPA | No server config needed |
| State | Global DB object + localStorage session | Simple, observable |
| Design | System fonts, CSS Grid, Flexbox | Lightweight, responsive |

**Production Target:**
```
CLIENT:
  React.js (Next.js 15) — Pages/App Router, Zustand + React Query
  Tailwind CSS + shadcn/ui, next-intl, Socket.io client, PWA support
        │
        ▼
SERVER:
  Node.js + Express.js — Auth (JWT), Rate limiting, Zod validation
  File upload (Multer → Cloudinary), Email (Resend/SendGrid)
  Socket.io WebSocket server
        │
        ▼
  PostgreSQL 16 — Users, Jobs, Applications, Messages, Reviews
  Meilisearch — Job indexing, geo-aware filtering
```

| Component | Choice | Alternative |
|---|---|---|
| Frontend | Next.js 15 (App Router) | Remix, Vue/Nuxt |
| State | Zustand + React Query | Redux Toolkit |
| Styling | Tailwind CSS + shadcn/ui | CSS Modules |
| i18n | next-intl | react-intl |
| Forms | React Hook Form + Zod | Formik |
| Backend | Node.js + Express | NestJS, Fastify |
| Auth | NextAuth.js + JWT + bcrypt | Clerk, Auth0 |
| Database | PostgreSQL 16 | MySQL 8 |
| ORM | Prisma | Drizzle |
| Uploads | Cloudinary (free tier) | S3 + presigned URLs |
| Search | Meilisearch (OSS) | Algolia |
| CI/CD | GitHub Actions → Vercel | Netlify |
| Testing | Jest + Playwright | Cypress |

#### D3. API Architecture

**Authentication:**
```
POST   /api/v1/auth/register         # Create account
POST   /api/v1/auth/login            # Email/password → JWT
POST   /api/v1/auth/refresh          # Refresh access token
POST   /api/v1/auth/logout           # Invalidate refresh token
POST   /api/v1/auth/forgot-password  # Send reset email
POST   /api/v1/auth/reset-password   # Reset with token
GET    /api/v1/auth/me               # Get current user
```

**Users:**
```
GET    /api/v1/users/me              # Current user profile
PUT    /api/v1/users/me              # Update profile
GET    /api/v1/users/:id             # Public profile
GET    /api/v1/users/:id/reviews     # Reviews for user
```

**Jobs:**
```
GET    /api/v1/jobs                  # List with ?q=, ?category=, ?sort=
GET    /api/v1/jobs/:id              # Single job detail
POST   /api/v1/jobs                  # Create (business only)
PUT    /api/v1/jobs/:id              # Update (owner only)
DELETE /api/v1/jobs/:id              # Delete (owner only)
PATCH  /api/v1/jobs/:id/status       # Update status
GET    /api/v1/jobs/:id/applicants   # List applicants
```

**Applications:**
```
GET    /api/v1/applications          # My applications
POST   /api/v1/applications          # Apply
PATCH  /api/v1/applications/:id/status  # Accept/reject
DELETE /api/v1/applications/:id      # Withdraw
```

**Messaging:**
```
GET    /api/v1/conversations         # List conversations
POST   /api/v1/conversations         # Create new
GET    /api/v1/conversations/:id/messages  # Get messages
POST   /api/v1/conversations/:id/messages  # Send message
```

**Reviews:**
```
GET    /api/v1/reviews               # List (filtered)
POST   /api/v1/reviews               # Create (one per user+job)
DELETE /api/v1/reviews/:id           # Delete own review
```

**Matching:**
```
GET    /api/v1/matching/jobs         # Recommended jobs for student
GET    /api/v1/matching/students     # Recommended students for business
```

**Global Response Format:**
```json
{
  "success": true,
  "data": { ... },
  "meta": { "page": 1, "limit": 20, "total": 153 },
  "message": "Operation completed successfully"
}
```

**Error Response Format:**
```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid input data",
    "details": [
      { "field": "email", "message": "Email is already registered" }
    ]
  }
}
```

#### D4. Internationalization (i18n) — Phase 1

**Coverage:**
| Language | Code | Keys | Status |
|---|---|---|---|
| English | en | ~200 | ✅ Complete |
| Japanese | ja | ~200 | ✅ Complete |

**Engine: Custom client-side `_t(key, ...args)` and `_tn(key, count, ...args)` in `js/i18n.js`.**

```js
let _currentLang = 'en';
function _t(key, ...args) {
  let str = LANG[_currentLang]?.[key] ?? LANG['en']?.[key] ?? key;
  args.forEach((arg, i) => { str = str.replace(new RegExp(`\\{${i}\\}`, 'g'), arg); });
  return str;
}
function _tn(key, count, ...args) {
  const pluralKey = count === 1 ? key : key + '_plural';
  return _t(pluralKey, count, ...args);
}
```

- **Toggle locations:** Bottom nav item (mobile), sidebar item (desktop)
- **Persistence:** localStorage key `jobmatch_lang`

**Key Categories (Phase 1):**
- Authentication & Landing (~25 keys)
- Roles & Badges (~5 keys)
- Dashboard & Navigation (~15 keys)
- Jobs & Job Detail (~30 keys)
- Matching (~10 keys)
- Applications (~15 keys)
- Messaging (~10 keys)
- Reviews (~15 keys)
- Demo System (~20 keys)
- Profile (~15 keys)
- General UI (~10 keys)
- Work Permission Warning (~5 keys)

**Gaps:**
| Gap | Impact | Priority |
|---|---|---|
| DB data not translated (job titles, skills) | Medium | Medium |
| `confirm()` dialogs not i18n'd | Low | Low |
| No `lang` attribute on `<html>` | Medium | Medium |
| No RTL support | Low (V3) | Low |
| Hardcoded `$` currency | Medium | Medium |

#### D5. Security & Compliance

| Requirement | MVP (Prototype) | Production |
|---|---|---|
| Password storage | Plain text (localStorage) | bcrypt hash, server-side |
| Transport security | N/A (file://) | HTTPS mandatory |
| Session management | localStorage session | JWT + refresh token |
| XSS prevention | Minimal | CSP headers, output encoding |
| CSRF protection | N/A | SameSite cookies + CSRF tokens |
| Rate limiting | None | 5 attempts/min on login |
| Input validation | HTML5 attributes | Server-side (Zod) |
| File upload security | None | Type check, size limit, virus scan |
| SQL injection | N/A | Parameterized queries (ORM) |

**Compliance:**
| Requirement | MVP | Production |
|---|---|---|
| Privacy Policy | ❌ | ✅ Required |
| Terms of Service | ❌ | ✅ Required |
| Cookie Consent | ❌ | ✅ Required (GDPR) |
| GDPR Right to Delete | ❌ | ✅ Required |
| Age Verification | ❌ | ✅ Required (COPPA) |
| Accessibility (WCAG 2.1 AA) | ❌ | ✅ Required |

#### D6. Accessibility Requirements (WCAG 2.1 AA)

| Criterion | Current | Target |
|---|---|---|
| Color contrast (4.5:1) | 🟡 Needs audit | ✅ Comply |
| Keyboard navigation | ❌ Not tested | ✅ Comply |
| Screen reader announcements | ❌ None | ✅ ARIA live regions |
| Focus indicators | 🟡 Browser defaults | ✅ Custom indicators |
| Semantic HTML landmarks | 🟡 Minimal | ✅ Full structure |
| ARIA labels | ❌ Missing | ✅ Full labeling |
| Touch targets (48×48px) | ✅ Compliant | ✅ Maintain |
| Reduced motion | ❌ Not implemented | ✅ `prefers-reduced-motion` |
| Dark mode | ❌ Not implemented | ✅ CSS custom properties |

#### D7. Performance Requirements

| Metric | Target |
|---|---|
| First Contentful Paint (FCP) | < 1.5 seconds |
| Time to Interactive (TTI) | < 3.0 seconds |
| Largest Contentful Paint (LCP) | < 2.5 seconds |
| Cumulative Layout Shift (CLS) | < 0.1 |
| API response time (p95) | < 200ms |

**Optimization Strategies (Production):**
- Code splitting — Next.js automatic per-page chunks
- Image optimization — Next.js Image with lazy loading
- Prefetching — `<Link prefetch>` for likely next screens
- Caching — Server-side Redis for job listings
- CDN — Static assets via Vercel Edge Network

#### D8. Error Handling & Edge Cases

**Error Categories:**
| Error Type | User Message (EN) | User Message (JA) | Behavior |
|---|---|---|---|
| Network failure | "Unable to connect. Please check your internet." | "接続できません。" | Retry button + offline indicator |
| Auth required | "Please log in to continue." | "ログインしてください。" | Redirect to `#login` |
| Email already registered | "This email is already registered." | "既に登録されています。" | Stay on register page |
| Invalid credentials | "Incorrect email or password." | "メールまたはパスワードが違います。" | Shake form |
| Job not found | "This job is no longer available." | "この求人はご利用いただけません。" | Navigate to jobs |
| Session expired | "Your session has expired." | "セッションが期限切れです。" | Clear session, redirect to login |
| Validation error | Inline field-specific messages | フィールド固有のメッセージ | Focus first invalid field |
| Empty state | Context-dependent messages | コンテキストに応じたメッセージ | Show helpful guidance + CTA |

**Form Validation Rules:**
| Field | Validation | Error Message |
|---|---|---|
| Name | Required, 2+ characters | "Name must be at least 2 characters" |
| Email | Required, valid email format | "Please enter a valid email address" |
| Password | Required, 8+ chars (production), 4+ (MVP) | "Password must be at least 8 characters" |
| Job title | Required, 3+ characters | "Please enter a job title" |
| Pay rate | Required, number, 1–500 | "Please enter a valid hourly rate" |
| Cover letter | Required, 20+ characters | "Please write a brief cover letter" |
| Category | Required (not empty) | "Please select a category" |

**Offline Support (V2 — PWA):**
- Cache static assets via service worker
- Cache recently viewed job listings
- Queue failed API calls for retry
- Show offline banner when connectivity lost

#### D9. KPIs & Success Metrics

**North Star Metric:** Weekly Active Matches — Number of student-job pairs where a student applied and was accepted within 7 days

**Acquisition (Month 6 / Month 12):**
| Metric | M6 Target | M12 Target |
|---|---|---|
| Total registered students | 1,000 | 10,000 |
| Total registered businesses | 100 | 1,000 |
| Monthly active users (MAU) | 3,000 | 30,000 |
| New signups/week | 100 | 1,000 |

**Engagement (Month 6 / Month 12):**
| Metric | M6 Target | M12 Target |
|---|---|---|
| Jobs posted/week | 20 | 200 |
| Applications per job | 5 | 12 |
| Student weekly return rate | 30% | 50% |
| Business weekly return rate | 40% | 60% |
| Messages sent/week | 100 | 2,000 |

**Quality:**
| Metric | Target |
|---|---|
| Application-to-hire conversion | > 25% (within 7 days) |
| Average time-to-hire | < 5 business days |
| Student satisfaction (≥4★) | > 70% |
| Business satisfaction (≥4★) | > 70% |
| Churn (monthly) | < 10% |

**Revenue (Month 12 / Month 24):**
| Metric | M12 Target | M24 Target |
|---|---|---|
| Paying businesses | 50 | 500 |
| MRR | $1,500 | $30,000 |
| ARPU (paying business) | $30/mo | $35/mo |

#### D10. Development Timeline

**Phase 0 — Validation (COMPLETED ✅)**
```
May 2026
• HTML/CSS/JS prototype built ✓
• 13 screens functional ✓
• English + Japanese i18n ✓
• Matching algorithm validated ✓
```

**Phase 1 — MVP Backend (Weeks 1–6)**
```
Week 1–2: Infrastructure
  • Node.js + Express server, PostgreSQL, CI/CD
Week 3–4: Core Features
  • Auth (register, login, JWT)
  • Job CRUD API, Application flow
Week 5–6: Integration
  • Migrate frontend to API calls
  • WebSocket messaging, Real-time chat
```

**Phase 2 — Polish & Quality (Weeks 7–10)**
```
Week 7–8: File uploads, availability calendar
  • Enhanced matching, Email notifications
Week 9–10: Password hashing, validation, rate limiting
  • Unit tests (Jest) + E2E (Playwright)
  • Accessibility audit
```

**Phase 3 — Launch & Distribution (Weeks 11–14)**
```
Week 11–12: SEO landing page, university partnerships
  • Social media, Referral program
Week 13–14: Stripe integration, subscription tiers
  • Upsell flows, Admin dashboard
```

#### D11. Risk Assessment — Phase 1

| # | Risk | Probability | Impact | Mitigation |
|---|---|---|---|---|
| 1 | Low adoption at launch | High | High | Partner with 2–3 university career centers |
| 2 | Chicken-and-egg problem | High | High | Seed with fake listings, show nearby cities |
| 3 | Student no-shows | Medium | Medium | Reputation system, confirmation requirements |
| 4 | Legal / liability issues | Low | High | ToS, insurance, informational platform only |
| 5 | Competition (Indeed/LinkedIn) | Medium | Medium | Hyper-local + student-specific niche |
| 6 | Data breach | Low | Critical | bcrypt, HTTPS, regular audits |
| 7 | Seasonal demand drops | High | Medium | Summer/winter seasonal promotions |
| 8 | Spam / fake listings | Medium | High | Business email verification, manual review |
| 9 | Scalability concerns | Low | Medium | Start single-server, connection pooling |
| 10 | Accessibility lawsuits | Low | High | WCAG 2.1 AA compliance from V2 |
| 11 | Student data privacy (FERPA) | Low | Critical | No education records collected |

#### D12. Post-Launch Roadmap

**Month 1–3: Stabilization**
- Bug fixes from beta testing
- Performance monitoring & optimization
- Add 3 more university partnerships
- Collect user feedback surveys

**Month 3–6: Growth**
- Mobile PWA (installable, offline support)
- Push notifications (Web Push API)
- University SSO integration (CAS / SAML)
- Group messaging (business → multiple applicants)
- Saved/bookmarked jobs

**Month 6–12: Expansion**
- Multi-city / multi-university expansion
- Integration with university job boards
- Resume builder with AI suggestions
- Interview scheduling (Calendly integration)
- Analytics dashboard for businesses

**Month 12+: Scale**
- Mobile native apps (React Native)
- International expansion
- AI-powered job recommendations (ML pipeline)
- Community features (forums, events)

#### D13. Known Bugs & Issues — Phase 1

| # | Issue | File(s) | Severity | Status |
|---|---|---|---|---|
| 1 | `confirm('Reset all data?')` is hardcoded English | `app.js` | 🟡 Medium | Open |
| 2 | "Other" category missing from browse filter dropdown | `jobs.js` | 🟡 Low | Open |
| 3 | Landing stats `+` suffix unnecessary | `app.js` | 🟢 Cosmetic | Open |
| 4 | Substring matching over-matches | `jobs.js` | 🟡 Medium | Open |
| 5 | `getNextId()` defined but never used | `data.js` | 🟢 Cosmetic | Open |
| 6 | "Applied" badge missing from browse jobs page | `jobs.js` | 🟡 Medium | Open |
| 7 | No aggregate/average rating displayed | `reviews.js` | 🟢 Low | Open |
| 8 | Inconsistent modal close (innerHTML vs remove) | `jobs.js`, `reviews.js` | 🟢 Cosmetic | Open |
| 9 | No `.edu` email validation despite UI hint | `auth.js` | 🟢 Low | Open |
| 10 | Cannot re-apply to rejected jobs | `jobs.js` | 🟡 Medium | Open |
| 11 | Welcome messages hardcoded in English | `messaging.js` | 🟡 Medium | Open |
| 12 | Language auto-detect uses only `navigator.language` | `i18n.js` | 🟢 Low | Open |
| — | ~~`renderLoginPage()` was missing~~ | `auth.js` | ✅ FIXED | Closed |
| — | ~~`lang: 'jp'` should be `'ja'`~~ | `auth.js` | ✅ FIXED | Closed |
| 13 | **CRITICAL**: Seed data role naming mismatch (short keys vs long keys) breaks work-permission gate | `data.js`, `auth.js` | 🔴 Critical | Open |
| 14 | **CRITICAL**: `workPermission` field missing from seed data users | `data.js` | 🔴 Critical | Open |
| 15 | `calculateMatch()` defined twice (dead copy in `data.js`) | `data.js`, `jobs.js` | 🟢 Cosmetic | Open |
| 16 | `visaMatchScore` / `studentTypeMatch` stubs return 100% always | `jobs.js` | 🟢 Cosmetic | Open |
| 17 | Phantom CSS (~100 lines unused): `.onboarding-overlay`, `.skeleton-*`, `.features-grid`, `.lang-selector` | `style.css` | 🟢 Cosmetic | Open |

#### D14. Prototyping Protip

The current prototype is a **multi-file SPA with vanilla JavaScript** that runs entirely in the browser:
- ✅ Open `index.html` directly — works from `file://` in most browsers
- ✅ No build tools, no server, no backend required
- ✅ Instant iteration (edit file, refresh browser)
- ❌ Not suitable for production (no security, no persistence beyond localStorage, no real backend)

For client demos and investor meetings, this prototype is sufficient to demonstrate:
1. Full 4-role user flows (Local Student, Foreign Student, JP Business, Intl Business)
2. 3-layer demo system (landing role cards, dashboard switcher bar, 5-step guided tour)
3. Responsive mobile-first design
4. Weighted composite matching with score breakdown bars
5. Bilingual interface (English ↔ Japanese toggle)
6. Visa tracking, nationality selection, categorized skill tag pickers

**When to graduate from this prototype:**
- When you need real user accounts (beyond 4 demo + 6 seed accounts)
- When you need real persistence (beyond single browser's localStorage)
- When you're ready for >1 concurrent user
- When you need data security

---

## 3. PHASE 2: Donation & Gratitude System

---

### A. Functional & Concept

#### A1. Overview & Philosophy

**What this is NOT:**
- ❌ NOT a fee or service charge
- ❌ NOT a tip (チップ) — this concept is culturally problematic in Japan
- ❌ NOT a disguised payment for job placement (would violate 職業安定法)
- ❌ NOT required or gated — all platform features remain free forever

**What this IS:**

A **voluntary gratitude system** where users who completed a successful match (hire → start → complete) can choose to send a "Thank You Gift" (感謝のお気持ち) to **JobMatch the platform** — to support ongoing operations, server costs, and community building.

```
Conceptual framing:
    "JobMatch is free for everyone. No fees, no subscriptions.
     If a match changed your life, you can send us a 
     'Thank You Cookie' 🍪 — a small donation (min ¥1,000) 
     to help keep the platform running."
```

#### A2. Feature Inventory — Phase 2

| # | Feature | Status | Notes |
|---|---|---|---|
| 81 | Photo upload (student profile, base64, <500KB) | ✅ DONE | On student profile edit form |
| 82 | Video intro upload (createObjectURL, session-only) | ✅ DONE | Metadata stored, blob cleared on refresh |
| 83 | Media visibility gate (business unlocks after acceptance) | ❌ PENDING | Locked → unlocked on status=accepted |
| 84 | Interview scheduling (business: type + date) | ✅ DONE | Radio: in-person/online/telephone + date picker |
| 85 | Interview card (student view) | ✅ DONE | Shows type, date, message link |
| 86 | Hire action (business → status=hire, toast) | ✅ DONE | Confirmation dialog, sets hiredAt |
| 87 | Start action (business → status=started, congrats modal) | ✅ DONE | Confirmation, sets startedAt |
| 88 | Congratulatory toast (both parties, shareable) | ✅ DONE | Wishes luck, toast on hire/start |
| 89 | 7-day review trigger (dashboard banner) | ✅ DONE | Checks startedAt + 7 days |
| 90 | Review gating (blocks apply/post until review done) | ✅ DONE | Uber-style: pending review blocks new actions |
| 91 | Donation prompt modal (¥1,000–¥5,000) | ✅ DONE | 4 preset amounts + custom, optional message |
| 92 | Supporters wall (public donation display) | ✅ DONE | Shows public donations per user profile |
| 93 | Success toast (social proof, shareable) | 🟡 PARTIAL | Toast exists; no social media share |
| 94 | Donation skip tracking (one-time per user per job) | ❌ PENDING | Prevents re-prompt after skip |
| 95 | Extended application statuses | ✅ DONE | interview, hired, started, done |

#### A3. Cultural Framing for Japan

| Element | Japanese Framing | Rationale |
|---|---|---|
| Button label | 「応援する」(Support us) | Sounds like cheering, not paying |
| Amount label | 「感謝のお気持ち」(Feeling of gratitude) | Warm, personal, non-transactional |
| Min amount explanation | ¥1,000 ≈ お菓子折り (thank-you cookie box) | Relatable cultural reference |
| Skip button | 「また今度」(Maybe later) | Casual, no guilt |
| Success message | 「応援ありがとうございます！JobMatch は皆さんのサポートで運営されています」 | Gratitude, not transaction |
| Donation name | Thank-You Cookie 🍪 | Playful, warm, non-monetary framing |

**Why this works in Japan:**
- Gift-giving (お礼/内祝い) is deeply ingrained culturally
- ¥1,000–¥3,000 maps to standard お菓子折り (thank-you sweets) range
- "Support us" (応援) is commonly used for creator/platform patronage
- No pressure — "Maybe later" is a natural Japanese polite decline

#### A4. Legal Compliance Notes

**Employment Security Law (職業安定法) Compliance:**

The April 2025 amendments prohibit:
| Prohibited Act | Applies to JobMatch? | Why |
|---|---|---|
| Platform paying workers "celebration money" for getting hired | ❌ Not applicable | Money flows user → platform, not platform → user |
| Platform charging fees to workers for job placement | ❌ Not applicable | Platform is free. Donation voluntary, post-hoc |
| Deceptive fee collection | ⚠️ Must comply | Clear disclosure: donation voluntary, NOT a fee |

**Key compliance measures:**
1. **Voluntariness paramount** — NEVER presented as required or connected to service quality
2. **Clear disclaimer on every donation screen**: "This is NOT a fee. JobMatch is 100% free."
3. **No service degradation** — donors and non-donors get identical experience
4. **No targeting** — donation prompt appears once per completed match
5. **Skip is default** — "Skip" button as prominent as "Send"

**Consumer Protection (特定商取引法):**
| Requirement | Compliance |
|---|---|
| Business operator name/address display | ✅ Listed on donation page |
| Price display (including tax) | ✅ Amount shown in JPY |
| Returns/cancellation policy | ✅ Donations final — clearly stated |

**Tax Implications:**
| Entity | Implication |
|---|---|
| JobMatch (platform) | Donations = taxable income |
| Donor (user) | Personal donations not tax-deductible in Japan |
| Classification | "Donation" (寄付金) not "fee" (手数料) — critical legal distinction |

**Data Privacy:**
| Concern | Handling |
|---|---|
| Donor identity on Supporters Wall | Opt-in only (default: off) |
| Individual donation amounts | Private (aggregated total only) |
| Right to delete | Donations immutable, public display removable |

---

### B. Logic & Design

#### B1. Extended Application Status Machine

**Phase 1 statuses:**
```
pending ──accepted──→ [stop]
    └──rejected──→ [TERMINAL]
```

**Phase 2 full status machine:**
```
pending ──accepted──→ interview ──hired──→ started ──complete──→ done
    │                                                                
    └──rejected──→ [TERMINAL]        (7-day timer)           
                                         │                        
                                    review prompt             
                                         │                        
                              ┌──────────┴──────────┐         
                              │                     │         
                          submit review        skip review      
                              │                     │         
                         donation prompt          [gating active]
                              │                     │         
                            done                   done (gated)
```

**Transition rules:**
| From | To | Triggered By | Business Rules | Side Effects |
|---|---|---|---|---|
| `pending` | `accepted` | Business Accept | Must be job owner | Unlocks photo/video media |
| `pending` | `rejected` | Business Reject | Must be job owner | Terminal state |
| `accepted` | `interview` | Business sets type + date | Must be accepted; type ∈ {in-person, online, telephone} | Sets `interviewType`, `interviewDate` |
| `interview` | `hired` | Business "Hire" | Must be `interview` | Sets `hiredAt = now` |
| `hired` | `started` | Business "Started" | Must be `hired` | Sets `startedAt = now` |
| `started` | `done` | System (auto) | Both reviews submitted | Sets `completedAt = now` |

**Terminal states:** `rejected`, `done` — no further transitions allowed.

**Invariants:**
- Status transitions strictly sequential — no skipping
- Each transition validated by a guard function
- Business-only transitions check caller identity
- All mutations call `saveDB()`

```js
function updateApplication(appId, newStatus, extra) {
  const app = DB.applications.find(a => a.id === appId);
  if (!app) return;
  
  const VALID_TRANSITIONS = {
    'pending':   ['accepted', 'rejected'],
    'accepted':  ['interview'],
    'interview': ['hired'],
    'hired':     ['started'],
    'started':   ['done'],
    'rejected':  [],
    'done':      []
  };
  
  if (!VALID_TRANSITIONS[app.status]?.includes(newStatus)) {
    showAlert('Invalid status transition', 'error');
    return;
  }
  // Apply transition...
}
```

#### B2. Review Gating Logic (Uber-Style)

**Core function:**
```js
function getPendingRequiredReviews(user) {
  const cutoff = new Date();
  cutoff.setDate(cutoff.getDate() - 7);
  
  return DB.applications.filter(a => {
    const isInvolved = a.studentId === user.id || 
      (user.type === 'business' && getJobById(a.jobId)?.businessId === user.id);
    if (!isInvolved || a.status !== 'started') return false;
    if (!a.startedAt || new Date(a.startedAt) > cutoff) return false;
    
    const otherId = a.studentId === user.id 
      ? getJobById(a.jobId)?.businessId 
      : a.studentId;
    
    const hasReview = DB.reviews.some(r => 
      r.fromId === user.id && r.toId === otherId && r.jobId === a.jobId
    );
    return !hasReview;
  });
}

function isReviewGatingActive(user) {
  return getPendingRequiredReviews(user).length > 0;
}
```

**Blocked actions:**
| Role | Blocked action | UX |
|---|---|---|
| Student | Click "Apply Now" on any job | Button disabled, tooltip: "Please complete your pending review first 📝" |
| Business | Click "Post a Job" nav item | Item grayed out, tooltip: "Complete pending reviews to post new jobs" |
| Business | Accept new applications | Accept button disabled with same tooltip |

**Unblock conditions:**
- Submit review for EACH pending required application
- Instant unblock (no page reload needed)

**Edge cases:**
- Multiple concurrent started jobs → ALL past 7 days need review
- One job past 7 days, another not yet → only the past-7 one blocks
- User has 0 started jobs → no gating
- Reviews submitted → instant unblock

#### B3. Donation Flow (Step-by-Step)

```
1. [Student/Business uses JobMatch]
           │
2. [Application → accepted → interview → hired → started]
           │
3. [7 days after startedAt]
           │
   ┌─────────▼────────────────────────────────────┐
   │  Dashboard: Review Request Banner            │
   │  "You started working at Campus Cafe!        │
   │   How is it going? Share your experience."   │
   └─────────┬──────────────────────────────────────┘
           │
4. ┌─────────▼──────────────────────────────────────┐
   │  Review Form (existing)                        │
   │  ★★★★☆ + Comment + [Submit]                   │
   └─────────┬──────────────────────────────────────┘
           │
5. ┌─────────▼──────────────────────────────────────┐
   │  🎉 Both Reviews Submitted!                    │
   │  "Thanks for being part of JobMatch!"          │
   └─────────┬──────────────────────────────────────┘
           │
6. ┌─────────▼──────────────────────────────────────┐
   │  Donation Prompt Modal                         │
   │  ☕ "Send a Thank-You Cookie to JobMatch 🍪"   │
   │  [¥1,000] [¥2,000] [¥3,000] [¥5,000]          │
   │  [Custom amount]  [Skip]                       │
   │  ⚠ "This is NOT a fee. JobMatch is free."     │
   └─────────┬──────────────────────────────────────┘
           │
7a. [SEND]               7b. [SKIP]
   ┌─────────▼──┐         ┌────────────────────┐
   │ 🎉 Thanks! │         │ "No problem!       │
   │ Your ¥X,000│         │  You can support   │
   │ keeps us   │         │  later from your   │
   │ free! 🙏   │         │  profile."         │
   └─────────┬──┘         └────────────────────┘
           │
8. ┌─────────▼──────────────────────────────────────┐
   │  🎉 Success Toast (shareable)                  │
   │  "{name} found their job via JobMatch          │
   │   and sent a Thank-You Cookie! 🍪"             │
   │  [📤 Share] [Back to Dashboard]                │
   └─────────────────────────────────────────────────┘
```

#### B4. Business Rules & Invariants

**Donation rules:**
- One donation per user per job (no double-tipping)
- Minimum: ¥1,000 (≈ cost of thank-you cookie box)
- Maximum: ¥10,000 (client-side cap)
- Can send with optional gratitude message (max 200 chars)
- Message can be made public (shown on Supporters Wall)
- Immutable once created (no edit/delete)
- `isPublic: false` → donation counted in total but message not shown

**Media visibility rules:**
- Student uploads photo/video to own profile (always visible to self)
- Business sees locked placeholder in application detail
- After accept → lock icon becomes clickable → opens modal

**Review gating invariants:**
- Function `isReviewGatingActive(user)` called before every blocked action
- Gating only checks `status === 'started'` applications past 7 days
- Reviews submitted for ALL such applications → gate lifted immediately
- No review = no unblock, regardless of donation status

---

### C. Mockups & Wireframes — Phase 2

#### C1. Student Profile — Photo/Video Upload
```
┌──────────────────────────────────────────┐
│   Edit Profile                           │
│                                          │
│   Name         [Tanaka Yuki         ]   │
│   Email        [tanaka@uni.ac.jp    ]   │
│                                          │
│   ┌────────────────────────────────────┐ │
│   │  Profile Photo                     │ │
│   │  ┌────────┐                        │ │
│   │  │        │   [Change Photo]       │ │
│   │  │  👤    │   [Remove]             │ │
│   │  │        │   Max 500KB · JPG/PNG  │ │
│   │  └────────┘                        │ │
│   └────────────────────────────────────┘ │
│                                          │
│   ┌────────────────────────────────────┐ │
│   │  Video Introduction                │ │
│   │  ┌──────────────────────────┐      │ │
│   │  │ ▶️ Video Preview         │      │ │
│   │  └──────────────────────────┘      │ │
│   │  [Upload Video (max 30s)]          │ │
│   │  ℹ️ Session-only (not saved        │ │
│   │     across refreshes)              │ │
│   └────────────────────────────────────┘ │
│                                          │
│   [Save Changes]    [Cancel]             │
└──────────────────────────────────────────┘
```

#### C2. Business Application — Media Gate
```
┌──────────────────────────────────────────┐
│   Applicant: Tanaka Yuki                 │
│   Job: Barista @ Campus Cafe             │
│   Status: ✅ Accepted                    │
│                                          │
│   ┌────────────────────────────────────┐ │
│   │  Student Profile                   │ │
│   │  ┌────────┐  Tanaka Yuki          │ │
│   │  │  👤    │  Japanese Student     │ │
│   │  │        │  Tokyo University     │ │
│   │  └────────┘  3rd Year · CS Major  │ │
│   │                                     │ │
│   │  [📷 View Photo] [🎬 View Video]   │ │
│   │  (Media unlocked after acceptance)  │ │
│   └────────────────────────────────────┘ │
└──────────────────────────────────────────┘

// Before acceptance — locked state:
│   ┌────── Locked ──────┐               │
│   │  🔒 Photo available │               │
│   │  after acceptance   │               │
│   └─────────────────────┘               │
```

#### C3. Interview Scheduling (Business)
```
┌──────────────────────────────────────────┐
│   Schedule Interview                     │
│   Applicant: Tanaka Yuki                 │
│   Job: Barista @ Campus Cafe             │
│                                          │
│   Interview Type:                        │
│   ┌────────────────────────────────────┐ │
│   │ ○ In-Person (対面)                 │ │
│   ├────────────────────────────────────┤ │
│   │ ● Online (オンライン)             │ │
│   ├────────────────────────────────────┤ │
│   │ ○ Telephone (電話)                │ │
│   └────────────────────────────────────┘ │
│                                          │
│   Date & Time:                           │
│   [📅 2026-05-20] [🕐 14:00]           │
│                                          │
│   [Send Interview Request]  [Cancel]     │
└──────────────────────────────────────────┘
```

#### C4. Interview Card (Student)
```
┌──────────────────────────────────────────┐
│  Interview Scheduled 🎯                  │
│                                          │
│  Barista @ Campus Cafe                   │
│  ┌────────────────────────────────────┐  │
│  │  📅 Date:  May 20, 2026           │  │
│  │  🕐 Time:  2:00 PM                │  │
│  │  💻 Type:  Online (Zoom)          │  │
│  └────────────────────────────────────┘  │
│                                          │
│  [📩 Message Business]                   │
└──────────────────────────────────────────┘
```

#### C5. Hire → Start → Congrats Flow
```
// Step 1: Hired
┌──────────────────────────────────────────┐
│  ✅ Mark as Hired                        │
│  "Hire Tanaka Yuki for Barista?"         │
│  [Yes, Hire! 🎉]  [Cancel]              │
└──────────────────────────────────────────┘
         │
// Step 2: Started
┌──────────────────────────────────────────┐
│  🚀 Mark as Started                      │
│  "Confirm Tanaka Yuki has started?"      │
│  [Yes, They Started!]  [Cancel]          │
└──────────────────────────────────────────┘
         │
// Step 3: Congratulatory Toast (BOTH parties)
┌──────────────────────────────────────────┐
│  🎉🎉🎉 Congratulations! 🎊             │
│                                          │
│  Tanaka Yuki started working at          │
│  Campus Cafe! 🚀                         │
│                                          │
│  We wish you both the very best! 🍀      │
│                                          │
│  [Share this moment]  [OK]              │
└──────────────────────────────────────────┘
```

#### C6. Review Request Banner (7-Day Trigger)
```
┌── Dashboard ─────────────────────────────┐
│                                          │
│  ┌── Reminder ──────────────────────────┐│
│  │  📝 You started at Campus Cafe       ││
│  │  8 days ago! How is it going?        ││
│  │                                      ││
│  │  [Write Review] [Remind Later]       ││
│  └──────────────────────────────────────┘│
└──────────────────────────────────────────┘
```

#### C7. Review Gating (Blocked Actions)
```
// Student trying to apply:
┌──────────────────────────────────────────┐
│  📝 Complete Your Review First           │
│  Submit your pending review before       │
│  applying to new jobs.                   │
│  [Go to Reviews]  [Cancel]              │
└──────────────────────────────────────────┘

// Business trying to post:
┌──────────────────────────────────────────┐
│  📝 Complete Your Review First           │
│  Submit pending review before posting    │
│  new jobs.                               │
│  [Go to Reviews]  [Cancel]              │
└──────────────────────────────────────────┘
```

#### C8. Donation Prompt Modal
```
┌──────────────────────────────────────────────┐
│  ☕ Support JobMatch                         │
│  Send a Thank-You Cookie 🍪                 │
│                                              │
│  "JobMatch helped connect you with the       │
│   perfect opportunity — 100% free.           │
│   Send us a small 'Thank You Cookie' to      │
│   keep the platform running."                │
│                                              │
│  Choose your cookie 🍪                       │
│  ┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐│
│  │  🍪    │ │ 🍪🍪   │ │ 🍪🍪🍪 │ │  💝   ││
│  │¥1,000  │ │¥2,000  │ │¥3,000  │ │¥5,000  ││
│  └────────┘ └────────┘ └────────┘ └────────┘│
│  Custom: ¥ [________]                        │
│                                              │
│  Message (optional, 200 chars):              │
│  ┌──────────────────────────────────────┐   │
│  │ "Thank you for finding me the        │   │
│  │  perfect job!"                       │   │
│  └──────────────────────────────────────┘   │
│  ☑ Show publicly on Supporters Wall         │
│                                              │
│  ⚠ This is NOT a fee. JobMatch is free.     │
│  Donations are voluntary.                    │
│                                              │
│  [Send Thank You 🍪]    [Skip]              │
└──────────────────────────────────────────────┘
```

#### C9. Supporters Wall (Public Profile Section)
```
┌──────────────────────────────────────────┐
│  🙏 Thank-You Supporters                 │
│                                          │
│  5 people have sent their gratitude      │
│  to keep JobMatch running!               │
│                                          │
│  ┌────────────────────────────────────┐  │
│  │  🍪 Tanaka Yuki                    │  │
│  │     "Thank you for finding me the  │  │
│  │      perfect job!"                 │  │
│  │     Sent 2 weeks ago               │  │
│  ├────────────────────────────────────┤  │
│  │  🍪 Sarah Miller · Campus Cafe    │  │
│  │     "Great platform!"              │  │
│  │     Sent 1 week ago                │  │
│  ├────────────────────────────────────┤  │
│  │  🍪 Anonymous Supporter            │  │
│  │     Sent 3 days ago               │  │
│  └────────────────────────────────────┘  │
│                                          │
│  [Support JobMatch Too 🍪]               │
└──────────────────────────────────────────┘
```

---

### D. Technicals — Phase 2

#### D1. Data Model Additions

**Application Schema Extension:**
```js
application = {
  // ...existing fields (id, jobId, studentId, coverLetter, status, appliedAt)
  interviewType: null | 'in-person' | 'online' | 'telephone',
  interviewDate: null | '2026-05-20T14:00:00',
  hiredAt: null | '2026-05-15T10:00:00',
  startedAt: null | '2026-05-20T09:00:00',
  completedAt: null | '2026-06-01T12:00:00',
  photoViewed: false,
  videoViewed: false
}
```

**Student Schema Extension:**
```js
student = {
  // ...existing fields
  photo: null | 'data:image/jpeg;base64,...',      // Base64 data URL
  videoIntro: null | {                              // Metadata object
    filename: 'intro.mp4',
    uploadedAt: '2026-05-15T10:00:00',
    blobUrl: 'blob:...'   // Session-only, cleared on refresh
  }
}
```

**New Collection: Platform Donations:**
```js
DB.platformDonations = [
  {
    id: 'pd1',
    userId: 's1',            // Who donated (student or business)
    userType: 'student',     // 'student' | 'business'
    jobId: 'j1',             // Which match inspired the donation
    amount: 1000,            // Integer, >= 1000
    message: 'Thank you for finding me the perfect job!',
    isPublic: true,          // Show on Supporters Wall
    createdAt: '2026-06-01T12:00:00'
  }
]
```

**Extended Entity Relationship:**
```
┌─────────────────────────────────┐
│            APPLICATION          │
│ id (PK), jobId (FK)            │
│ studentId (FK), coverLetter    │
│ status [interview/hired/started/done]  ◄── Extended
│ interviewType (Phase 2)        │
│ interviewDate (Phase 2)        │
│ hiredAt / startedAt / completedAt │
│ photoViewed / videoViewed      │
└──────────┬──────────────────────┘
           │
           │ ┌────────────────────────────────┐
           │ │     PLATFORM DONATION (NEW)    │
           ├─┤ id (PK), userId (FK)          │
           │ │ userType, jobId (FK)          │
           │ │ amount (INT >= 1000)          │
           │ │ message (OPT, 200 chars)      │
           │ │ isPublic (BOOL)               │
           │ │ createdAt                     │
           │ └────────────────────────────────┘
           │
           │ ┌────────────────────────────────┐
           │ │     USER (Student Extended)    │
           └─┤ photo (base64)                │
             │ videoIntro (metadata)         │
             └────────────────────────────────┘
```

#### D2. i18n Key Inventory — Phase 2 (45 New Keys)

**Application Status & Pipeline:**
| Key | EN | JA |
|---|---|---|
| `status.interview` | Interview Scheduled | 面接予定 |
| `status.hired` | Hired | 採用済み |
| `status.started` | Started | 勤務開始 |
| `status.done` | Completed | 完了 |
| `apps.interview` | Schedule Interview | 面接を設定 |
| `apps.interviewInPerson` | In-Person | 対面 |
| `apps.interviewOnline` | Online | オンライン |
| `apps.interviewPhone` | Telephone | 電話 |
| `apps.interviewDate` | Interview Date | 面接日 |
| `apps.interviewScheduled` | Interview Request Sent! | 面接リクエストを送信しました！ |
| `apps.interviewBadge` | Interview Scheduled 🎯 | 面接予定 🎯 |
| `apps.hire` | Mark as Hired | 採用する |
| `apps.hireConfirm` | Hire {0} for {1}? | {0}を{1}として採用しますか？ |
| `apps.hiredToast` | 🎉 Hired! Welcome to the team! | 🎉 採用おめでとうございます！ |
| `apps.start` | Mark as Started | 勤務開始を確認 |
| `apps.startConfirm` | Confirm {0} has started? | {0}が勤務を開始したことを確認しますか？ |
| `apps.startedToast` | 🚀 Confirmed started! | 🚀 勤務開始を確認しました！ |
| `apps.congratsTitle` | 🎉 Congratulations! | 🎉 おめでとうございます！ |
| `apps.congratsBody` | {0} started at {1}! Best of luck! 🍀 | {0}が{1}で勤務を開始しました！🍀 |
| `apps.wishLuck` | We wish you a wonderful journey! | 素晴らしい旅になりますように！ |
| `apps.mediaPhoto` | View Photo | 写真を見る |
| `apps.mediaVideo` | View Video | 動画を見る |
| `apps.mediaLocked` | Available after acceptance | 承認後に利用可能 |

**Profile — Photo & Video:**
| Key | EN | JA |
|---|---|---|
| `profile.photo` | Profile Photo | プロフィール写真 |
| `profile.photoHint` | Max 500KB · JPG or PNG | 最大500KB · JPGまたはPNG |
| `profile.videoIntro` | Video Introduction | 自己紹介動画 |
| `profile.videoHint` | Introduce yourself briefly (max 30s) | 簡単な自己紹介（最大30秒） |
| `profile.videoSessionOnly` | Video is session-only | 動画はセッション限定です |

**Reviews & Donation:**
| Key | EN | JA |
|---|---|---|
| `review.reminder` | You started at {0} 8 days ago! How is it going? | {0}で勤務開始から8日経ちました！いかがですか？ |
| `review.gatingTitle` | Review Required | レビューが必要です |
| `review.gatingDesc` | Submit pending review before applying | 新しい求人に応募する前にレビューを提出してください |
| `review.gatingDescBiz` | Submit pending review before posting | 新しい求人を投稿する前にレビューを提出してください |
| `review.gatingAction` | Go to Reviews | レビューへ |
| `donate.title` | Support JobMatch ☕ | JobMatchを応援する ☕ |
| `donate.subtitle` | Send a Thank-You Cookie 🍪 | 感謝のお気持ちを送る 🍪 |
| `donate.amount1` | 🍪 ¥1,000 — Cookie | 🍪 ¥1,000 |
| `donate.amount2` | 🍪🍪 ¥2,000 — Double | 🍪🍪 ¥2,000 |
| `donate.amount3` | 🍪🍪🍪 ¥3,000 — Party | 🍪🍪🍪 ¥3,000 |
| `donate.amount5` | 💝 ¥5,000 — Premium | 💝 ¥5,000 |
| `donate.custom` | Custom amount | カスタム金額 |
| `donate.min` | Minimum: ¥1,000 | 最低: ¥1,000 |
| `donate.message` | Message (optional, 200 chars) | メッセージ（任意） |
| `donate.public` | Show publicly | 公開する |
| `donate.submit` | Send Thank You 🍪 | 送信する 🍪 |
| `donate.skip` | Maybe later | また今度 |
| `donate.thanks` | Thank You! 🙏 | ありがとうございます！🙏 |
| `donate.thanksDesc` | Your ¥{0} keeps JobMatch free! | ¥{0}のご支援でJobMatchは無料で運営できます！ |
| `donate.disclaimer` | NOT a fee. JobMatch is 100% free. | 手数料ではありません。JobMatchは完全無料です。 |
| `donate.wallTitle` | 🙏 Thank-You Supporters | 🙏 応援してくださった方々 |
| `donate.wallCount` | {0} supporters! | {0}人の方が応援！ |
| `toast.successTitle` | 🎉 Another Great Match! | 🎉 また一つ素敵なマッチング！ |
| `toast.successBody` | {0} found their job and shared gratitude! 🍪 | {0}が仕事を見つけ、感謝の気持ちを送りました！🍪 |
| `toast.share` | Share this story | シェアする |

#### D3. KPI Targets — Phase 2

| Metric | Target (Month 3) |
|---|---|
| Donation conversion rate (% of completed matches) | > 15% |
| Average donation amount | ¥1,500 |
| Monthly donation revenue (at 100 completed matches/mo) | ¥22,500 |
| Review submission rate (within 7 days of prompt) | > 60% |
| Supporters Wall profiles with ≥1 public donation | > 10% |
| Success toast shares (per 100 matches) | > 5 |
| Users unblocked by review gating | > 90% within 48 hours |

#### D4. Risk Assessment — Phase 2

| # | Risk | Probability | Impact | Mitigation |
|---|---|---|---|---|
| 1 | Perceived as fee in disguise | Medium | High | Clear legal disclaimer on every screen |
| 2 | Low donation adoption | High | Low | Success toast as social proof; not primary revenue |
| 3 | Video storage impractical | High | Medium | Session-only with clear messaging |
| 4 | Review gating creates frustration | Medium | Medium | Gentle reminders; easy path to complete |
| 5 | Legal scrutiny from MHLW | Low | Critical | Peer-to-peer framing; transparent disclosures |
| 6 | Donation fraud / chargebacks | Low | Medium | Fraud detection; manual review of large amounts |

---

## 4. Appendix: Implementation Audit

### Code vs Documentation Audit (conducted 2026-05-15)

**Phase 1 — Implemented vs PRD-only:**

| Area | Features Implemented | Features Missing |
|---|---|---|
| Auth | Registration, Login, Demo credentials, Session, Logout, Work permission radio, Skill/language tag pickers | Password hashing, Email verification, Forgot password, Social login, Account deletion |
| Jobs | Post form, Browse, Detail, Search, Filter, Sort, Match %, No-exp toggle | Job editing, Deletion, Mark filled, Save/bookmark, Applied badge on browse |
| Applications | Apply modal, Student/business lists, Accept/reject, Interview scheduling, Hire/start actions, Congratulatory toast, Extended statuses (interview/hired/started), Status badges, Message link | Withdraw, Reapply after rejection |
| Matching | Weighted scoring, Best matches section, Business matches, Breakdown bars, No-exp bonus | Location, Pay, Schedule matching |
| Messaging | Conversation list, Chat view, Send, Auto-create, Mark read, Unread count | WebSocket, Typing indicators, File sharing |
| Reviews | Student/business reviews, Star selector, Card display, By-you/about-you, Duplicate prevention, 7-day review trigger, Review gating (Uber-style), Donation prompt modal, Supporters wall | Aggregate rating, Shareable social media |
| Profile | View/edit, Reset demo, Completeness meter, Photo upload (base64), Video intro (session-only) | — |
| Demo | Role cards, One-click entry, Switcher bar, 5-step tour, Exit | — |
| i18n | EN + JA ~200 keys, Toggle, Persistence, Plural-aware | RTL, Locale-aware dates/currency |

**Phase 2 — Implemented 2026-05-15:**

**Critical Bugs — Status:**

| # | Bug | Status | Notes |
|---|---|---|---|
| 1 | Seed data role naming mismatch (short vs long) | ✅ FIXED 2026-05-15 | All 10 seed entries now use long roles (`student-local`, `student-foreign`, `business-jp`, `business-intl`) |
| 2 | `workPermission` missing from seed foreign students | ✅ FIXED 2026-05-15 | Added `workPermission: 'yes'` to s3 (James Wilson) and s4 (Priya Patel) |
| 3 | `calculateMatch()` duplicated in `data.js` + `jobs.js` | ✅ FIXED 2026-05-15 | Removed dead copy from `data.js`; only `jobs.js` version remains |
| 4 | Phantom CSS (~100 lines unreachable) | ❌ PENDING | `.onboarding-overlay`, `.skeleton-*`, `.features-grid`, `.lang-selector` |
| 5 | `visaMatchScore` / `studentTypeMatch` stubs (always 100%) | ❌ PENDING | No-op stubs in `jobs.js:443-445` |

---

> **Document Version:** 5.0 (Phase 2 — Platform Donation & Gratitude System)
> **Prototype Location:** Open `/path/to/jobmatch/index.html` directly in browser
> **Demo Roles:** Japanese Student (Tanaka Yuki) · International Student (James Wilson) · JP Business (Sarah Miller) · Intl Business (Demo Business Co)
> **Total Features Tracked:** 95
> **Completed:** 89 (94%) · Partial: 3 (3%) · Pending: 3 (3%) · Designed: 0 (0%)
