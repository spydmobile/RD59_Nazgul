# RD-59 "Nazgul" As-Built Parts List

**Drone Designator**: RD-59
**Code Name**: Nazgul
**Operator**: SpyD (Franco Nogarin)
**Platform**: Nazgul DC5 ECO V1.1 - 5" Freestyle Quadcopter
**Last Updated**: 2025-12-02

---

## Acquisition History

| Detail | Information |
|--------|-------------|
| **Purchase Date** | July 15, 2025 |
| **Previous Owner** | Devon "Toasty" Felker |
| **Location** | Hay River |
| **Purchase Price** | $273.12 CAD |
| **Original Model** | Nazgul DC5 ECO V1.1 6S HD O4 - ELRS + GPS |
| **Condition at Purchase** | Partial - DJI O4 video system removed, no receiver included |

---

## Current Configuration Status

**Aircraft Status**: ❌ **NOT AIRWORTHY**
**Reason**: Missing receiver and video system
**Test Flights by Current Operator**: None

---

## Component Inventory

### ✓ OPERATIONAL COMPONENTS (As-Purchased July 15, 2025)

#### Airframe

| Component | Specification | Status | Notes |
|-----------|---------------|--------|-------|
| **Frame** | Nazgul DC5 240mm wheelbase | ✓ Operational | DeadCat geometry, carbon fiber |
| **Weight** | ~450g (without battery) | ✓ As spec | Per factory specifications |
| **Dimensions** | 193 × 144 × 34 mm (L×W×H) | ✓ As spec | |

#### Flight Electronics

| Component | Specification | Status | Notes |
|-----------|---------------|--------|-------|
| **Flight Controller** | BLITZ ATF435 | ✓ Operational | Untested by current operator |
| **ESC** | BLITZ E55S 4-in-1 60A | ✓ Operational | Untested by current operator |
| **Motors** | XING-E Pro 2207 1800KV (x4) | ✓ Operational | Untested by current operator |

#### Power System

| Component | Specification | Status | Notes |
|-----------|---------------|--------|-------|
| **Battery Connector** | XT60 | ✓ Operational | Anti-spark technology |
| **Voltage** | 6S (22.2V nominal) | ✓ Compatible | Per original spec |
| **Recommended Battery** | 6S 1480mAh | ✓ Compatible | Factory recommendation |

#### Navigation

| Component | Specification | Status | Notes |
|-----------|---------------|--------|-------|
| **GPS Module** | iFlight GPS | ✓ Operational | Came with aircraft |

#### Propellers

| Component | Specification | Status | Notes |
|-----------|---------------|--------|-------|
| **Factory Props** | Nazgul F5 (5-inch) | ✓ Available | Factory props included |
| **Upgrade Props** | Gemfan 51433 Hurricane Tri-Blade | ✓ Available | Purchased July 17, delivered July 24 |

**Propeller Inventory**:
- Nazgul F5 props (factory, quantity unknown)
- Gemfan 51433 Hurricane (lemon yellow) x4 sets (8 props, 4CW+4CCW) - rear motors
- Gemfan 51433 Hurricane (dark grey) x4 sets (8 props, 4CW+4CCW) - front motors
- **Color scheme rationale**: Dark grey on front motors to stay out of FPV camera view (DeadCat design)

#### Batteries

| Component | Specification | Quantity | Status | Notes |
|-----------|---------------|----------|--------|-------|
| **Flight Batteries** | GNB 1350mAh 6S 100C LiPo XT60 | 4 | ✓ Available | Purchased July 17, delivered July 24 |

**Battery Specifications**:
- **Voltage**: 6S (22.2V nominal, 25.2V full charge)
- **Capacity**: 1350mAh
- **Discharge Rate**: 100C continuous
- **Connector**: XT60 (matches aircraft)
- **Weight**: ~165g each (estimated)
- **Expected Flight Time**:
  - Analog (MOD-002A): 5-7 minutes freestyle
  - HDZero (MOD-002C): 4-6 minutes (better than Walksnail due to lighter weight)

**Battery Selection Rationale (1350mAh vs Factory 1480mAh)**:
- **No Action Camera**: Not adding GoPro/action cam weight (~50-130g saved)
- **HDZero Lighter Than O4**: HDZero Freestyle V2 (~45-50g) vs DJI O4 (~70g) = ~20-25g saved
- **Better Power-to-Weight**: Lighter overall build with smaller battery = more aggressive flight characteristics
- **Flight Time Trade-off**: ~30-60 seconds less than 1480mAh, but better performance for freestyle

---

### 🟡 ADDITIONAL COMPONENTS (On Hand)

