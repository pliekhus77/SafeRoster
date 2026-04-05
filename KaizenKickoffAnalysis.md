# SafeRoster — Kaizen Analysis

**5 Whys, Launch Blockers & 90-Day Roadmap**

**Prepared by:** Patrick
**Role:** Founder / Builder
**Framework:** Kaizen / 5 Whys
**Date:** April 4, 2026

---

## Section 1 — 5 Whys root cause analysis

Three independent root cause chains were run — each targeting a distinct reason the project has not launched. All three must be resolved for SafeRoster to reach a live pilot trip.

---

### 5 Whys #1 — Project has no accountable owner

> **Problem statement:** SafeRoster exists as a well-documented concept but has not yet been built.

| | Why | Answer |
|---|---|---|
| W1 | Why hasn't the project been started? | No one has committed to being the accountable owner — the project exists as a shared idea without a named decision-maker who controls timeline and scope. |
| W2 | Why is there no accountable owner? | The roles of funder, product owner, and technical lead have not been assigned to specific people — the concept document describes what the app should do, not who is responsible for making it real. |
| W3 | Why haven't roles been assigned? | No stakeholder has been asked to commit resources — budget, developer time, or legal review hours — because the business case hasn't been formally presented to anyone with authority to approve it. |
| W4 | Why hasn't the business case been presented? | The concept document focuses on features and technology, not on revenue model, target customer, or total addressable market — the commercial case is unproven and unwritten. |
| **W5** | **Why is the commercial case unwritten?** | **The project originated as a solution-first idea — the problem was well understood, but the question "who pays for this, how much, and why now" was never addressed in the founding documents.** |

> **Root cause:** SafeRoster is solution-first, not business-first. There is no named buyer, no validated willingness to pay, and no owner with budget authority — so the project cannot formally start.

> **Countermeasure:** Write a one-page business case naming the buyer (K–12 school districts), a price hypothesis, and identify one sponsor with budget authority to approve a pilot. Only then assign a product owner.

---

### 5 Whys #2 — Legal/privacy compliance is causing paralysis

> **Problem statement:** COPPA/FERPA and biometric consent requirements are creating perceived paralysis around building anything.

| | Why | Answer |
|---|---|---|
| W1 | Why is the legal/privacy layer causing paralysis? | The team feels they cannot write a single line of production code until the compliance framework is resolved, treating it as a blocker rather than a constraint to design around. |
| W2 | Why is compliance treated as a binary blocker? | No one has scoped which features require legal sign-off before launch vs. which can be built and compliance-reviewed in parallel — the entire feature set feels legally frozen. |
| W3 | Why hasn't this scoping been done? | There is no privacy attorney or compliance advisor formally attached to the project — legal questions get asked informally and answered incompletely, which amplifies uncertainty. |
| W4 | Why is there no compliance advisor attached? | Engaging legal counsel was implicitly deferred until the MVP was "far enough along" — but that bar is undefined, creating a chicken-and-egg standstill. |
| **W5** | **Why was legal deferred?** | **The project plan has no explicit compliance milestone — there is no date by which a privacy framework must exist, so it keeps getting deferred in favour of product decisions that feel more tangible.** |

> **Root cause:** No compliance milestone exists on the project roadmap. Legal review is treated as something that happens after building, not alongside it — which is backwards for an app handling minors' biometric and location data.

> **Countermeasure:** Add "compliance framework complete" as a Week 4 milestone. Split the feature set into three tiers: build freely / build but review before data touches it / do not build yet. Engage a COPPA/FERPA specialist for a fixed-scope review.

---

### 5 Whys #3 — No validated pilot partner

> **Problem statement:** There is no school, tour operator, or organization committed to piloting SafeRoster on a real trip.

| | Why | Answer |
|---|---|---|
| W1 | Why is there no pilot partner? | No one has asked a real potential customer to pilot it — the concept has been developed entirely without customer discovery conversations. |
| W2 | Why have there been no customer discovery conversations? | The team assumes the product must be built before it can be shown to potential users — but a clickable prototype or even a slide deck is enough to validate interest. |
| W3 | Why does the team think the product must exist first? | There is no sales or go-to-market owner on the team — the people working on the concept are builders, not sellers, and customer conversations feel outside their role. |
| W4 | Why is there no go-to-market owner? | The founding team composition was never formally decided — it defaulted to whoever was interested in the product concept, which skews technical. |
| **W5** | **Why was team composition never decided?** | **The project was framed as a product design exercise, not a venture — so the question "who sells this?" was never asked as part of the founding process.** |

