# RD-59 "Nazgul" As-Built Parts List

**Drone Designator**: RD-59
**Code Name**: Nazgul
**Operator**: SpyD (Franco Nogarin)
**Platform**: Nazgul DC5 ECO V1.1 - 5" Freestyle Quadcopter
**Last Updated**: 2025-11-10

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
- **Expected Flight Time**: 5-7 minutes freestyle (estimated)

---

### 🟡 ENHANCEMENT COMPONENTS (On Hand, Awaiting Installation)

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

| Component | Original Spec | Current Status | Parts Status | Required Action |
|-----------|---------------|----------------|--------------|-----------------|
| **Video System** | DJI O4 Air Unit Pro | ❌ REMOVED by previous owner | ✓ ON HAND (delivered July 24, 2025) | Install Walksnail Avatar HD Moonlight |
| **Camera** | DJI O4 camera (1/1.3" sensor) | ❌ REMOVED by previous owner | ✓ ON HAND | Install Walksnail Moonlight camera |
| **VTX** | DJI O4 (5.170-5.850 GHz) | ❌ REMOVED by previous owner | ✓ ON HAND | Install Walksnail Avatar VTX |

**Parts on Hand (MOD-002)**:
- Walksnail Avatar HD Moonlight VTX Kit (complete)
- Moonlight camera (included in kit)
- VTX module (included in kit)
- Antennas (included in kit)

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

**Objective**: Install RX + VTX → Get aircraft flying

| Item | Status | Parts On Hand Since | Notes |
|------|--------|-------------------|-------|
| **MOD-001: ELRS Receiver** | ✓ Parts on hand | June 4, 2025 | HappyModel EP1 Dual RX ready to install |
| **MOD-002: Walksnail Video System** | ✓ Parts on hand | July 24, 2025 | Avatar HD Moonlight kit ready to install |

### Phase 2: Optional Enhancements (Install After Flying)

**Objective**: Add enhancements after baseline performance established

| Item | Status | Parts On Hand Since | Notes |
|------|--------|-------------------|-------|
| **MOD-003: RGB Arm LEDs** | ✓ Parts on hand | June 4, 2025 | SpeedyBee 2812 LEDs x4 |
| **MOD-004: GPS-mate Power Module** | ✓ Parts on hand | July 24, 2025 | VIFLY GPS-mate w/ Finder 2 buzzer |

**Installation Plan**: Install Phase 1 (RX + VTX) → Test flights → Then add Phase 2 enhancements.

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

**No modifications completed yet.**

**Pending Modifications** (parts on hand, ready to install):
- **MOD-001**: ELRS Receiver Installation (parts acquired June 4, 2025)
- **MOD-002**: Walksnail Avatar HD Video System Installation (parts delivered July 24, 2025)
- **MOD-003**: RGB Arm LED Installation (parts acquired June 4, 2025)
- **MOD-004**: VIFLY GPS-mate Power Module Installation (parts delivered July 24, 2025)

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