#### Analog Video Components (MOD-002A - CONFIRMED PATH)

| Component | Specification | Status | Notes |
|-----------|---------------|--------|-------|
| **VTX** | GEPRC RAD Mini 1W (5.8GHz, 25mW-1W) | ✓ ON HAND (arrived Dec 2, 2025) | Replaces failed TX800 |
| **VTX (Failed)** | SpeedyBee TX800 | ❌ FAILED (bench test Nov 14) | No video output, excessive heat - removed |
| **Camera** | CADDX Ratel 2 (red) | ✓ INSTALLED | Analog FPV camera, mounted in custom TPU V3 bumper |

**Purpose**: FPV capability with maximum flight time (5-7 min) - CONFIRMED as RD-59 video system

**Decision (Dec 2, 2025)**: Analog chosen over digital to maximize flight time for cruiser role

#### Digital Video Components - Path 1: Walksnail (MOD-002B - Optional Upgrade)

| Component | Specification | Status | Notes |
|-----------|---------------|--------|-------|
| **Digital System** | Walksnail Avatar HD Moonlight VTX Kit | ✓ ON HAND (delivered July 24, 2025) | Upgrade only if analog insufficient |
| **Goggles** | Goggles X (already owned) | ✓ OWNED | Considerable investment already made |

**Purpose**: HD video quality, onboard recording - upgrade if analog performance unsatisfactory

#### Digital Video Components - Path 2: HDZero (MOD-002C - REALLOCATED)

| Component | Specification | Status | Notes |
|-----------|---------------|--------|-------|
| **Digital System** | HDZero Freestyle V2 Kit | ➡️ REALLOCATED TO RD-54 | Arrived Dec 2, 2025 - allocated to RD-54 Zorro |
| **Goggles** | HDZero Goggle 2 (red) with Echo Antenna Kit | ✓ ARRIVED | $679.99, ordered Nov 2, 2025 |

**Status Update (Dec 2, 2025)**: HDZero VTX reallocated to RD-54 "Zorro" for HDZero evaluation. RD-59 will use analog (MOD-002A) for maximum flight time.

**Fleet Context**:
- **DJI Mini Pro 4**: Complete setup (Motion, Goggles, screen remote) - cinematic/AP platform
- **Walksnail Fleet**: Goggles X + drones with Avatar VTX
  - RD-55 "Flylens75" (Walksnail Avatar VTX installed)
  - RD-59 "Nazgul" (Walksnail Avatar HD Moonlight available as backup)
- **HDZero Fleet**: HDZero Goggle 2 + HDZero VTX
  - RD-54 "Zorro" (HDZero Freestyle V2 - pending install)

#### Arm LEDs (MOD-003)

| Component | Specification | Status | Notes |
|-----------|---------------|--------|-------|
| **RGB LEDs** | SpeedyBee Programmable 2812 Arm LEDs | ✓ ON HAND (acquired June 4, 2025) | 4 pieces for motor arms |

**Purpose**: Visibility and orientation during flight, aesthetic enhancement

#### GPS Power Module (MOD-004)

| Component | Specification | Status | Notes |
|-----------|---------------|--------|-------|
| **GPS Power** | VIFLY GPS-mate w/ Finder 2 Buzzer | ✓ ON HAND (delivered July 24, 2025) | Powers existing iFlight GPS |

**Purpose**: Clean power for GPS, improved performance, built-in lost model buzzer

---

### ❌ MISSING COMPONENTS (Required for Airworthiness)

#### Radio System

| Component | Status | Parts Status | Required Action |
|-----------|--------|--------------|-----------------|
| **Receiver** | ❌ NOT INSTALLED | ✓ ON HAND (acquired June 4, 2025) | Install HappyModel ELRS EP1 Dual RX |
| **Control Link** | ❌ NONE | Pending installation | ExpressLRS 2.4GHz |

**Parts on Hand (MOD-001)**:
- HappyModel ExpressLRS TCXO EP1 Dual RX
- Dual antennas (included)

#### Video System

| Component | Original Spec | Current Status | Initial Install | Optional Upgrade |
|-----------|---------------|----------------|----------------|------------------|
| **Video System** | DJI O4 Air Unit Pro (Digital HD) | ❌ REMOVED by previous owner | **Analog** (MOD-002A) | Digital (MOD-002B) |
| **Camera** | DJI O4 1/1.3" sensor, 155° FOV | ❌ REMOVED | CADDX Ratel 2 (red) | Walksnail Moonlight |
| **VTX** | DJI O4 (5.170-5.850 GHz, 15km) | ❌ REMOVED | SpeedyBee TX800 (5.8GHz, 25-800mW) | Walksnail Avatar VTX |
| **Recording** | DJI O4 4GB onboard | ❌ REMOVED | None (analog) | HD onboard |