> **Root cause:** SafeRoster was designed as a product, not launched as a venture. No one on the founding team owns customer acquisition, so there is no pipeline of pilot partners and no feedback loop from real users.

> **Countermeasure:** Identify one person whose explicit job is to run 10 discovery interviews with school trip coordinators within 30 days — before a single line of production code is written. Target: one signed letter of intent from a pilot partner.

---

## Section 2 — Launch blockers

Everything that must be resolved before SafeRoster can run a real pilot trip. Sorted by dependency order — items at the top must clear before items below can start.

### Must clear before anything else

| # | Blocker | What it means | Status |
|---|---|---|---|
| 1 | Named product owner with budget authority | Someone must own scope, timeline, and spend decisions. Without this, every other blocker has no one to resolve it. | 🔴 Blocking |
| 2 | One-page business case with revenue hypothesis | Defines the buyer, the price model, and the TAM. Required before any investor or institutional sponsor will engage. | 🔴 Blocking |
| 3 | Compliance framework (COPPA/FERPA/biometric) | Must know which features require legal sign-off before any minor's data is collected. Fixed-scope review with a specialist. | 🔴 Blocking |

### Must clear before pilot

| # | Blocker | What it means | Status |
|---|---|---|---|
| 4 | Signed letter of intent from one pilot partner | A real school committed to a specific trip date. Drives the MVP scope ceiling. | 🟡 Pre-pilot |
| 5 | AI facial recognition vendor selected | On-device (Apple Vision / ML Kit) vs. cloud (AWS Rekognition). Decision affects data residency, offline capability, and cost model. | 🟡 Pre-pilot |
| 6 | Parental consent and data deletion workflow | Cannot collect a single minor's photo or GPS coordinate without this. Must include post-trip auto-purge. | 🟡 Pre-pilot |
| 7 | Check-in SLA and notification stack tested | Critical-priority notification channel must bypass Do Not Disturb. Must be load-tested at full group size before a live trip. | 🟡 Pre-pilot |

### Nice to have — not blocking

| # | Blocker | What it means | Status |
|---|---|---|---|
| 8 | Parent/guardian view-only portal | Valuable for adoption, not safety-critical for the pilot. Build in cycle 2. | 🟢 Deferred |
| 9 | Gamification / badges for on-time check-ins | Engagement feature. Validate core check-in compliance first. | 🟢 Deferred |

---

## Section 3 — PDCA cycle

Iterative improvement cycle mapped to SafeRoster features and pilot operations. Recommended cadence: one cycle per feature increment or per trip pilot cohort, whichever comes first.

### Plan
- Define check-in completion SLA (target ≥ 95%)
- Map notification failure modes by device OS
- Identify AI false-negative rate baseline
- Set COPPA/FERPA compliance checklist
- Select pilot school group (n ≈ 30 travelers)

### Do
- Implement critical-priority notification channel
- Deploy AI recognition with demographic calibration
- Run single-day field trip pilot with live chaperones
- Log every check-in attempt, success, and failure
- Collect in-app feedback from travelers and chaperones

### Check
- Measure actual check-in completion vs 95% SLA
- Review AI match accuracy by photo quality / lighting
- Analyse latency on chaperone dashboard refreshes
- Audit GPS coordinate accuracy vs known waypoints
- Review consent workflow completion rate

### Act
- Standardise critical notification as default for all trips
- Expand AI training set if accuracy < 90%
- Escalate unresolved issues to next sprint backlog
- Update privacy policy if consent flow changes
- Re-run cycle for next feature increment

---

## Section 4 — Value stream map

Check-in value stream from trip setup to verified attendance. Steps marked as waste candidates are priority improvement targets.

### Setup flow (pre-trip)

| Step | Owner | Note |
|---|---|---|
| Create trip | Admin | |
| Import roster | Admin | |
| ⚠️ Manual photo review | Admin | **Waste** — candidate for auto-quality scoring |
| Consent sent | Parent / guardian | |
| Profile confirmed | System | |

### Live check-in flow (during trip)

| Step | Note |
|---|---|
| Prompt fires (scheduled) | |
| Traveler notified (push) | |
| ⚠️ Wait for group to assemble | **Waste** — group assembly delay |
| Group selfie submitted (GPS tagged) | |
| AI recognition (on-device / cloud) | |
| ⚠️ Chaperone manually confirms | **Waste** — over-processing when AI confidence is high |
| Roster updated (real-time) | |

### Waste reduction targets

