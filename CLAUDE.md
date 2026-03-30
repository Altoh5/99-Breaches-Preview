# Memory

## Me
Alvin Toh (toh.alvin@gmail.com). Working on the 99-Breaches-Preview web app — an educational lead-magnet microsite for DPEX Network / Straits Interactive promoting the book "99 Privacy Breaches to Beware Of."

## Project
| Key | Value |
|-----|-------|
| **Repo** | github.com/Altoh5/99-Breaches-Preview |
| **Live site** | altoh5.github.io/99-Breaches-Preview/ |
| **Stack** | Static HTML + Tailwind CSS + vanilla JS (no build tools) |
| **Main file** | `app.html` (the full web app, ~1680 lines) |
| **Landing** | `index.html` (overview/entry page) |
| **Local dev** | `python3 -m http.server 8099` |
| **Deploy** | GitHub Pages (push to `main` branch) |

## Terms
| Term | Meaning |
|------|---------|
| DPMP | Data Protection Management Programme — the framework the book supports |
| DPO | Data Protection Officer — the target audience |
| DPOinBOX | DPEX Network's SaaS platform for DPMP compliance |
| DPEX Network | Data Protection Excellence Network (Straits Interactive brand) |
| PDPA | Personal Data Protection Act (Singapore) |
| DPTM | Data Protection Trust Mark (Singapore certification) |
| GAPSR | Govern, Assess, Protect, Sustain, Respond — the Privacy Operational Life Cycle |
| MAC Framework | Monitor, Audit, Communicate — 3-part DPMP video series |
| GHL | GrowthWorks / LeadConnector HQ — lead capture form provider |
| PbD | Privacy by Design |

## Architecture
| Component | Details |
|-----------|---------|
| **Sidebar** | 2 special nav buttons (About Book, DPMP Resources) + 8 section buttons (A–H) rendered from `bookData` |
| **Content** | Dynamic rendering via `selectSection()` → `renderAboutBook()`, `renderDPMPResources()`, or `renderChapters()` |
| **Data** | `aboutBookData` (book metadata), `dpmpVideoData` (30 videos in 8 DPMP categories), `bookData` (8 sections, 17 chapters) |
| **Gating** | First 2 chapters per section free; rest gated behind GHL lead form; `?unlocked=1` URL param bypasses |
| **Videos** | YouTube embeds via `youtube-nocookie.com`; existing chapter videos + new DPMP Resources page |
| **Cross-links** | Each chapter has `relatedDPMP` array linking to relevant DPMP videos via `getDPMPVideo()` + `renderRelatedDPMP()` |

## DPMP Video Resources (added Mar 2026)
29 curated videos from the DPOinBOX Academy playlist + DPEX Network channel, structured around the **Privacy Operational Life Cycle (GAPSR)**:
1. **Govern** — Programme Governance & DPO Appointment (7 videos)
2. **Assess** — Data Inventory, Process Mapping & Risk Assessment (6 videos)
3. **Protect** — Policies, Controls, Training & Third-Party Management (8 videos)
4. **Sustain** — Monitor, Audit & Communicate / MAC Framework (4 videos)
5. **Respond** — Breach Management & Incident Response (4 videos)

Reference: Thailand Demo Toolkit v2a.pptx (Privacy Operational Life Cycle diagram)

Source playlists:
- youtube.com/@dpexnetwork
- youtube.com/playlist?list=PLeFbwfnrYD4qbvcEmHRTj0_Z4betys6BC

## Design
| Element | Value |
|---------|-------|
| **Theme** | Dark (bg `#0f1117`, cards `#1a1d27`) |
| **Brand color** | Orange `#E8631A` |
| **Fonts** | Fraunces (display), Plus Jakarta Sans (body), IBM Plex Mono (labels) |
| **Style** | Glassmorphism, subtle dot grid bg, grain texture overlay |

## Git Notes
- The `.git/index.lock` file can get stuck due to sandbox permissions — delete it manually if git operations fail
- Sandbox cannot `git push` (no GitHub auth) — push must be done from Alvin's local terminal

## Pending / Next
- Push latest commit to GitHub (DPMP Resources addition)
- LinkedIn Insight Tag integration (noted in README)
- Google Analytics + Meta Pixel setup (noted in README)
