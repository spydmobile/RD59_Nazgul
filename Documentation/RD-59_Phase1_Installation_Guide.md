# RD-59 "Nazgul" Phase 1 Installation Guide

**Drone Designator**: RD-59
**Code Name**: Nazgul
**Operator**: SpyD (Franco Nogarin)
**Created**: 2025-11-10
**Status**: Pre-Installation Planning

---

## Overview

This guide provides step-by-step instructions for Phase 1 installations on RD-59, using specific wiring details from the BLITZ ATF435 flight controller diagram.

**Phase 1 Objective**: Install receiver and analog video system to achieve minimum flight capability

**Modifications Covered**:
- MOD-001: ELRS Receiver Installation
- MOD-002A: Analog Video System Installation (TX800 + Ratel 2)

---

## Prerequisites

### Tools Required
- Soldering iron (temperature-controlled recommended)
- Solder (60/40 or 63/37 rosin core)
- Wire strippers
- Heat shrink tubing
- Hot air gun or lighter (for heat shrink)
- Double-sided mounting tape
- Hex drivers (for frame disassembly if needed)
- Multimeter (for continuity testing)

### Parts Required
- [x] HappyModel ExpressLRS TCXO EP1 Dual RX (on hand since June 4, 2025)
- [x] SpeedyBee TX800 VTX (on hand, liberated from 3.5" build)
- [x] CADDX Ratel 2 camera (red) (on hand)
- [x] VTX antenna (included with TX800)
- [ ] VTX mounting standoffs (verify TX800 includes them - CRITICAL)

### Pre-Installation Checks
- [ ] Verify TX800 VTX is functional (bench test recommended due to previous shorting issues)
- [ ] Verify TX800 includes proper standoffs (prevents shorting to FC/frame)
- [ ] Verify ELRS receiver antennas are intact
- [ ] Verify camera lens is clean and undamaged
- [ ] Have analog goggles available for video testing

---

## BLITZ ATF435 Flight Controller Reference

### UART Assignments (Recommended)

| UART | Pads | Assignment | Purpose |
|------|------|------------|---------|
| **UART2** | R2/T2 | ELRS Receiver | Control link (CRSF protocol) |
| **UART1** | R1/T1 | TX800 VTX | SmartAudio/Tramp control |
| UART3 | R3/T3 | Available | (Alternative for VTX if needed) |
| UART4 | R4/T4 | Available | (Future use) |
| UART5 | R5/T5 | Available | (Future use) |
| UART6 | R6 | Available | (Future use) |

**Note**: SDA/SCL pads are for GPS (I2C) and cannot be remapped to UART

### Power Rails Available

| Power Rail | Voltage | Use Case |
|------------|---------|----------|
| **VBAT** | Battery voltage (22.2V nominal for 6S) | VTX power, high-power peripherals |
| **9V** | Regulated 9V | (Not needed for Phase 1) |
| **5V** | Regulated 5V | Receiver power, camera power |
| **3.3V** | Regulated 3.3V | (Internal FC use) |
| **GND** | Ground | All components |

### FC Status LEDs (Reference)

| LED Color | Meaning |
|-----------|---------|
| Blue | Flashing during startup |
| Red | 3.3V power indicator |
| Orange | VBAT power indicator |
| Green | 5V BEC power indicator |

**Expected on Power-Up**: Red, Orange, and Green LEDs should illuminate

---

## MOD-001: ELRS Receiver Installation

### Step 1: Physical Mounting

**Mounting Location Options**:
- Between FC and top plate (typical)
- Under FC (if space available)
- Side-mounted on frame standoffs

**Installation**:
1. Determine best mounting location (access to R2/T2/5V/GND pads on FC)
2. Clean mounting surface with isopropyl alcohol
3. Apply double-sided mounting tape to receiver
4. Position receiver for easy access to antenna routing
5. Press firmly to secure

### Step 2: Antenna Routing

**Critical**: Dual antennas must be positioned at ~90° to each other for optimal diversity reception

**Routing Strategy**:
- Antenna 1: Route to rear-left, secure to rear arm
- Antenna 2: Route to rear-right, secure to rear arm
- Ensure antennas exit frame at different angles (avoid parallel)
- Use heat shrink or zip ties to secure antenna wires to frame
- Keep antennas away from carbon fiber and metal (RF blocking)

### Step 3: Wiring to FC

**Wire Connections** (UART2 - R2/T2 pads):

| Receiver Wire | FC Pad | Purpose | Notes |
|--------------|--------|---------|-------|
| RX (receiver input) | T2 | FC transmits data to receiver | Yellow/white wire typical |
| TX (receiver output) | R2 | Receiver transmits data to FC | Green/white wire typical |
| VCC (power) | 5V | Receiver power (5V regulated) | Red wire typical |
| GND (ground) | GND | Common ground | Black wire typical |

**Soldering Steps**:
1. Tin all four receiver wires
2. Tin R2, T2, 5V, and GND pads on FC
3. Solder RX wire to T2 pad (FC transmits to receiver)
4. Solder TX wire to R2 pad (Receiver transmits to FC)
5. Solder VCC wire to 5V pad
6. Solder GND wire to GND pad
7. Verify all joints are shiny and secure (no cold solder joints)
8. Apply heat shrink over exposed solder joints (optional but recommended)

**Common Mistake**: Swapping RX/TX - Remember: Receiver RX connects to FC TX (and vice versa)

### Step 4: Betaflight Configuration

**Ports Tab**:
1. Connect FC to Betaflight Configurator via USB
2. Navigate to **Ports** tab
3. Find **UART2** row
4. Set **Serial RX** in dropdown
5. Click **Save and Reboot**

**Configuration Tab**:
1. Navigate to **Configuration** tab
2. Scroll to **Receiver** section
3. Set **Receiver Protocol** to **CRSF**
4. Click **Save and Reboot**

### Step 5: Binding & Testing

**Binding Procedure**:
1. Put ELRS transmitter into bind mode (refer to transmitter manual)
2. Power on RD-59 with battery (expect receiver LED to flash rapidly)
3. Wait for bind confirmation (receiver LED solid or slow blink)
4. Power cycle aircraft to confirm bind persists

**Control Testing**:
1. Navigate to **Receiver** tab in Betaflight
2. Move sticks on transmitter
3. Verify all channels respond correctly:
   - Roll (Aileron) - Channel 1
   - Pitch (Elevator) - Channel 2
   - Throttle - Channel 3
   - Yaw (Rudder) - Channel 4
   - Arm switch - Channel 5 (or configured channel)
4. Verify channel ranges (typically 1000-2000)

**Failsafe Configuration**:
1. Navigate to **Failsafe** tab
2. Set desired failsafe behavior (typically "Drop" for throttle)
3. Configure failsafe stage 2 (land or no pulses)
4. Test failsafe by powering off transmitter (verify aircraft disarms)

**RSSI Verification**:
1. Power on transmitter and aircraft
2. Check RSSI value in Betaflight (should show signal strength)
3. Walk away with transmitter to test range (optional bench test)

**Completion**: MOD-001 complete when all controls respond and failsafe works correctly

---

## MOD-002A: Analog Video System Installation

### Step 0: Pre-Installation Bench Test

**CRITICAL**: TX800 suspected of shorting issues on previous 3.5" build

**Bench Test Procedure**:
1. Connect TX800 to power supply (7.4V-25.2V capable, or old battery)
2. Connect CADDX Ratel 2 camera to TX800 video input
3. Power on TX800 (check for LED indicator)
4. Check video output with analog goggles/receiver
5. Verify SmartAudio/Tramp control works (if testable)
6. **If TX800 shows issues**: Consider replacement before installation

**Standoff Verification**:
- Verify TX800 includes proper standoffs for mounting
- Standoffs must provide clearance from FC and frame (prevents shorting)
- If standoffs missing: source replacements before proceeding

### Step 1: Camera Installation

**Camera Mounting**:
1. Install camera mount on front of frame (if not already present)
2. Determine camera angle (20-40° typical for freestyle, 30° recommended starting point)
3. Mount CADDX Ratel 2 camera with appropriate angle
4. Secure camera with included screws/hardware
5. Route camera wire toward VTX mounting location

**Camera Angle Guide**:
- 20-25°: Cruising/cinematic flying
- 30-35°: Balanced freestyle/racing
- 40-50°: Aggressive racing

### Step 2: VTX Physical Installation

**CRITICAL SAFETY NOTE**: TX800 MUST be mounted with standoffs to prevent shorting to FC or carbon fiber frame

**VTX Mounting**:
1. Position TX800 on stack with standoffs installed
2. Verify standoffs provide 3-5mm clearance from FC below
3. Verify no metal surfaces can contact VTX circuit board
4. Secure VTX with screws through standoffs
5. Position for easy antenna connector access

**Antenna Installation**:
1. Thread antenna wire through frame (route away from carbon fiber)
2. Attach antenna to TX800 SMA/U.FL connector
3. **NEVER power VTX without antenna connected** (immediate damage)
4. Secure antenna wire to frame with zip tie/heat shrink
5. Position antenna for clear signal path (not blocked by frame/props)

### Step 3: Camera to VTX Wiring

**Connection**:
- Camera video output (yellow wire typical) → VTX video input
- Camera ground (black wire typical) → VTX ground
- Camera power (red wire typical) → VTX camera power output (5V typically)

**Note**: TX800 likely provides regulated power for camera - verify in TX800 manual

### Step 4: VTX to FC Wiring

**Power Connections**:

| VTX Wire | FC Pad | Purpose | Notes |
|----------|--------|---------|-------|
| VTX + (power) | VBAT | Battery voltage power | Red wire typical, check TX800 voltage range (should support 6S) |
| VTX - (ground) | GND | Common ground | Black wire typical |

**Control Connections (UART1 - R1/T1 pads)**:

| VTX Wire | FC Pad | Purpose | Notes |
|----------|--------|---------|-------|
| VTX TX (audio out) | R1 | VTX transmits SmartAudio/Tramp to FC | Yellow/white wire typical |
| VTX RX (audio in) | T1 | FC transmits commands to VTX (optional) | Green/white wire typical, may not be needed for all protocols |

**Soldering Steps**:
1. Tin all VTX wires
2. Tin VBAT, GND, R1, T1 pads on FC
3. Solder VTX power (+) wire to VBAT pad
4. Solder VTX ground (-) wire to GND pad
5. Solder VTX TX wire to R1 pad (for SmartAudio/Tramp)
6. Solder VTX RX wire to T1 pad (if bidirectional control needed)
7. Verify all joints are secure
8. Apply heat shrink over exposed joints

**Final Wiring Check**:
- [ ] No wires touching propeller path
- [ ] All joints secure and insulated
- [ ] Antenna securely attached
- [ ] Camera securely mounted
- [ ] VTX mounted with standoffs (clearance verified)

### Step 5: Betaflight Configuration

**Ports Tab**:
1. Navigate to **Ports** tab in Betaflight
2. Find **UART1** row
3. Set peripherals based on TX800 protocol:
   - If **SmartAudio**: Select **VTX (TBS SmartAudio)**
   - If **IRC Tramp**: Select **VTX (IRC Tramp)**
4. Click **Save and Reboot**

**Video Transmitter Tab**:
1. Navigate to **Video Transmitter** tab
2. Enable VTX control
3. Configure VTX Table (5.8GHz bands and channels):
   - Band A (Boscam A): 5865, 5845, 5825, 5805, 5785, 5765, 5745, 5725 MHz
   - Band B (Boscam B): 5733, 5752, 5771, 5790, 5809, 5828, 5847, 5866 MHz
   - Band E (Boscam E): 5705, 5685, 5665, 5645, 5885, 5905, 5925, 5945 MHz
   - Band F (Fatshark/Airwave): 5740, 5760, 5780, 5800, 5820, 5840, 5860, 5880 MHz
   - Band R (Raceband): 5658, 5695, 5732, 5769, 5806, 5843, 5880, 5917 MHz
4. Set power levels:
   - Level 1: 25mW (pit mode for bench testing)
   - Level 2: 200mW (medium range)
   - Level 3: 800mW (maximum range)
5. Click **Save and Reboot**

**OSD Tab**:
1. Navigate to **OSD** tab
2. Configure OSD layout with desired elements:
   - **Critical**: Battery voltage, RSSI, flight time, armed indicator
   - **Useful**: Throttle position, altitude, GPS coordinates (if using GPS)
   - **Optional**: Current draw, mAh consumed, artificial horizon
3. Position elements on screen (drag and drop)
4. Click **Save**

### Step 6: Video System Testing

**Initial Power-Up** (CRITICAL SAFETY):
1. Verify antenna is connected to TX800 (NEVER power VTX without antenna)
2. Set VTX to **pit mode (25mW)** for initial testing
3. Power on aircraft with battery
4. Verify TX800 LED indicator (should show power/activity)

**Video Feed Test**:
1. Power on analog goggles and set to match TX800 frequency
2. Verify video feed appears in goggles
3. Check video quality (should be clear analog image)
4. Verify OSD elements appear on screen
5. Check for interference or noise

**SmartAudio/Tramp Control Test**:
1. Access VTX menu via OSD (stick commands or OSD menu)
2. Test changing VTX band/channel
3. Test changing VTX power level (25mW → 200mW → 800mW)
4. Verify changes take effect (goggles should show signal strength change)

**Range Test** (optional bench test):
1. Set VTX to 800mW
2. Walk away with goggles to test range
3. Verify video remains clear at expected distances

**Final Video Checks**:
- [ ] Video feed clear and stable
- [ ] OSD elements visible and accurate
- [ ] Battery voltage displayed correctly
- [ ] RSSI displayed correctly (from ELRS receiver)
- [ ] VTX power level changes work
- [ ] VTX channel changes work

**Completion**: MOD-002A complete when video feed is clear and all OSD/VTX controls work

---

## Phase 1 Completion Checklist

### MOD-001: ELRS Receiver
- [ ] Receiver physically mounted
- [ ] Antennas routed at 90° diversity
- [ ] Wired to UART2 (R2/T2/5V/GND)
- [ ] Betaflight configured (UART2 Serial RX, CRSF protocol)
- [ ] Bound to transmitter
- [ ] All control channels responding correctly
- [ ] Failsafe configured and tested
- [ ] RSSI displaying in OSD

### MOD-002A: Analog Video System
- [ ] TX800 bench tested (functional, no shorting)
- [ ] Camera mounted with appropriate angle
- [ ] TX800 mounted with standoffs (clearance verified)
- [ ] Antenna connected and secured
- [ ] Camera wired to VTX
- [ ] VTX wired to FC (VBAT/GND for power, R1/T1 for control)
- [ ] Betaflight configured (UART1 VTX, VTX table, OSD layout)
- [ ] Video feed clear and stable
- [ ] OSD elements displayed correctly
- [ ] SmartAudio/Tramp control working
- [ ] Power level switching tested (25/200/800mW)

### Pre-Flight Checks
- [ ] All solder joints secure and insulated
- [ ] No wires in propeller path
- [ ] All components secured (no loose parts)
- [ ] Battery connector secure
- [ ] Propellers installed correctly (check direction and tightness)
- [ ] FC status LEDs normal (Red, Orange, Green on power-up)
- [ ] GPS lock achieved (if applicable)
- [ ] Aircraft arms successfully (via transmitter switch)
- [ ] Aircraft disarms successfully (via transmitter switch)
- [ ] Motors spin in correct direction (test with props off!)

### Documentation Updates
- [ ] Update RD-59_AsBuilt_Parts_List.md (mark MOD-001 and MOD-002A as operational)
- [ ] Update RD-59_Modifications_Log.md (mark MOD-001 and MOD-002A as completed)
- [ ] Update RD-59_Build_Timeline.md (add installation completion date)
- [ ] Take photos of completed installation for reference

---

## Next Steps After Phase 1

Once Phase 1 is complete, proceed to:

1. **Pre-flight Testing**:
   - Bench test with battery (props off)
   - Verify motor directions
   - Test arm/disarm
   - Verify all flight modes (if configured)

2. **First Test Flight**:
   - Choose safe, open location
   - First hover test (LOS - line of sight)
   - First FPV test flight (short duration)
   - Evaluate performance (handling, video quality, flight time)

3. **Digital Upgrade Decision**:
   - If analog performance insufficient: choose MOD-002B (Walksnail) or MOD-002C (HDZero)
   - If analog performance satisfactory: skip digital upgrade, proceed to Phase 2 enhancements

4. **Phase 2 Enhancements** (optional):
   - MOD-003: RGB Arm LEDs
   - MOD-004: VIFLY GPS-mate Power Module

---

## Troubleshooting

### ELRS Receiver Issues

**Receiver not binding**:
- Verify RX/TX wires not swapped (receiver RX → FC T2, receiver TX → FC R2)
- Verify 5V power reaching receiver (check with multimeter)
- Verify UART2 enabled in Betaflight Ports tab
- Try different bind procedure (refer to ELRS documentation)

**No control inputs in Betaflight**:
- Verify receiver protocol set to CRSF in Configuration tab
- Verify receiver is bound (LED behavior)
- Check RX/TX wiring again

**Weak RSSI or range issues**:
- Verify antennas are intact and properly positioned
- Check for antenna blockage (carbon fiber, metal parts)
- Ensure antennas at ~90° diversity angle

### Analog Video Issues

**No video feed**:
- Verify antenna connected (CRITICAL - VTX damage if not connected)
- Verify VTX powered (check LED indicator)
- Verify camera powered (check for lens focus/activity)
- Check camera to VTX wiring (video signal connection)
- Try different channel/band on goggles

**Poor video quality/static**:
- Check for loose antenna connection
- Verify antenna not damaged
- Check for electrical interference (poor grounding)
- Verify camera lens clean and focused

**No OSD display**:
- Verify UART1 enabled for VTX in Betaflight Ports tab
- Verify SmartAudio/Tramp protocol selected correctly
- Check VTX TX wire to R1 pad connection
- Verify OSD enabled in Betaflight Configuration tab

**VTX not responding to commands**:
- Verify SmartAudio/Tramp wiring correct (VTX TX → FC R1)
- Try alternative UART (UART3 on R3/T3)
- Check VTX documentation for correct protocol

**TX800 overheating or shutting down**:
- Verify antenna connected (overheating indicates no antenna load)
- Check for short circuit to frame/FC
- Verify standoffs providing proper clearance
- Check voltage within TX800 specifications

---

## Safety Notes

### Critical Safety Rules

1. **NEVER power VTX without antenna connected** - Instant damage to VTX
2. **Always use proper standoffs for VTX** - Prevents shorting and damage
3. **Test with props off first** - Verify motor directions and control before flight
4. **Check for loose parts before powering** - Prevent shorts and damage
5. **Use proper battery connector** - XT60 on RD-59, verify polarity
6. **Monitor battery voltage** - Never discharge 6S LiPo below 3.3V per cell (19.8V total)

### Battery Safety

- **6S LiPo voltage ranges**:
  - Fully charged: 25.2V (4.2V per cell)
  - Nominal: 22.2V (3.7V per cell)
  - Low alarm: 21.0V (3.5V per cell) - land immediately
  - Critical: 19.8V (3.3V per cell) - risk of permanent damage

- Set low voltage alarm in Betaflight OSD (recommend 21.0V for 6S)

---

## Reference Documents

- **Modifications Log**: [RD-59_Modifications_Log.md](RD-59_Modifications_Log.md)
- **As-Built Parts List**: [RD-59_AsBuilt_Parts_List.md](RD-59_AsBuilt_Parts_List.md)
- **Build Timeline**: [RD-59_Build_Timeline.md](RD-59_Build_Timeline.md)
- **Factory Specs**: [reference/Nazgul_DC5_ECO_Factory_Specs.md](reference/Nazgul_DC5_ECO_Factory_Specs.md)
- **FC Wiring Diagram**: [reference/20231227025325BF14871BLITZATF435FCWiringDiagram20231005.pdf](reference/20231227025325BF14871BLITZATF435FCWiringDiagram20231005.pdf)

---

**Document Status**: Pre-Installation Planning Complete
**Last Updated**: 2025-11-10
**Next Update**: After Phase 1 installation completion
