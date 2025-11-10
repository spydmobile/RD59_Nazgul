# RD-59 "Nazgul" Build Timeline

**Drone Designator**: RD-59
**Code Name**: Nazgul
**Operator**: SpyD (Franco Nogarin)
**Last Updated**: 2025-11-10

---

## Timeline Overview

**Project Start**: July 15, 2025 (Acquisition Date)
**Current Phase**: Pre-Flight Preparation
**Days Since Acquisition**: 118 days (as of Nov 10, 2025)

---

## Chronological History

### Phase 0: Pre-Acquisition (Unknown - July 15, 2025)

#### Factory Build
- **Original Build**: Nazgul DC5 ECO V1.1 assembled by iFlight
- **Factory Configuration**: Complete aircraft with DJI O4 Air Unit Pro
- **Original Owner**: Unknown (purchased by Devon "Toasty" Felker)

#### Previous Owner Period
- **Owner**: Devon "Toasty" Felker
- **Location**: Hay River
- **Modifications by Previous Owner**:
  - Removed DJI O4 Air Unit Pro (camera + VTX)
  - Removed GoPro (if one was installed)
  - Note: No receiver was ever installed (not included in factory package)
- **Duration of Ownership**: Unknown
- **Flight History**: Unknown

---

### Phase 0.5: Pre-Acquisition Parts Procurement (June 2025)

#### June 4, 2025 - ELRS Receiver & LED Purchase ✓
- **Parts Acquired** (before RD-59 acquisition):
  - HappyModel ExpressLRS TCXO EP1 Dual RX
  - SpeedyBee Programmable 2812 Arm LEDs (4 pcs)
- **Context**: Parts purchased for general use, not specifically for RD-59
- **Later Applied**: These parts later designated for RD-59 installation (MOD-001, MOD-003)

**Lessons Learned**:
- Having ELRS receiver on hand accelerated RD-59 readiness
- Generic FPV parts procurement paid off when acquiring partial build

---

### Phase 1: Acquisition (July 2025)

#### July 14, 2025 - Pre-Purchase Documentation
- **Photos taken**: Initial documentation photos captured
  - Photos available at: `/Users/franconogarin/localcode/spyd.com/public/drone-lab/drones/RD-59/googlePhotos/`
  - Timestamps: July 14, 2025 at 16:55:46 and 17:13:37

#### July 15, 2025 - Acquisition Day ✓
- **Transaction Completed**
  - Purchased from: Devon "Toasty" Felker
  - Location: Hay River
  - Purchase Price: $273.12 CAD
  - Condition: Partial build - missing video system, no receiver
- **Photos taken**: Additional documentation at 12:35:11
- **Initial Assessment**:
  - Frame: Complete and undamaged
  - Flight electronics: Present (FC, ESC, motors)
  - GPS: Present
  - Battery connector: XT60 with anti-spark
  - Props: Nazgul F5 included
  - Missing: DJI O4 video system (removed)
  - Missing: Receiver (never installed)

**Lessons Learned**:
- Aircraft purchased as partial build with known missing components
- Previous owner removed video system, reducing value but also cost
- Provides opportunity to select preferred video system (analog vs digital)

---

### Phase 2: Pre-Flight Preparation (July 15, 2025 - Present)

#### July 17, 2025 - Parts Ordered ✓
- **Decision Made**: Walksnail Avatar HD selected for video system
- **Rationale**:
  - Operator moved away from DJI ecosystem ($10k invested, no longer using)
  - Considerable investment in Goggles X (Avatar compatible)
  - Onboard HD recording capability important to operator
- **Parts Ordered**:
  - Walksnail Avatar HD Moonlight VTX Kit
  - Gemfan 51433 Hurricane Tri-Blade Props (lemon yellow x2, dark grey x2)
  - GNB 1350mAh 6S 100C LiPo XT60 (x4)
  - SpeedyBee F7 50A V3 Combo Stack (future consideration)
  - VIFLY GPS-mate External GPS Power Module w/ Built-In Finder 2 Buzzer

**Decisions Made**:
- ✅ Receiver: HappyModel ELRS EP1 Dual RX (already owned)
- ✅ Video system: Walksnail Avatar HD Moonlight (ordered)
- ✅ Batteries: GNB 1350mAh 6S 100C (ordered)
- ✅ Props: Gemfan Hurricane 51433 with color scheme for DeadCat frame

#### July 24, 2025 - Parts Delivered ✓
- **All ordered parts received**
- **Inventory Status**: All critical components on hand
  - MOD-001 (ELRS receiver): Ready
  - MOD-002 (Walksnail video): Ready
  - MOD-003 (RGB LEDs): Ready
  - MOD-004 (GPS-mate): Ready
- **Aircraft Status**: Ready for installation work

