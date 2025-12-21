# Project Plan: RD59 Nazgul

**Project:** RD59_Nazgul
**Owner:** Circuit (Fleet Steward)
**Created:** December 21, 2025
**Status:** Not Airworthy (Missing Critical Systems)

---

## Overview

RD59 "Nazgul" is a 5" freestyle quad acquired as a partial build. The DJI O4 video system was removed by the previous owner, and no receiver was ever installed. Critical systems pending installation.

**Repository:** `spydmobile/RD59_Nazgul`
**Location:** `projects/drone_management/drones/RD59_Nazgul/`
**Platform:** 5" Freestyle (iFlight Nazgul DC5 ECO V1.1)

---

## Current State

| Attribute | Value |
|-----------|-------|
| **Airworthiness** | NOT AIRWORTHY |
| **Acquisition Date** | July 15, 2025 |
| **Days Since Acquisition** | 159 days |
| **Previous Owner** | Devon "Toasty" Felker |
| **Flight Hours (Current Owner)** | 0.0 |
| **Video System** | REMOVED (was DJI O4) |
| **Control Link** | NOT INSTALLED |

**Operational Components:**
- Frame (Nazgul DC5 240mm DeadCat)
- FC (BLITZ ATF435 - untested)
- ESC (BLITZ E55S 4-in-1 60A - untested)
- Motors (XING-E Pro 2207 1800KV x4 - untested)
- GPS (iFlight - operational)
- Props (Nazgul F5)

**Missing Components:**
- Receiver (never included)
- Video system (stripped by previous owner)

---

## Milestones

### Milestone 1: Acquisition (COMPLETE)
**Status:** Complete | **Date:** July 15, 2025

- [x] Purchased from Devon Felker
- [x] Documented as-received condition
- [x] Created documentation structure
- [x] Photographed aircraft

### Milestone 2: Phase 1 Parts (COMPLETE)
**Status:** Complete | **Date:** July 24, 2025

Parts on hand, installation pending.

- [x] Order ELRS receiver (HappyModel EP1 Dual)
- [x] Order analog VTX (SpeedyBee TX800)
- [x] Order analog camera (CADDX Ratel 2)
- [x] Parts received

### Milestone 3: Phase 1 Installation (PENDING)
**Status:** Pending | **Priority:** CRITICAL

Get aircraft flying with analog video for maximum flight time.

- [ ] Install HappyModel ELRS EP1 Dual receiver (MOD-001)
- [ ] Install SpeedyBee TX800 VTX (MOD-002A)
- [ ] Install CADDX Ratel 2 camera
- [ ] Route antennas
- [ ] Configure Betaflight
- [ ] Bind ELRS receiver
- [ ] Bench test all systems
- [ ] First hover test
- [ ] Maiden FPV flight

### Milestone 4: Phase 1B Digital Upgrade (OPTIONAL)
**Status:** Optional | **Priority:** Low

Only if analog insufficient after test flights.

- [ ] Evaluate analog performance
- [ ] Decision: Keep analog or upgrade?
- [ ] If upgrade: Install Walksnail Avatar HD Moonlight (MOD-002B)
- [ ] Note: Digital reduces flight time (5-7 min → 3-5 min)

### Milestone 5: Phase 2 Enhancements (PENDING)
**Status:** Pending | **Priority:** Low

Install after test flights prove platform viability.

- [ ] Install SpeedyBee RGB LEDs (MOD-003)
- [ ] Install VIFLY GPS-mate with Finder 2 (MOD-004)

---

## GitHub Issues

| # | Title | Labels | Priority |
|---|-------|--------|----------|
| 1 | Install HappyModel ELRS EP1 Dual RX receiver | pending-install, radio-system | CRITICAL |
| 2 | Select and install replacement FPV video system | enhancement, video-system | CRITICAL |

---

## Current Tasks

| Task | Priority | Status |
|------|----------|--------|
| Install ELRS receiver | CRITICAL | Parts in hand |
| Install analog VTX/camera | CRITICAL | Parts in hand |
| Betaflight configuration | High | After installation |
| First flight test | High | After config |
| Evaluate analog performance | Medium | After flights |

---

## Installation Strategy

**Phase 1: Minimum Viable Aircraft**
1. Install receiver (ELRS EP1 Dual) - control link
2. Install analog VTX (TX800) + camera (Ratel 2) - video link
3. Get flying, evaluate performance

**Why Analog First:**
- Longer flight time (5-7 min vs 3-5 min with digital)
- Lower power consumption
- Parts already on hand
- Can upgrade later if needed

**Phase 1B Decision Point:**
After 5-10 test flights, evaluate:
- Is analog video quality acceptable?
- Is 5-7 min flight time sufficient?
- If no: upgrade to Walksnail (MOD-002B)

---

## Operations

**Documentation:**
- Parts List: `Documentation/RD-59_AsBuilt_Parts_List.md`
- Timeline: `Documentation/RD-59_Build_Timeline.md`
- Modifications: `Documentation/RD-59_Modifications_Log.md`
- Installation Guide: `Documentation/RD-59_Phase1_Installation_Guide.md`

**Pre-acquisition history:**
- Previous owner flight history: Unknown
- Previous incidents: Unknown
- All electronics untested by current operator

---

*Circuit - Fleet Steward*