**Installation Strategy: Analog First, Then Choose Digital Path**

**MOD-002A: Analog System (Initial Install - Already Owned)**
- SpeedyBee TX800 VTX (5.8GHz, 25-800mW) - liberated from 3.5" build
- CADDX Ratel 2 camera (red) - already owned
- VTX antenna (included with TX800)
- **Flight Time**: 5-7 min (40-50% better than digital)
- **Weight**: +25g (45g lighter than digital)
- **Range**: 2-4km at 800mW

**MOD-002B: Walksnail Digital System (Optional Path 1 - On Hand)**
- Walksnail Avatar HD Moonlight VTX Kit (delivered July 24, 2025)
- Moonlight camera (included in kit)
- VTX module (included in kit)
- Antennas (included in kit)
- Goggles X (already owned)
- **Flight Time**: 3-5 min (40-50% penalty vs analog)
- **Weight**: +70g (45g heavier than analog)
- **Range**: 3-6km (slightly better)
- **Benefits**: HD video quality, onboard HD recording, existing goggles investment

**MOD-002C: HDZero Digital System (Optional Path 2 - In Transit)**
- HDZero Freestyle V2 Kit (ordered Nov 2, expected ~Nov 9-15)
- HDZero camera (included in kit)
- HDZero VTX (included in kit)
- HDZero Goggle 2 (red) with Echo Antenna Kit (ordered Nov 2, $679.99)
- **Flight Time**: 3-5 min (similar to Walksnail)
- **Weight**: Similar to Walksnail (~+45-70g vs analog)
- **Range**: 3-6km (estimated, similar to Walksnail)
- **Benefits**: Lower latency than Walksnail, HD recording, evaluating HDZero ecosystem

**Decision**: Install analog first (MOD-002A), test performance, choose between Walksnail (MOD-002B) or HDZero (MOD-002C) only if needed

**Original Video System Specifications** (for reference):
- **Sensor**: 1/1.3-inch
- **Resolution**: 4K@30fps, 1080p@100fps
- **FOV**: 155° ultra-wide
- **Stabilization**: RockSteady 3.0+
- **Range**: Up to 15 km (FCC)
- **Recording**: 4GB built-in memory

---

## Build Specifications

### Performance Specifications (Factory)

| Specification | Value |
|--------------|-------|
| **Max Speed** | 190 km/h |
| **Max Hover Time** | ~7.5 minutes (with 6S 1480mAh) |
| **Max Flight Altitude** | 7000 m |
| **Wind Resistance** | Up to level 7 |
| **Operating Temperature** | -10 °C to 40 °C |

### Weight Budget

| Category | Weight |
|----------|--------|
| **Dry Weight** | ~450g ± 5g (without battery) |
| **With 6S 1480mAh Battery** | ~675g ± 5g |
| **Current Configuration** | ~450g (no video system, no receiver) |

---

## Pending Installations

### Phase 1: Critical Airworthiness (Install First)

**Objective**: Install RX + Analog VTX → Get aircraft flying with maximum flight time

| Item | Status | Parts On Hand Since | Notes |
|------|--------|-------------------|-------|
| **MOD-001: ELRS Receiver** | 🟢 INSTALLED | June 4, 2025 | HappyModel EP1 Dual RX - installed Nov 13, needs binding |
| **MOD-002A: Analog Video System** | ✓ Parts ready | Dec 2, 2025 | GEPRC RAD Mini 1W + Ratel 2 (installed) - CONFIRMED PATH |

**Expected Performance (Phase 1)**:
- Flight time: 5-7 minutes
- Range: 2-4km at 1W
- Weight penalty: +25g (minimal)

### Phase 1B: Optional Digital Upgrade (Walksnail Backup)

**Objective**: Upgrade to Walksnail digital if analog performance unsatisfactory

| Item | Status | Parts On Hand Since | Notes |
|------|--------|-------------------|-------|
| **MOD-002B: Walksnail Avatar HD** | ✓ Parts on hand | July 24, 2025 | Backup option: Use existing Goggles X investment |
| **MOD-002C: HDZero Freestyle V2** | ➡️ REALLOCATED | Dec 2, 2025 | Allocated to RD-54 Zorro |

**Decision (Dec 2, 2025)**: HDZero VTX allocated to RD-54 "Zorro" for HDZero ecosystem evaluation. RD-59 confirmed for analog (MOD-002A) with Walksnail as backup only.

