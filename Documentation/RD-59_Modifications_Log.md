# RD-59 "Nazgul" Modifications Log

**Drone Designator**: RD-59
**Code Name**: Nazgul
**Operator**: SpyD (Franco Nogarin)
**Last Updated**: 2025-11-10

---

## Modification Summary

| Total Modifications | Last Modification Date | Current Status |
|-------------------|----------------------|----------------|
| **0 completed, 6 pending** | HDZero ordered Nov 2, 2025 | Awaiting installation |

**Installation Plan**:
- **Phase 1 (Critical)**: MOD-001 + MOD-002A (analog) → Get aircraft flying with minimal weight
- **Phase 1B (Optional Upgrade)**: Choose digital path:
  - MOD-002B (Walksnail) → If analog insufficient and prefer Goggles X
  - MOD-002C (HDZero) → If analog insufficient and prefer low latency
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

**UART Selection** (from BLITZ ATF435 wiring diagram):
- **Recommended**: UART2 (R2/T2 pads) - shown in diagram for ELRS receiver
- **Alternative UARTs available**: UART1 (R1/T1), UART3 (R3/T3), UART4 (R4/T4), UART5 (R5/T5), UART6 (R6)

**Wiring Connections**:
- [ ] Solder RX wire to T2 pad (FC transmits to receiver)
- [ ] Solder TX wire to R2 pad (FC receives from receiver)
- [ ] Solder VCC wire to 5V pad (receiver power)
- [ ] Solder GND wire to GND pad (ground)

**Physical Installation**:
- [ ] Determine mounting location (typically between FC and camera mount)
- [ ] Mount HappyModel EP1 Dual RX receiver with double-sided tape or heat shrink

**Dual Antenna Routing Strategy**:

The HappyModel EP1 Dual RX has two T-shaped antennas for diversity reception. The Nazgul was originally designed for DJI O4's antenna configuration, so custom routing is required for optimal dual-antenna diversity.

**Critical Antenna Diversity Principles**:
- ✅ **90° separation**: Antennas must be perpendicular to each other (NOT parallel)
- ✅ **Physical separation**: Mount at different locations on frame
- ✅ **Minimize carbon fiber contact**: CF blocks 2.4GHz signal - maintain 5-10mm clearance minimum
- ✅ **Secure firmly**: Heat shrink/zip ties prevent antenna movement into props
- ✅ **Top mounting preferred**: Less carbon fiber interference than bottom mounting
- ❌ **Never parallel**: Defeats dual diversity purpose
- ❌ **Never touching carbon fiber**: Causes major signal degradation

**Primary Antenna (Antenna 1) - Rear Vertical**:
- [ ] Route through rear of frame (where DJI O4 antenna previously exited, or near GPS)
- [ ] Position **vertically** or angled back/up at 30-45° (perpendicular to drone body)
- [ ] Use existing antenna mount hole if available, or create exit point
- [ ] Heat shrink antenna base to frame standoff or rear for stability
- [ ] Ensure antenna extends beyond frame and clears carbon fiber by 5-10mm minimum

**Secondary Antenna (Antenna 2) - Rear Side Top (RECOMMENDED)**:

**Option 3: Rear Side Top** ✅ **BEST CONFIGURATION**
- [ ] Mount T-antenna **horizontally** (parallel to drone body) on top of frame
- [ ] Position beside or slightly forward of VTX location
- [ ] Maintain **10-15mm clearance from VTX** to minimize RF interference
- [ ] Orient T-antenna so it's **perpendicular to primary antenna** (90° diversity)
- [ ] Ensure antenna tips **do not touch carbon fiber arms** (maintain 5-10mm gap)
- [ ] Use heat shrink or small zip tie to secure to frame standoff or top plate
- [ ] Verify antenna tips have clearance from props during flight

**Why Option 3 (Rear Side Top) is Optimal**:
- Top mounting = minimal carbon fiber interference (best signal propagation)
- Rear location = away from front props (DeadCat has most prop activity forward)
- Physical separation from primary antenna = improved diversity
- Horizontal T gives 90° diversity from vertical primary
- Less vulnerable to ground strikes vs bottom mounting
- Good separation from electrical noise sources (ESC/battery)

**Alternative Options Evaluated** (use only if Option 3 not feasible):

*Option 1: Side Bottom (Under FC)* - ❌ **NOT RECOMMENDED**
- Antenna tips touch CF arms = major signal loss
- Maximum carbon fiber interference
- Vulnerable to ground strikes