**Lessons Learned**:
- 7-day turnaround from order to delivery (July 17 → July 24)
- All critical airworthiness components acquired within 9 days of drone purchase

#### July 24 - November 10, 2025 - Planning & Documentation
- **Current Status**: Aircraft stored, all parts on hand, awaiting installation
- **Documentation Created** (November 10, 2025):
  - Repository established for RD-59 Nazgul
  - As-built parts list documented
  - Factory specifications captured
  - Modifications log with MOD-001 through MOD-004 detailed
  - Complete installation checklists prepared

**Current Blockers**:
- ⏳ No receiver installed - Parts on hand, awaiting installation (MOD-001)
- ⏳ No video system - Parts on hand, awaiting installation (MOD-002)
- ⏳ Installation work not yet started - All tools and parts available

---

## Future Planned Activities

### Phase 3: Component Selection & Ordering ✅ COMPLETED

**Objectives**: ✅ All objectives met
- ✅ Select and order receiver system
- ✅ Select and order video system
- ✅ Plan installation sequence

**Tasks Completed**:
- [x] Research ELRS receiver options (completed before June 4)
- [x] Research video system options (completed before July 17)
- [x] Make final component selections (Walksnail Avatar HD selected)
- [x] Order receiver system (already owned as of June 4)
- [x] Order video system (ordered July 17)
- [x] Receive and inventory parts (delivered July 24)

**Actual Duration**: 7 days (July 17 order → July 24 delivery)
**Phase Completed**: July 24, 2025

---

### Phase 4: Critical Installations (TBD)

**Objectives**:
- Install receiver and video system (MOD-001 + MOD-002)
- Configure all electronics
- Get aircraft flying

**Installation Plan**: Install RX + VTX → Get it flying → Everything else comes later

**Phase 4a: Receiver Installation (MOD-001)**
- [ ] Install HappyModel ELRS EP1 Dual RX
- [ ] Wire receiver to FC (TX/RX/VCC/GND)
- [ ] Route dual antennas for optimal diversity
- [ ] Configure ELRS in Betaflight
- [ ] Bind receiver to transmitter
- [ ] Test control inputs and failsafe

**Phase 4b: Video System Installation (MOD-002)**
- [ ] Install Walksnail Avatar HD Moonlight VTX Kit
- [ ] Mount Moonlight camera
- [ ] Wire VTX to FC (UART for MSP) and power (VBAT/GND)
- [ ] Route and secure VTX antenna
- [ ] Configure MSP and OSD in Betaflight
- [ ] Test video feed with Goggles X
- [ ] Verify HD recording functionality

**Phase 4c: Bench Testing & Preparation**
- [ ] Bench test all systems together
- [ ] Verify all functions operational
- [ ] Pre-flight safety checks
- [ ] Update documentation

**Estimated Duration**: 1-2 days (depending on complexity)

---

### Phase 5: Test Flights & Baseline Establishment (TBD)

**Objectives**:
- Perform first test flights
- Establish operational baseline
- Tune and optimize as needed

**Tasks**:
- [ ] Pre-flight inspection
- [ ] First hover test (LOS)
- [ ] First FPV test flight
- [ ] PID tuning as needed
- [ ] Video quality assessment
- [ ] Range testing
- [ ] Document baseline performance
- [ ] Update parts list with test results

**Estimated Duration**: 1-2 weeks (weather dependent)

---

### Phase 6: Optional Enhancements (TBD)

**Objectives**:
- Install optional enhancements (MOD-003, MOD-004)
- Improve visibility, GPS performance, and lost model recovery

**Prerequisites**: Complete Phase 5 test flights and establish baseline performance

**Tasks**:
- [ ] Install RGB Arm LEDs (MOD-003) - SpeedyBee 2812 LEDs
- [ ] Configure LED patterns in Betaflight
- [ ] Test LED functionality
- [ ] Install VIFLY GPS-mate power module (MOD-004)
- [ ] Configure Finder 2 buzzer
- [ ] Test GPS performance improvement
- [ ] Test lost model buzzer functionality
- [ ] Update documentation

**Estimated Duration**: 1 day

**Note**: These are optional enhancements. Skip this phase if baseline performance is satisfactory and enhancements not desired.

---

### Phase 7: Operational Status (TBD)

**Objectives**:
- Achieve full operational status
- Regular flight operations
- Ongoing maintenance

**Expected Activities**:
- Regular flight sessions
- Maintenance as needed
- Performance monitoring
- Incident response (if any)
- Upgrades/modifications as desired

---

## Project Statistics

### Time Investment