| Waste | Countermeasure |
|---|---|
| Manual photo review | Auto-quality scoring on upload — reject blurry images before they enter the recognition queue. |
| Group assembly wait | Staggered check-in windows: traveler has 15 minutes to find 2 other group members rather than waiting for the full group. |
| Chaperone manual confirmation | Auto-approve when AI confidence ≥ 95%. Flag for manual review only when confidence falls below threshold. |
| Late detection of missed check-ins | Proactive alert to chaperone at T−5 min before window closes, not after. |

---

## Section 5 — Improvement priority matrix

Improvement items ranked by safety impact and implementation effort. Address high-impact / low-effort items first.

| Improvement item | Impact | Effort | Priority |
|---|---|---|---|
| Critical-priority notification channel (bypass DND) | Safety | Low | 🔴 Do now |
| Auto-alert chaperone 5 min before check-in window closes | Safety | Low | 🔴 Do now |
| Define check-in SLA in product requirements | Process | Low | 🔴 Do now |
| AI confidence threshold: auto-approve ≥ 95% matches | Efficiency | Medium | 🟡 Plan next |
| Photo quality scorer on upload | Accuracy | Medium | 🟡 Plan next |
| Demographic calibration of AI recognition model | Safety / Equity | High | 🟡 Plan next |
| Parental consent automation (digital signature) | Compliance | Medium | 🟡 Plan next |
| Offline fallback check-in (SMS/QR) when connectivity lost | Safety | High | 🟢 Backlog |
| Chaperone dashboard real-time performance optimisation | Usability | High | 🟢 Backlog |
| Post-trip automated data erasure pipeline | Compliance | Medium | 🟢 Backlog |

---

## Section 6 — First 90-day roadmap

Milestone sequence from concept to live pilot trip. Each milestone has a binary outcome — it either happened or it didn't.

| Timeline | Milestone | Success criteria | Phase |
|---|---|---|---|
| Wk 1–2 | Name the product owner and write the business case | One named person owns the project. Business case has buyer, price hypothesis, and TAM estimate. | Foundation |
| Wk 2–4 | Run 10 discovery interviews | Confirmed pain, confirmed willingness to pay, and one warm lead for a pilot partner. | Validate |
| Wk 3–4 | Compliance framework complete | Feature tiers assigned: build freely / build with review / hold. COPPA/biometric scope reviewed by specialist. | Legal |
| Wk 4–6 | Clickable prototype built and shown to pilot lead | Figma or low-code prototype covers check-in flow, chaperone dashboard, and consent screen. | Validate |
| Wk 5–6 | Letter of intent signed with pilot partner | Named org, named trip date (≥ 8 weeks out), named group size. Defines MVP scope ceiling. | Commitment |
| Wk 6–10 | MVP built: check-in, AI, GPS, chaperone dashboard | Core safety loop only. Consent workflow, critical notification, post-trip data purge included. | Build |
| Wk 10–11 | Internal load test and compliance review | Simulate 40-person trip. Notification delivery ≥ 95%. Legal confirms consent flow meets COPPA. | QA |
| Wk 12 | Live pilot trip | Real group, real trip, real chaperones. Measure check-in rate, AI accuracy, chaperone satisfaction. | Launch |

---

## Section 7 — Early decisions requiring an owner and a deadline

These five decisions, if deferred, will stall the project. Each needs a named owner and a decision date — not just an answer.

| Decision | Recommended answer | Rationale |
|---|---|---|
| Who is the primary buyer? | K–12 school districts (first) | Schools have clear duty-of-care liability and trip budgets. Tour operators move faster but have smaller groups. Serving both in v1 fractures MVP scope. |
| On-device or cloud AI recognition? | On-device for MVP | Avoids cloud data residency issues for minors' biometrics, works offline, ships faster. Cloud unlocks 1:N matching at scale — defer until compliance framework and group sizes justify it. |
| What is the revenue model? | Per-trip fee, convert to annual | Per-trip ($49) lowers the commitment barrier for first-time buyers. Convert to district annual ($2,400/yr) after the third trip purchase at a school. |
| Native or cross-platform? | React Native for MVP | Native (Swift/Kotlin) is preferred for camera and GPS but doubles the build team required. React Native ships faster; the performance delta matters less at pilot scale. |
| What is the MVP scope ceiling? | Five features, defined by pilot trip date | Check-in with group photo, AI recognition, GPS tag, chaperone dashboard, critical alert. The pilot partner's trip date is the hard deadline that enforces scope discipline. |

---

*SafeRoster Kaizen Analysis — Prepared by Patrick — April 2026*