*Option 2: Side Top (Above FC, between arms)* - ⚠️ **MARGINAL**
- Better than bottom, but antenna tips still touch/near CF arms
- Props directly above = turbulence/strike risk

*Option 4: Rear Side Bottom (Under VTX)* - ❌ **NOT RECOMMENDED**
- Carbon fiber interference from bottom mounting
- Ground strike vulnerability
- Near battery/ESC electrical noise

**Final Antenna Installation Verification**:
- [ ] Verify 90° separation between primary (vertical) and secondary (horizontal) antennas
- [ ] Verify both antenna tips clear carbon fiber by 5-10mm minimum
- [ ] Verify neither antenna can reach prop paths during flight
- [ ] Verify antennas are secured and cannot move/vibrate loose
- [ ] Verify secondary antenna has 10-15mm clearance from VTX
- [ ] Take photos of final antenna routing for documentation

**Configuration & Testing**:
- [ ] Enable UART2 in Betaflight Ports tab
- [ ] Configure UART2 for Serial RX
- [ ] Set receiver protocol to CRSF (ExpressLRS)
- [ ] Bind receiver to transmitter
- [ ] Test control inputs (roll/pitch/yaw/throttle)
- [ ] Configure and test failsafe settings
- [ ] Verify signal strength and range (bench test)
- [ ] Verify RSSI display on OSD
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

**Pre-Installation Testing**:
- [ ] Bench test TX800 to verify not damaged from previous shorting issues
- [ ] Prepare TX800 mounting with proper standoffs (CRITICAL - avoid shorting!)
- [ ] Verify TX800 antenna connector is intact

**UART Selection for VTX Control** (from BLITZ ATF435 wiring diagram):
- **Recommended**: UART1 (R1/T1 pads) or UART3 (R3/T3 pads) for SmartAudio/Tramp
- **Note**: UART2 already reserved for ELRS receiver (MOD-001)
- **Alternative UARTs**: UART4 (R4/T4), UART5 (R5/T5), UART6 (R6) if needed

**Camera Installation**:
- [ ] Install camera mount on front of frame
- [ ] Mount CADDX Ratel 2 camera with appropriate angle (20-40° typical for freestyle)
- [ ] Wire camera to TX800 VTX (camera video out → VTX video in)

**VTX Installation**:
- [ ] Install TX800 VTX with standoffs (CRITICAL - prevents shorting to FC or frame)
- [ ] Verify standoffs provide clearance from all metal surfaces
- [ ] Position VTX for easy antenna access

**Wiring Connections - VTX to FC**:
- [ ] Solder VTX TX wire to R1 pad (for SmartAudio/Tramp control)
- [ ] Solder VTX RX wire to T1 pad (if bidirectional control needed)
- [ ] Solder VTX power (+) wire to VBAT pad (filtered battery voltage)
- [ ] Solder VTX ground (-) wire to GND pad

**Antenna & Finalization**:
- [ ] Route and secure VTX antenna away from carbon fiber
- [ ] Ensure antenna has clear path (not blocked by frame/props)
- [ ] Secure all wiring with heat shrink/tape
- [ ] Verify no wires touching propeller path

**Configuration & Testing**:
- [ ] Enable UART1 in Betaflight Ports tab
- [ ] Configure UART1 for VTX (SmartAudio/Tramp/IRC Tramp)
- [ ] Configure VTX table in Betaflight (5.8GHz bands/channels)
- [ ] Configure OSD layout (add battery voltage, RSSI, flight time, etc.)
- [ ] Test video feed with analog goggles
- [ ] Verify OSD elements display correctly
- [ ] Test VTX power level switching (25/200/800mW)
- [ ] Verify VTX channel/band switching via OSD
- [ ] Update RD-59_AsBuilt_Parts_List.md

---

### MOD-002B: Walksnail Avatar HD Upgrade (Optional Path 1)

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
- Already own Goggles X (Walksnail compatible)

#### Modification Details

| Item | MOD-002A Config (Analog) | MOD-002B Config (Walksnail) |
|------|------------------------|-------------------------|
| **Video System** | SpeedyBee TX800 (analog) | Walksnail Avatar HD Moonlight |
| **Camera** | CADDX Ratel 2 | Walksnail Moonlight camera |
| **VTX** | TX800 (5.8GHz, 800mW) | Walksnail Avatar VTX (digital) |
| **Recording** | None | HD onboard recording |
| **Goggles** | Any analog goggles | Goggles X (already owned) |

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

