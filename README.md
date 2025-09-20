# THGnLR: An Intelligent Application for Automated, Large-Scale Multimodal Human Audio-Video Data Acquisition and Auto-Cleansing
**An Intelligent Application for Automated, Large-Scale Multimodal Human Audio–Video Data Acquisition and Auto-Cleansing**  

> ⚠️ **Status:** Pre-publication. This repo is intentionally code-free. The code exists; it’s currently enjoying a relaxing spa day before camera-ready. Academic collaborations welcome—see **Partner With Us**.

---

## TL;DR
THGnLR turns messy, real-world human AV recordings into **high-trust, audit-ready datasets**. It guides capture, auto-cleans through layered intelligence (pose/blur/exposure, VAD/SNR, identity, lip-sync, de-dup), and exports self-describing bundles (JSON manifests, checksums, consent hooks) that run **offline-first** on commodity desktops. Result: **less reviewer strain**, **fewer duplicates**, **cleaner data**, **happier models**.

---

## Why this exists
Modern AV systems (talking-head generation, visual speech recognition, meeting analytics) thrive on **quality**, not just quantity. Classrooms and labs bring variable webcams, acoustics, lighting, and connectivity—plus governance requirements such as consent, revocation, and audit trails. THGnLR applies **computational intelligence at intake** to:
- standardize recordings (codec/fps/audio rate, naming schema);
- auto-clean with explainable gates;
- prevent split leakage via de-duplication;
- package outputs with **manifests + checksums + reason codes**.

> If documentation is your love language, you’ll appreciate the self-describing exports and optional Datasheet/Model Card add‑ons.

---

## What it does (high level)
- **Guided Capture** — Calibrate → Record → Validate, with consent + device/environment metadata.
- **Auto-Cleansing Gates**  
  1) Structural integrity (container/CFR/duration)  
  2) Visual quality & pose (blur, illumination, frontalness, occlusions)  
  3) Speech presence & audio integrity (VAD, SNR, clipping)  
  4) Identity consistency (face + speaker)  
  5) Lip-sync & AV alignment (offset in ms)  
  6) De-duplication (frame-hash + sequence similarity)
- **Confidence-Gated Decisions** — Accept / Review / Reject, with reasoned feedback for targeted re-capture.
- **Governance-Ready Exports** — Clean media + JSON sidecars + checksums, with consent revocation propagation and train/val/test split control.
- **Offline-First** — Works in labs/classrooms without reliable internet.

---

## Architecture (ASCII snack)
```
Capture UI ─▶ Standardize ─▶ Intelligence Gates ─▶ Decision
                                 │                     ├─▶ Accept → Package & Version → Exports
                                 ├─▶ De-dup            ├─▶ Review  → Fast human triage
                                 └─▶ Reports           └─▶ Reject  → Re-capture (with reason)
```

---

## What’s in this repo (and what isn’t)
- ✅ **Design overview** (this README), evaluation plan, example manifest schema, figure(s).
- ✅ **How to cite** (template below; `CITATION.cff` planned on pre-print release).
- ❌ **Source code** (on purpose). Demo builds are shared privately with partners.

---

## Partner With Us (academia & research)
Seeking department-scale pilots, thesis-friendly datasets, and joint studies.

**Ideal collaborators**
- Speech/vision labs needing **consent-aware**, **offline-capable** intake.
- Programs that care about **revocation** and **auditability**.
- Groups tired of **duplicates** sneaking into train/val/test.

**You get**
- Demo builds + config profiles,
- Evaluation recipes (gate-level P/R/F1, sync error, dedup efficacy, throughput, reviewer minutes/hour),
- Potential **co‑authorship** on the AICDAKD 2025 paper (publication in flight),
- Office hours (puns included at no extra charge).

**Say hi:** open a GitHub **Discussion** titled “Partnership request” (template below), or email `vineet@vecc.gov.in`.  

**Discussion template**
```
Institution: 
Contact(s): 
Use case (THG, lipreading, cohort mgmt, other): 
Timeline: 
Data governance constraints (if any):
```

---

## Roadmap (selected)
- Adaptive thresholding from reviewer feedback.
- Hybrid VAD (fast front‑end + neural refinement).
- Stronger no‑reference quality metrics.
- Auto‑generated **Datasheets** per export; optional **Model Cards** for embedded verifiers.

---

## Citing this work (pre‑print forthcoming)
Until a DOI is available, please cite:
```bibtex
@misc{thgnlr2025,
  title  = {THGnLR: An Intelligent Application for Automated, Large-Scale Multimodal Human Audio–Video Data Acquisition and Auto-Cleansing},
  note   = {pre-publication},
  year   = {2025},
  author = {THGnLR Team}
}
```
When the pre‑print is live, the repo will include a `CITATION.cff` so GitHub can render a one‑click citation panel.

---

## Contributing (docs & discussions)
- Open **Issues** for clarifications/typos.
- Use **Discussions** for partnerships and Q&A (enable categories like “Partnerships,” “Q&A,” “Show & Tell”).
- This repo adopts the **Contributor Covenant v2.1**—be excellent to each other. See `CODE_OF_CONDUCT.md` (or link the canonical text).

---

## License
Documentation in this repository is shared under **CC‑BY‑4.0** (or **CC‑BY‑NC‑4.0**, per institutional policy). Demo binaries and source code, when shared privately with partners, carry separate terms.

---

## Disclaimer
THGnLR handles **human** AV data. Deployments must follow applicable laws and institutional policies. Use consent forms, honor revocations, and attach documentation (manifests, datasheets) to any data redistributed from this work.

---

## Appendix: housekeeping kit (optional)
- Add `CITATION.cff` for clean, machine‑readable citations.
- Add `CODE_OF_CONDUCT.md` (Contributor Covenant v2.1).
- Add `SECURITY.md` and `GOVERNANCE.md` for intake deployments.
- Pin a “Partnerships” category in **Discussions** for inbound collabs.