**If Analog Insufficient - Walksnail (MOD-002B)**:
- Flight time penalty: 3-5 min (vs 5-7 min analog)
- Weight penalty: +45g heavier than analog
- Benefits: HD video, onboard recording, uses Goggles X

### Phase 2: Optional Enhancements (Install After Flying)

**Objective**: Add enhancements after baseline performance established

| Item | Status | Parts On Hand Since | Notes |
|------|--------|-------------------|-------|
| **MOD-003: RGB Arm LEDs** | ✓ Parts on hand | June 4, 2025 | SpeedyBee 2812 LEDs x4 |
| **MOD-004: GPS-mate Power Module** | ✓ Parts on hand | July 24, 2025 | VIFLY GPS-mate w/ Finder 2 buzzer |

**Installation Plan**: Phase 1 (RX + Analog) → Test flights → Evaluate if digital upgrade needed → Phase 2 enhancements

**Additional Equipment On Hand** (not currently planned for installation):
- **SpeedyBee F7 50A V3 Combo Stack** (delivered July 24, 2025)
  - Future upgrade option for FC/ESC replacement
  - Current BLITZ stack to be evaluated during test flights first
  - See `RD-59_Modifications_Log.md` for details

---

## Known Issues

| Issue | Severity | Impact | Resolution | Status |
|-------|----------|--------|------------|--------|
| No receiver installed | CRITICAL | Aircraft not controllable | Install HappyModel ELRS EP1 Dual RX (MOD-001) | Parts on hand |
| No video system | CRITICAL | No FPV capability | Install Walksnail Avatar HD (MOD-002) | Parts on hand |
| Not test flown by operator | INFO | Unknown operational baseline | Complete installations, then test flight | Pending MOD-001/002 |

**Status Update**: All critical parts are on hand as of July 24, 2025. Aircraft is ready for installation work to begin.

---

## Modification History

**Completed Modifications**:
- **MOD-001**: ELRS Receiver Installation - 🟢 INSTALLED Nov 13, 2025 (needs binding/config)

**In Progress**:
- **MOD-002A**: Analog Video System - Camera installed, GEPRC RAD ready to install (replaces failed TX800)

**Pending Modifications**:
- **MOD-002B**: Walksnail Avatar HD (parts delivered July 24, 2025) ✓ On hand - Backup if analog insufficient
- **MOD-002C**: HDZero Freestyle V2 - ➡️ REALLOCATED to RD-54 Zorro (Dec 2, 2025)
- **MOD-003**: RGB Arm LED Installation (parts acquired June 4, 2025) ✓ On hand
- **MOD-004**: VIFLY GPS-mate Power Module Installation (parts delivered July 24, 2025) ✓ On hand

See `RD-59_Modifications_Log.md` for complete modification details and installation checklists.

---

## Reference Documents

- **Factory Specifications**: `reference/Nazgul_DC5_ECO_Factory_Specs.md`
- **Google Photos Album**: [RD-59 Photo Gallery](https://photos.google.com/album/AF1QipMQ81SgmNKcywQYFzFxxncO6l4DfiegxZddzp05)
- **Local Photos**: `/Users/franconogarin/localcode/spyd.com/public/drone-lab/drones/RD-59/googlePhotos/`
- **Incident Log**: `RD-59_Incident_Log.md`
- **Modifications Log**: `RD-59_Modifications_Log.md`
- **Timeline**: `RD-59_Build_Timeline.md`

---

## Notes

**Important Reminders**:
- This aircraft was purchased as a partial build with critical systems removed
- DJI O4 system was factory-installed but removed by previous owner before sale
- Receiver was never included (not part of factory package)
- All flight electronics (FC, ESC, motors) are untested by current operator
- First test flight will establish operational baseline

**Next Steps**:
1. ✅ ~~Select and purchase receiver system~~ - **COMPLETE** (HappyModel ELRS EP1 Dual RX on hand)
2. ✅ ~~Select and purchase video system~~ - **COMPLETE** (Walksnail Avatar HD Moonlight on hand)

**PHASE 1: GET IT FLYING**
3. **Install and configure receiver** (MOD-001) - See installation checklist in Modifications Log
4. **Install and configure video system** (MOD-002) - See installation checklist in Modifications Log
5. **Perform bench testing** - Verify receiver and video operational
6. **Perform test flights and establish baseline** - First flights with current BLITZ stack
7. **Evaluate performance** - Assess BLITZ stack performance

**PHASE 2: ENHANCEMENTS (After flying)**
8. *Optional*: Install RGB LEDs (MOD-003)
9. *Optional*: Install GPS-mate (MOD-004)
10. *If needed*: Evaluate if SpeedyBee stack upgrade warranted