### MOD-002C: HDZero Freestyle V2 Upgrade (Optional Path 2)

**Status**: 🟡 **PENDING** - Parts ordered, in transit (expected arrival ~Nov 9-15, 2025)
**Type**: Upgrade
**Priority**: LOW (alternative to Walksnail if MOD-002A performance insufficient)
**Parts Ordered**: November 2, 2025
**Parts Expected**: Week of November 9, 2025

#### Description
Alternative digital upgrade path using HDZero Freestyle V2 system. This is an alternative to MOD-002B (Walksnail), not in addition to it.

#### When to Consider This Upgrade
- **Primary use case**: Operator wants HDZero to become daily driver goggles for FPV fleet
- Analog range (2-4km) is insufficient for desired flying style
- Lower latency preferred over maximum video quality (key HDZero advantage)
- HD video quality desired but not at expense of responsiveness
- Onboard HD recording needed
- Evaluating HDZero ecosystem for potential fleet-wide transition from Walksnail

#### Modification Details

| Item | MOD-002A Config (Analog) | MOD-002C Config (HDZero) |
|------|------------------------|-------------------------|
| **Video System** | SpeedyBee TX800 (analog) | HDZero Freestyle V2 |
| **Camera** | CADDX Ratel 2 | HDZero camera (included in kit) |
| **VTX** | TX800 (5.8GHz, 800mW) | HDZero VTX (digital) |
| **Recording** | None | HD onboard recording |
| **Goggles** | Any analog goggles | HDZero Goggle 2 (red, with Echo antenna kit) |

#### Rationale (If Upgrade Needed)
- **Transitioning to HDZero as primary ecosystem**: Want HDZero Goggle 2 to become daily driver goggles
- **Current fleet context**:
  - DJI: Mini Pro 4 complete setup (Motion, Goggles, screen remote) - cinematic/AP platform
  - Walksnail: Goggles X + multiple drones with Avatar VTX - current FPV fleet
    - RD-54 "Zorro" (Walksnail Avatar VTX)
    - RD-55 "Flylens75" (Walksnail Avatar VTX)
    - RD-59 "Nazgul" (Walksnail Avatar HD Moonlight available, not installed)
  - HDZero: New to ecosystem, evaluating for FPV transition
- **Lower latency advantage**: HDZero known for better responsiveness than Walksnail/DJI
- **Strategic investment**: $829.98 to evaluate HDZero as replacement for Goggles X across 3-aircraft FPV fleet
- **RD-59 as test platform**: Evaluate HDZero here before potentially converting RD-54 & RD-55 from Walksnail
- **Fleet-wide decision**: If HDZero succeeds on RD-59, may retrofit RD-54 & RD-55 with HDZero VTXs
- **HD recording**: Important for post-flight review
- **Ecosystem diversification**: Separate cinematic (DJI) from FPV racing/freestyle (HDZero target)

