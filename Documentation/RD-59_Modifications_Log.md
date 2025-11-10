# RD-59 "Nazgul" Modifications Log

**Drone Designator**: RD-59
**Code Name**: Nazgul
**Operator**: SpyD (Franco Nogarin)
**Last Updated**: 2025-11-10

---

## Modification Summary

| Total Modifications | Last Modification Date | Current Status |
|-------------------|----------------------|----------------|
| **0 completed, 5 pending** | Parts delivered July 24, 2025 | Awaiting installation |

**Installation Plan**:
- **Phase 1 (Critical)**: MOD-001 + MOD-002A (analog) → Get aircraft flying with minimal weight
- **Phase 1B (Optional Upgrade)**: MOD-002B (digital) → Upgrade to Walksnail if analog insufficient
- **Phase 2 (Optional Enhancements)**: MOD-003 + MOD-004 → Add LEDs and GPS-mate after baseline established

---

## Planned Modifications

### PHASE 1: CRITICAL AIRWORTHINESS INSTALLATIONS

**Objective**: Install receiver and video system to achieve minimum flight capability

### MOD-001: ELRS Receiver Installation

**Status**: 🟡 **PENDING** - Parts on hand, awaiting installation
**Type**: Initial Installation
**Priority**: CRITICAL (required for airworthiness)
**Parts Acquired**: June 4, 2025 (already owned before drone acquisition)

#### Description
Installation of ExpressLRS receiver system to enable aircraft control.

#### Modification Details

| Item | Original Config | Modified Config |
|------|----------------|-----------------|
| **Receiver** | None (never included) | HappyModel ExpressLRS TCXO EP1 Dual RX |
| **Control Link** | None | ExpressLRS 2.4GHz |
| **Antenna** | None | Included with EP1 Dual RX |

#### Rationale
- Aircraft was purchased without receiver (not included in factory package)
- Receiver is critical component for aircraft control
- ELRS selected for low latency, long range, and reliability
- EP1 Dual RX provides redundancy with dual antenna diversity
- Already owned this receiver prior to acquiring RD-59

#### Expected Impact
- Enable aircraft control capability
- Required for test flights
- Minimal weight impact (~1-2g)
- Dual receiver provides improved range and reliability

#### Parts On Hand
- [x] HappyModel ExpressLRS TCXO EP1 Dual RX (acquired June 4, 2025)
- [x] Antennas (included with receiver)

#### Installation Checklist
- [ ] Verify FC UART availability for receiver
- [ ] Determine mounting location
- [ ] Install receiver
- [ ] Wire to FC (TX/RX/VCC/GND)
- [ ] Route antennas for optimal diversity
- [ ] Configure ELRS in Betaflight
- [ ] Bind to transmitter
- [ ] Test control inputs and failsafe
- [ ] Verify signal strength and range
- [ ] Secure with heat shrink/tape
- [ ] Update RD-59_AsBuilt_Parts_List.md

---

### MOD-002A: Analog Video System Installation (Initial)