| Phase | Start Date | End Date | Duration | Status |
|-------|-----------|----------|----------|---------|
| **Pre-Acquisition Parts** | June 4, 2025 | June 4, 2025 | 1 day | Completed |
| **Pre-Acquisition** | Unknown | July 15, 2025 | Unknown | Completed |
| **Acquisition** | July 15, 2025 | July 15, 2025 | 1 day | Completed |
| **Component Selection** | July 15, 2025 | July 24, 2025 | 9 days | Completed |
| **Pre-Flight Prep** | July 24, 2025 | Present | 109 days | In Progress |
| **Installation** | TBD | TBD | TBD | Pending |
| **Test Flights** | TBD | TBD | TBD | Pending |
| **Operational** | TBD | Ongoing | Ongoing | Pending |

**Days Since Acquisition**: 118 days (July 15 - Nov 10, 2025)
**Days Parts On Hand**: 109 days (July 24 - Nov 10, 2025)

### Cost Tracking

| Category | Amount (CAD) | Date | Notes |
|----------|-------------|------|-------|
| **ELRS Receiver + LEDs** | Price not recorded | June 4, 2025 | HappyModel EP1 Dual RX + SpeedyBee RGB LEDs x4 |
| **Initial Purchase** | $273.12 | July 15, 2025 | Partial aircraft from Toasty |
| **Video System** | Price not recorded | July 17, 2025 | Walksnail Avatar HD Moonlight VTX Kit |
| **Batteries (x4)** | Price not recorded | July 17, 2025 | GNB 1350mAh 6S 100C XT60 |
| **Props** | Price not recorded | July 17, 2025 | Gemfan 51433 Hurricane x4 sets |
| **GPS-mate** | Price not recorded | July 17, 2025 | VIFLY GPS-mate w/ Finder 2 |
| **SpeedyBee Stack** | Price not recorded | July 17, 2025 | F7 50A V3 Combo (future consideration) |
| **Total Recorded** | $273.12+ | | Plus unrecorded parts costs |

**Note**: Exact costs for parts ordered June 4 and July 17 not documented. Consider updating with actual costs if desired.

### Flight Hours

| Metric | Value |
|--------|-------|
| **Total Flight Time** | 0 hours |
| **Flights by Current Operator** | 0 |
| **Flights by Previous Owner** | Unknown |

---

## Key Milestones

- ✅ **June 4, 2025**: ELRS receiver and RGB LEDs acquired
- ✅ **July 15, 2025**: Aircraft acquired from Devon "Toasty" Felker
- ✅ **July 17, 2025**: Video system, batteries, props, and accessories ordered
- ✅ **July 24, 2025**: All ordered parts delivered - aircraft ready for installation
- ✅ **November 10, 2025**: Documentation repository established
- ⏳ **TBD**: Receiver installed (MOD-001)
- ⏳ **TBD**: Video system installed (MOD-002)
- ⏳ **TBD**: Optional enhancements installed (MOD-003, MOD-004)
- ⏳ **TBD**: First test flight by current operator
- ⏳ **TBD**: Operational status achieved
- ⏳ **TBD**: Decision on SpeedyBee stack upgrade (if needed)

---

## Lessons Learned

### From Acquisition (July 2025)
1. **Partial builds can be good value** - Purchasing aircraft without video system saved money and provides flexibility for system selection
2. **Know what's missing** - Clear understanding of missing components allowed accurate pricing and planning
3. **Documentation matters** - Photos from July 14-15 provide valuable reference for as-purchased condition
4. **Having parts on hand pays off** - ELRS receiver already owned before acquisition accelerated readiness

### From Parts Selection (July 2025)
1. **Ecosystem matters** - Moving away from DJI ($10k invested) influenced choice of Walksnail Avatar
2. **Existing investment drives decisions** - Goggles X ownership made Avatar HD the logical choice
3. **Fast parts turnaround** - 7-day delivery (July 17 → 24) enabled quick progression
4. **Smart prop color scheme** - Lemon yellow rear, dark grey front keeps props out of FPV camera (DeadCat design)
5. **Future-proofing** - Purchasing SpeedyBee stack as backup option provides insurance if BLITZ stack underperforms

### From Documentation (November 2025)
1. **Document early and accurately** - 109 days between parts arrival and documentation - earlier would be better
2. **Capture rationale** - Recording "why" decisions were made (DJI ecosystem exit) provides valuable context
3. **Track all dates** - Having specific dates (June 4, July 17, July 24) creates clear timeline

### Future Lessons
*(To be added as installations and test flights progress)*

---

## Related Documents

- **Parts List**: `RD-59_AsBuilt_Parts_List.md`
- **Incident Log**: `RD-59_Incident_Log.md`
- **Modifications**: `RD-59_Modifications_Log.md`
- **Factory Specs**: `reference/Nazgul_DC5_ECO_Factory_Specs.md`
- **Photo Gallery**: [Google Photos Album](https://photos.google.com/album/AF1QipMQ81SgmNKcywQYFzFxxncO6l4DfiegxZddzp05)