#### Expected Impact (vs Analog)
- Better video quality (HD digital, lower latency than Walksnail)
- Onboard HD recording capability
- Range comparable to Walksnail (3-6km estimated)
- **Flight time**: 4-6 min (better than Walksnail, lighter than original DJI O4)
- **Weight advantage over O4**: HDZero (~45-50g) vs DJI O4 (~70g) = ~20-25g lighter
- **Power draw**: ~1.5-2A (less than Walksnail's ~2.5A)
- **No action cam**: Build stays light without GoPro/action cam weight

#### HDZero vs Walksnail Comparison

| Characteristic | HDZero Freestyle V2 | Walksnail Avatar HD Moonlight |
|---------------|-------------------|----------------------------|
| **Latency** | Lower (known for responsiveness) | Higher than HDZero |
| **Video Quality** | Good HD quality | Excellent HD quality |
| **Recording** | HD onboard | HD onboard |
| **Range** | 3-6km (estimated) | 3-6km |
| **Ecosystem Cost** | $829.98 (goggles + VTX) | Already own Goggles X + multiple Avatar VTXs |
| **Fleet Strategy** | Evaluating as Goggles X replacement | Current FPV fleet standard |
| **Flight Time** | 4-6 min (lighter than O4) | 3-5 min |
| **Weight** | ~45-50g (lighter than O4) | ~70g |
| **Power Draw** | ~1.5-2A | ~2.5A |

#### Parts Status
- [ ] HDZero Goggle 2 (red) with Echo Antenna Kit - $679.99 (ordered Nov 2, in transit)
- [ ] HDZero Freestyle V2 Kit - $149.99 (ordered Nov 2, in transit)
- Expected delivery: Week of November 9, 2025

#### Installation Checklist (If Proceeding)
- [ ] Receive and inventory HDZero parts
- [ ] Remove TX800 and Ratel 2 (save as spares)
- [ ] Install HDZero camera mount
- [ ] Mount HDZero camera
- [ ] Install HDZero VTX module
- [ ] Wire camera to VTX
- [ ] Wire VTX to FC (check HDZero protocol requirements)
- [ ] Wire VTX to power (VBAT/GND)
- [ ] Route and secure VTX antenna
- [ ] Configure HDZero protocol in Betaflight
- [ ] Configure OSD layout
- [ ] Set up HDZero Goggle 2 with Echo antenna kit
- [ ] Test video feed with HDZero Goggle 2
- [ ] Test HD recording functionality
- [ ] Verify VTX power level and channel
- [ ] Update RD-59_AsBuilt_Parts_List.md

**Decision Point**: Choose between MOD-002B (Walksnail) or MOD-002C (HDZero) based on analog testing and system evaluation. Only one digital system will be installed.

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

**LED Pad Identification** (from BLITZ ATF435 wiring diagram):
- **LED Signal Pad**: Labeled "LED" on FC (WS2812 compatible)
- **Power Options**: 5V or VBAT depending on LED voltage requirements
- **Ground**: GND pad

**Physical Installation**:
- [ ] Mount SpeedyBee 2812 LEDs on motor arms (one per arm)
- [ ] Position LEDs visible from sides/rear for orientation
- [ ] Verify LED power requirements (5V vs VBAT)

**Wiring Connections**:
- [ ] Wire LEDs in series (Data Out from LED1 → Data In to LED2, etc.)
- [ ] Solder first LED Data In wire to LED pad on FC
- [ ] Solder LED power wire to 5V or VBAT pad (check LED specs)
- [ ] Solder LED ground wire to GND pad
- [ ] Secure wiring to arms with heat shrink/tape

**Configuration & Testing**:
- [ ] Enable LED Strip in Betaflight Configuration tab
- [ ] Configure LED count to 4 (one per arm)
- [ ] Configure LED layout in Betaflight LED Strip tab
- [ ] Program LED patterns/colors (orientation indicators)
- [ ] Test LED functionality (power on test)
- [ ] Verify LED patterns during arm/disarm
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

**GPS Power Identification** (from BLITZ ATF435 wiring diagram):
- **Current GPS Connection**: iFlight GPS connected to SDA/SCL pads (I2C)
- **Current Power**: GPS powered from FC 5V rail
- **GPS-mate Purpose**: Provide clean, filtered power to reduce electrical noise

**Physical Installation**:
- [ ] Identify GPS power wires on existing iFlight GPS (5V and GND)
- [ ] Find suitable mounting location for GPS-mate module
- [ ] Install GPS-mate module (double-sided tape or mounting pad)

**Wiring Connections**:
- [ ] Disconnect GPS 5V wire from FC 5V pad
- [ ] Keep GPS GND connected to FC GND (common ground)
- [ ] Connect GPS-mate input power (+) to VBAT pad on FC
- [ ] Connect GPS-mate input ground (-) to GND pad on FC
- [ ] Connect GPS-mate output power to GPS 5V wire (now powered by GPS-mate)
- [ ] Leave GPS data wires (SDA/SCL) connected to FC (unchanged)

**Finder 2 Buzzer Configuration**:
- [ ] Locate Finder 2 buzzer output on GPS-mate module
- [ ] Connect buzzer wires if external buzzer needed (optional)
- [ ] Configure Finder 2 buzzer settings (refer to VIFLY manual)

**Testing & Verification**:
- [ ] Power on aircraft, verify GPS-mate power LED illuminates
- [ ] Verify GPS still communicates with FC (check Betaflight GPS tab)
- [ ] Test GPS satellite acquisition (compare before/after times)
- [ ] Test Finder 2 buzzer functionality (lost model alarm)
- [ ] Verify GPS accuracy improvement (check HDOP values)
- [ ] Secure all wiring with heat shrink/tape
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