**Status**: 🟡 **PENDING** - Parts on hand, awaiting installation
**Type**: Initial Installation
**Priority**: CRITICAL (required for FPV operation)
**Parts Status**: Already owned (liberated from 3.5" build)

#### Description
Installation of analog FPV system (SpeedyBee TX800 + CADDX Ratel 2) as initial video system to get aircraft flying quickly.

#### Modification Details

| Item | Original Config | Modified Config |
|------|----------------|-----------------|
| **Video System** | DJI O4 Air Unit Pro (Digital HD) | Analog (TX800 + Ratel 2) |
| **Camera** | DJI O4 1/1.3" sensor, 155° FOV | CADDX Ratel 2 (red) |
| **VTX** | DJI O4 (5.170-5.850 GHz, 15km range) | SpeedyBee TX800 (5.8GHz, 25-800mW) |
| **Recording** | DJI O4 4GB onboard | None (analog) |

#### Rationale
- **Test with what's already owned**: TX800 and Ratel 2 already on hand (liberated from 3.5" build)
- **Get flying quickly**: Analog is lighter and faster to install
- **Better flight time**: ~5-7 min vs 3-5 min with digital (40-50% improvement)
- **Lighter weight**: ~25g vs ~70g for digital (45g savings)
- **Lower power draw**: ~1A vs ~2.5A for digital
- **Evaluate needs**: Test analog performance before committing to digital
- **TX800 redemption**: Previous underperformance on 3.5" suspected due to mounting without standoffs (shorting issues)
- **Proper installation this time**: Will use standoffs to prevent shorting as per manual

#### Expected Impact
- Enable FPV video capability (analog quality)
- Flight time: **5-7 minutes** freestyle (excellent)
- Range: **2-4km** at 800mW (sufficient for most flying)
- Weight impact: **+25g** (minimal)
- Power draw: **~1A** at 800mW (low)
- No onboard recording (trade-off for flight time)

#### Performance Comparison vs Digital

| Metric | Analog (MOD-002A) | Digital (MOD-002B) | Advantage |
|--------|------------------|-------------------|-----------|
| Weight | +25g | +70g | Analog: 45g lighter |
| Power | ~1A | ~2.5A | Analog: 1.5A less |
| Flight Time | 5-7 min | 3-5 min | Analog: +40-50% |
| Range | 2-4km | 3-6km | Digital: slightly better |
| Video Quality | Standard analog | HD digital | Digital: much better |
| Recording | No | Yes (HD) | Digital wins |
| Cost | $0 (owned) | $0 (owned) | Tie |

**Decision**: Start with analog, evaluate if digital upgrade is worth the flight time penalty

#### Parts On Hand
- [x] SpeedyBee TX800 VTX (liberated from 3.5" build)
- [x] CADDX Ratel 2 camera (red) (already owned)
- [x] VTX antenna (included with TX800)

#### Installation Checklist
- [ ] Bench test TX800 to verify not damaged from previous shorting
- [ ] Prepare TX800 mounting with proper standoffs (critical - avoid shorting!)
- [ ] Install camera mount
- [ ] Mount CADDX Ratel 2 camera
- [ ] Install TX800 VTX with standoffs
- [ ] Wire camera to VTX
- [ ] Wire VTX to FC (UART for SmartAudio/Tramp if supported)
- [ ] Wire VTX to power (VBAT/GND)
- [ ] Route and secure VTX antenna
- [ ] Configure VTX table in Betaflight
- [ ] Configure OSD layout
- [ ] Test video feed with analog goggles
- [ ] Verify power levels (25/200/800mW)
- [ ] Update RD-59_AsBuilt_Parts_List.md

---

### MOD-002B: Digital Video System Upgrade (Optional)

**Status**: 🔵 **OPTIONAL** - Parts on hand, install only if MOD-002A performance insufficient
**Type**: Upgrade
**Priority**: LOW (upgrade from analog if needed)
**Parts Ordered**: July 17, 2025
**Parts Delivered**: July 24, 2025

#### Description
Optional upgrade to Walksnail Avatar HD Moonlight VTX Kit if analog performance proves insufficient.

#### When to Consider This Upgrade
- Analog range (2-4km) is insufficient for desired flying style
- HD video quality desired for review/progression
- Onboard HD recording needed
- Willing to accept 40-50% flight time reduction for better video

#### Modification Details

| Item | MOD-002A Config (Analog) | MOD-002B Config (Digital) |
|------|------------------------|-------------------------|
| **Video System** | SpeedyBee TX800 (analog) | Walksnail Avatar HD Moonlight |
| **Camera** | CADDX Ratel 2 | Walksnail Moonlight camera |
| **VTX** | TX800 (5.8GHz, 800mW) | Walksnail Avatar VTX (digital) |
| **Recording** | None | HD onboard recording |

#### Rationale (If Upgrade Needed)
- **Walksnail over DJI**: Operator exited DJI ecosystem ($10k investment)
- **Goggles X compatibility**: Considerable investment already made
- **HD recording**: Important for post-flight review
- **Better range**: 3-6km vs 2-4km analog
- **Digital HD quality**: Superior to analog

#### Expected Impact (vs Analog)
- Better video quality (HD digital)
- Onboard HD recording capability
- Slightly better range (3-6km vs 2-4km)
- **Flight time penalty**: 3-5 min vs 5-7 min (40-50% reduction)
- **Weight penalty**: +45g heavier than analog
- **Power penalty**: +1.5A more draw than analog

#### Parts On Hand
- [x] Walksnail Avatar HD Moonlight VTX Kit (delivered July 24, 2025)
- [x] Moonlight camera (included in kit)
- [x] VTX module (included in kit)
- [x] Antennas (included in kit)

#### Installation Checklist (If Proceeding)
- [ ] Remove TX800 and Ratel 2 (save as spares)
- [ ] Install Walksnail camera mount
- [ ] Mount Moonlight camera
- [ ] Install Walksnail VTX module
- [ ] Wire camera to VTX
- [ ] Wire VTX to FC (UART for MSP)
- [ ] Wire VTX to power (VBAT/GND)
- [ ] Route and secure VTX antenna
- [ ] Configure MSP in Betaflight
- [ ] Configure OSD layout
- [ ] Test video feed with Goggles X
- [ ] Test HD recording functionality
- [ ] Verify VTX power level and channel
- [ ] Update RD-59_AsBuilt_Parts_List.md

**Decision Point**: Only proceed with this upgrade if analog testing reveals insufficient performance

---

### PHASE 2: OPTIONAL ENHANCEMENTS

**Objective**: Add enhancements after aircraft is flying and baseline performance is established

**Installation Sequence**: Complete Phase 1 (MOD-001 + MOD-002) and test flights first, then proceed with these optional enhancements.

---

### MOD-003: RGB Arm LED Installation

**Status**: 🟡 **PENDING** - Parts on hand, awaiting installation after Phase 1
**Type**: Enhancement
**Priority**: LOW (aesthetic upgrade - install after aircraft is flying)
**Parts Acquired**: June 4, 2025 (already owned before drone acquisition)

#### Description
Installation of programmable RGB LEDs on motor arms for visibility and aesthetics.

#### Modification Details

| Item | Original Config | Modified Config |
|------|----------------|-----------------|
| **Arm LEDs** | None | SpeedyBee Programmable 2812 Arm LEDs (4 pcs) |
| **LED Control** | None | FC LED output (programmable) |

#### Rationale
- Improved visibility during flight (orientation and position)
- Aesthetic enhancement
- Low-light/night flying aid
- Already owned these LEDs prior to acquiring RD-59

#### Expected Impact
- Enhanced visual orientation during flight
- Night flying capability
- Weight impact: Minimal (~2-4g total for 4 LEDs)
- Minor power draw from battery

#### Parts On Hand
- [x] SpeedyBee Programmable 2812 Arm LEDs x4 (acquired June 4, 2025)

#### Installation Checklist
- [ ] Verify FC LED pad availability
- [ ] Mount LEDs on motor arms
- [ ] Wire LEDs in series (data line)
- [ ] Connect to FC LED pad
- [ ] Configure LED count in Betaflight
- [ ] Program LED patterns/colors
- [ ] Test LED functionality
- [ ] Secure wiring with heat shrink/tape
- [ ] Update RD-59_AsBuilt_Parts_List.md

---

### MOD-004: VIFLY GPS-mate Power Module Installation

**Status**: 🟡 **PENDING** - Parts on hand, awaiting installation after Phase 1
**Type**: Enhancement
**Priority**: MEDIUM (improves GPS performance - install after aircraft is flying)
**Parts Ordered**: July 17, 2025
**Parts Delivered**: July 24, 2025

#### Description
Installation of VIFLY GPS-mate external power module with built-in Finder 2 buzzer to provide clean power to existing iFlight GPS.

#### Modification Details

| Item | Original Config | Modified Config |
|------|----------------|-----------------|
| **GPS Power** | Powered from FC 5V rail | VIFLY GPS-mate (dedicated power module) |
| **GPS Module** | iFlight GPS (existing) | iFlight GPS (unchanged) |
| **Buzzer** | None or FC buzzer | VIFLY Finder 2 buzzer (built into GPS-mate) |

#### Rationale
- **Clean power for GPS**: GPS-mate provides dedicated, filtered power to GPS module
- **Improved GPS performance**: Reduced electrical noise improves satellite acquisition and accuracy
- **Built-in buzzer**: Finder 2 buzzer aids in locating aircraft after crashes
- **Not a replacement**: This powers the existing iFlight GPS, doesn't replace it

#### Expected Impact
- Faster GPS satellite lock
- Improved GPS accuracy and stability
- Lost model finder functionality
- Weight impact: Minor (~5-10g)
- Additional crash recovery aid

#### Parts On Hand
- [x] VIFLY GPS-mate External GPS Power Module w/ Built-In Finder 2 Buzzer (delivered July 24, 2025)

#### Installation Checklist
- [ ] Identify GPS power wires on existing iFlight GPS
- [ ] Install GPS-mate module
- [ ] Disconnect GPS from FC 5V power
- [ ] Connect GPS to GPS-mate output
- [ ] Connect GPS-mate input to battery power (VBAT)
- [ ] Verify GPS power LED on GPS-mate
- [ ] Test GPS satellite acquisition
- [ ] Configure Finder 2 buzzer
- [ ] Test buzzer functionality
- [ ] Secure GPS-mate module
- [ ] Update RD-59_AsBuilt_Parts_List.md

---

## Completed Modifications

**No modifications completed yet.**

All components remain in as-purchased configuration from July 15, 2025.

---

## Future Considerations

### SpeedyBee F7 50A V3 Combo Stack (Not Yet Planned)

**Status**: 🔵 **ON HAND** - Not an active modification
**Parts Ordered**: July 17, 2025
**Parts Delivered**: July 24, 2025

#### Description
SpeedyBee F7 50A V3 combo stack purchased and on hand, but **not currently planned for installation**. This is a potential future upgrade option once the current BLITZ ATF435/E55S stack has been tested and evaluated.

#### Why On Hand
- Purchased as a "good future stack for the 5-inch"
- Current BLITZ stack performance is unknown (aircraft not yet flown)
- Provides backup option if BLITZ stack proves inadequate
- Can be evaluated after establishing baseline performance

#### Current Status
- BLITZ ATF435 FC + BLITZ E55S ESC remain installed
- SpeedyBee stack stored for potential future use
- **No modification planned until current stack is tested**

#### Next Steps
- Complete MOD-001 through MOD-004 (receiver, video, LEDs, GPS-mate)
- Test fly RD-59 with current BLITZ stack
- Evaluate performance and identify any issues
- Decide if SpeedyBee stack upgrade is needed

**Note**: This will only become an active modification (MOD-005 or later) if operator decides to replace the BLITZ stack after flight testing.

---

## Modification Categories

**Understanding Modification Types**:

- **Initial Installation**: Installing component that was never present
- **Emergency Repair**: Forced modification due to crash damage
- **Upgrade**: Replacing functional component with better alternative
- **Enhancement**: Adding new capability not present before
- **Replacement**: Like-for-like part swap due to wear or failure

---

## Modification Numbering

Modifications are numbered sequentially: MOD-001, MOD-002, MOD-003, etc.

**Status Indicators**:
- 🔴 **PROPOSED**: Modification being considered
- 🟡 **PENDING**: Parts ordered, awaiting installation
- 🔵 **IN PROGRESS**: Installation underway
- 🟢 **COMPLETED**: Modification finished and tested

---

## Related Documents

- **Parts List**: `RD-59_AsBuilt_Parts_List.md`
- **Incident Log**: `RD-59_Incident_Log.md`
- **Timeline**: `RD-59_Build_Timeline.md`
- **Factory Specs**: `reference/Nazgul_DC5_ECO_Factory_Specs.md`
