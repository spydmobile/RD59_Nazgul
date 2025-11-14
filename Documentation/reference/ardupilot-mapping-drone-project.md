# ArduPilot Mapping Drone with ELRS MAVLink Telemetry
## Cable-Free Ground Control Station Setup

**Project Goal:** Build a custom autonomous mapping drone using ArduPilot with wireless MAVLink telemetry over ExpressLRS, eliminating the need for separate telemetry radios or cables between transmitter and laptop.

**Primary Use Case:** Aerial mapping and surveying for forestry/wildfire management applications

---

## System Architecture Overview

```
┌─────────────────────────────────────────────────────────┐
│                      AIRCRAFT                            │
│                                                          │
│  ┌─────────────────────────────────────────────────┐   │
│  │ Flywoo GOKU H743 PRO Mini Stack                  │   │
│  │ - H743 Flight Controller                         │   │
│  │ - 45A AM32 ESC (integrated)                      │   │
│  │ - ArduPilot Firmware                             │   │
│  │ - MAVLink configured on UART                     │   │
│  └──────────────┬──────────────────────────────────┘   │
│                 │                                        │
│                 │ UART Connection                        │
│                 │                                        │
│  ┌──────────────▼──────────────────────────────────┐   │
│  │ iFlight ELRS 2.4GHz 500mW TX Module              │   │
│  │ (Flashed with RECEIVER firmware)                 │   │
│  │ - RX-as-TX mode (ELRS 3.5+)                      │   │
│  │ - 500mW uplink power                             │   │
│  │ - MAVLink protocol mode                          │   │
│  └─────────────────────────────────────────────────┘   │
│                                                          │
└──────────────────────────┬───────────────────────────────┘
                           │
                           │ RF Link (2.4GHz ELRS)
                           │ • RC Control (uplink)
                           │ • MAVLink Telemetry (bidirectional)
                           │
┌──────────────────────────▼───────────────────────────────┐
│                   GROUND STATION                          │
│                                                           │
│  ┌────────────────────────────────────────────────┐     │
│  │ RadioMaster Boxer Transmitter                   │     │
│  │                                                 │     │
│  │  ┌──────────────────────────────────────────┐ │     │
│  │  │ Ranger Micro 2.4GHz ELRS TX Module       │ │     │
│  │  │ - 1W output power                        │ │     │
│  │  │ - WiFi Backpack enabled                  │ │     │
│  │  │ - MAVLink mode                           │ │     │
│  │  │ - Creates WiFi AP                        │ │     │
│  │  └─────────────┬────────────────────────────┘ │     │
│  │                │                                │     │
│  │                │ WiFi UDP (MAVLink)             │     │
│  └────────────────┼────────────────────────────────┘     │
│                   │                                       │
│                   │ Wireless Connection                   │
│                   │ No cables!                            │
│  ┌────────────────▼────────────────────────────────┐    │
│  │ Laptop / Tablet                                  │    │
│  │ - Mission Planner / QGroundControl               │    │
│  │ - Connects to "ExpressLRS TX Backpack XXXXXX"   │    │
│  │ - UDP port 14550                                 │    │
│  └──────────────────────────────────────────────────┘    │
│                                                           │
└───────────────────────────────────────────────────────────┘
```

---

## Hardware Bill of Materials

### Aircraft Components

| Item | Model | Purpose | Price | Notes |
|------|-------|---------|-------|-------|
| **Flight Controller Stack** | Flywoo GOKU H743 PRO Mini 45A AM32 20x20 | Flight control + ESC | $114.99 | H743 processor, 20x20 mounting, integrated 45A ESC |
| **ELRS TX Module** | iFlight ELRS 2.4GHz 500mW TX | Telemetry (flashed as RX) | ~$42.00 | Will be flashed with receiver firmware using RX-as-TX feature |
| **GPS Module** | Standard ArduPilot-compatible GPS | Position/navigation | ~$30-80 | UBLOX M8N/M9N or better |
| **Frame** | Your choice | Airframe | Varies | Based on your mapping mission requirements |
| **Motors** | Your choice | Propulsion | Varies | Match to frame and battery |
| **Battery** | LiPo 4S-6S | Power | Varies | Based on flight time requirements |

### Ground Station Components

| Item | Model | Purpose | Price | Status |
|------|-------|---------|-------|--------|
| **Transmitter** | RadioMaster Boxer 4-in-1 | RC control | - | ✅ You own this |
| **ELRS TX Module** | Ranger Micro 2.4GHz ELRS | 1W transmitter with WiFi | - | ✅ You own this |
| **Laptop/Tablet** | Your existing device | Ground control station | - | ✅ You own this |

### Additional Requirements

- **Antenna for aircraft ELRS TX:** Standard dipole or directional (comes with module)
- **Power wiring:** For connecting ELRS module to flight controller power
- **Mission Planner or QGroundControl** (free software)

**Total New Hardware Cost:** ~$157 (FC stack + ELRS TX module for aircraft)

---

## Software & Firmware Requirements

### Aircraft Side

1. **ArduPilot Firmware**
   - Version: Latest stable (4.5.x or newer)
   - Target: FlywooH743PRO or similar H743 target
   - Download: https://firmware.ardupilot.org/

2. **ELRS Firmware for TX Module**
   - Version: 3.5.0 or newer (required for RX-as-TX feature)
   - Configuration: Receiver firmware flashed to TX module
   - Tool: ExpressLRS Configurator

### Ground Station Side

1. **ELRS Firmware for Ranger Micro**
   - Version: 3.5.0 or newer
   - Configuration: MAVLink mode enabled
   - WiFi backpack enabled

2. **EdgeTX or OpenTX** (already on Boxer)
   - ELRS Lua script (latest version)

3. **Ground Control Station Software**
   - Mission Planner (Windows) or
   - QGroundControl (Windows/Mac/Linux/Android/iOS)

---

## Setup Process

### Phase 1: Flash & Configure Aircraft ELRS TX Module

This is the clever part - flashing a TX module with receiver firmware to get 500mW uplink power.

#### Step 1.1: Flash iFlight TX Module with Receiver Firmware

1. **Install ExpressLRS Configurator 3.5+**
   - Download from: https://github.com/ExpressLRS/ExpressLRS-Configurator/releases

2. **Connect iFlight ELRS TX module via USB**

3. **In Configurator:**
   - Select Device Category: `2.4 GHz`
   - Select Device: Find the iFlight TX model
   - **Enable "RX as TX" option** in advanced settings
   - Set your binding phrase (must match ground TX)
   - Select Regulatory Domain: `ISM_2400` (FCC) or `EU_CE_2400` (EU)

4. **Build & Flash**
   - Click "Build & Flash"
   - Wait for completion
   - Module now acts as a high-power receiver

#### Step 1.2: Physical Installation on Aircraft

1. **Mount ELRS module** near the flight controller
2. **Connect power:**
   - 5V from flight controller BEC
   - GND to flight controller ground
3. **Connect UART:**
   - ELRS TX → Flight Controller RX (e.g., SERIAL2_RX)
   - ELRS RX → Flight Controller TX (e.g., SERIAL2_TX)
4. **Connect antenna** to ELRS module (critical - don't power without antenna!)

---

### Phase 2: Configure Flight Controller

#### Step 2.1: Flash ArduPilot Firmware

1. **Connect flight controller via USB**
2. **Open Mission Planner**
3. **Flash firmware:**
   - Setup → Install Firmware
   - Select "Copter" (or Plane/Rover based on your frame)
   - Choose latest stable version
   - Wait for flash completion

#### Step 2.2: Configure UART for MAVLink

Using Mission Planner, set these parameters:

```
# Configure SERIAL2 for MAVLink (adjust SERIAL number based on your wiring)
SERIAL2_PROTOCOL = 2         # MAVLink2
SERIAL2_BAUD = 460800       # 460800 baud (required for ELRS MAVLink)

# Configure RSSI from ELRS
RSSI_TYPE = 5               # ReceiverProtocol (gets RSSI from MAVLink RC)

# Other important parameters
RC_OPTIONS = 8192           # Bit 13: Enable 420KBaud for ELRS (if needed)
```

**Write Parameters** and **Reboot** the flight controller.

---

### Phase 3: Configure Ground Station ELRS (Ranger Micro)

#### Step 3.1: Update Ranger Micro Firmware

1. **Power on Boxer with Ranger Micro installed**
2. **Enable WiFi on Ranger Micro:**
   - Via Lua script: `WiFi Connectivity → Enable WiFi`
   - Or via 5-way button if your module has one

3. **Connect to WiFi:**
   - SSID: `ExpressLRS TX`
   - Password: `expresslrs`

4. **Open web browser → http://10.0.0.1**

5. **Flash Latest Firmware:**
   - Download latest ELRS 3.5.x firmware
   - Upload via web UI
   - Set binding phrase (must match aircraft)
   - Flash firmware

#### Step 3.2: Configure for MAVLink Mode

Using EdgeTX/OpenTX on your Boxer:

1. **Access ELRS Lua Script:**
   - Long press SYS on Boxer
   - Navigate to ExpressLRS script

2. **Configure Link Settings:**
   - Select `Other Devices` → Your aircraft receiver
   - Set `Serial Protocol` to **MAVLink**
   - Back to main menu
   - Set `Link Mode` to **MAVLink** (not Normal)
   
3. **Configure Performance Settings:**
   - `Packet Rate`: F1000 or 333Hz Full (recommended for MAVLink)
   - `TX Power`: 1000mW (1W)
   - `Telemetry Ratio`: Will auto-set to 1:2 in MAVLink mode

4. **Enable WiFi Telemetry Forwarding:**
   - In Lua script: `Backpack` menu
   - Set `Telemetry` to **WiFi**
   - Ranger Micro will now forward MAVLink via WiFi

---

### Phase 4: Connect Ground Control Station

#### Step 4.1: Connect Laptop to Ranger Micro WiFi

1. **On your laptop, connect to WiFi:**
   - SSID: `ExpressLRS TX Backpack XXXXXX`
   - Password: `expresslrs`

2. **Alternative (Home WiFi):**
   - You can configure the backpack to connect to your home WiFi
   - More convenient if you're always flying from same location

#### Step 4.2: Configure Mission Planner

1. **Open Mission Planner**

2. **Set Connection Type:**
   - Top right corner: Select `UDP`
   - Port: `14550` (default)

3. **Click "Connect"**

4. **Mission Planner should:**
   - Connect automatically
   - Start downloading parameters
   - Display telemetry data
   - Show aircraft position (once GPS lock)

#### Step 4.3: Verify Everything Works

**Test RC Control:**
- Move sticks on Boxer → Should see response in Mission Planner
- Flight Mode switch → Should change modes in Mission Planner

**Test Telemetry:**
- Should see GPS data
- Battery voltage
- RSSI/Link quality
- All MAVLink telemetry

**Test Parameter Changes:**
- Try changing a parameter in Mission Planner
- Should write successfully to aircraft

---

## Expected Performance

### Link Performance (2.4GHz ELRS)

| Packet Rate | Data Rate | Latency | Recommended Use |
|-------------|-----------|---------|-----------------|
| **F1000Hz** | ~4000 bps | ~4ms | Parameter download, mission upload, mapping |
| **333Hz Full** | ~3500 bps | ~6ms | Good balance, recommended for mapping |
| **250Hz** | ~2500 bps | ~8ms | Longer range, good telemetry |
| **150Hz** | ~1500 bps | ~12ms | Extended range missions |

### Power Budget

**Aircraft Side:**
- ELRS TX at 500mW: ~2.5W power draw
- Uplink range: 10-30 km (depending on conditions)

**Ground Side:**
- Ranger Micro at 1W: ~5-7W power draw
- Downlink range: 30+ km

**Your bottleneck:** Aircraft's 500mW uplink (not the ground 1W downlink)

### Practical Range Expectations

For **mapping missions:**
- **Conservative range:** 5-10 km
- **Typical operating range:** 3-5 km
- **Line of sight required:** Yes (for safe mapping operations)

This is **more than adequate** for:
- Forestry surveying
- Wildfire damage assessment
- Terrain mapping
- Area reconnaissance

---

## Mission Planning for Mapping

### Mission Planner Workflow

1. **Create Survey Mission:**
   - Mission Planner → Flight Plan tab
   - Draw polygon around area to map
   - Auto WP → Survey (Grid)
   - Set altitude, overlap percentage, camera trigger
   - Upload mission via MAVLink

2. **Pre-Flight Checks:**
   - GPS lock (3D fix)
   - HDOP < 2.0
   - Battery voltage good
   - RC link solid (check RSSI)
   - MAVLink telemetry flowing

3. **Execute Mission:**
   - Arm in stabilize/loiter
   - Switch to Auto mode
   - Aircraft executes survey grid
   - Monitor progress in Mission Planner

4. **Data Collection:**
   - Camera triggers at waypoints
   - Telemetry logs saved (for georeferencing)
   - Return to home when complete

### Integration with Your Workflow

Since you work with:
- **Wildfire management** (Prometheus fire modeling)
- **Forest planning**
- **WebODM** (drone mapping)
- **Geospatial applications**

This setup gives you:
- ✅ Full autonomous waypoint missions
- ✅ Real-time telemetry monitoring
- ✅ Parameter adjustment in-flight
- ✅ Precise GPS logging for georeferencing
- ✅ No cables between transmitter and laptop
- ✅ Professional-grade flight control

---

## Advantages of This Setup

### vs. Traditional SiK/RFD900 Telemetry Radio:

| Feature | This Setup | Traditional Radio |
|---------|------------|-------------------|
| **Hardware cost** | $157 (reuses ELRS) | $200-400 (separate radios) |
| **Cables** | None (WiFi) | USB cable to laptop |
| **Dongles on laptop** | None | Telemetry radio required |
| **Complexity** | One RF link | Two separate links (RC + telem) |
| **Latency** | Very low (~4-8ms) | Higher (~50-100ms) |
| **Data rate at range** | Good (~2-4 kbps) | Similar |

### vs. Basic CRSF Telemetry:

- ✅ **Full MAVLink support** (not just basic telemetry)
- ✅ **Mission uploads** possible
- ✅ **Parameter changes** in field
- ✅ **Ground control station integration**
- ✅ **Professional workflow**

---

## Troubleshooting Guide

### Aircraft won't bind

**Check:**
- Binding phrase matches between TX and RX
- Both using same ELRS firmware version (3.5+)
- RX is actually flashed with receiver firmware
- Power and antenna connected properly

### No MAVLink telemetry

**Check:**
- `SERIAL2_PROTOCOL = 2` (MAVLink2)
- `SERIAL2_BAUD = 460800`
- TX/RX wires not swapped
- Link Mode set to **MAVLink** (not Normal) in Lua script
- Backpack telemetry set to **WiFi**

### Can't connect Mission Planner

**Check:**
- Connected to correct WiFi network
- UDP port 14550
- Aircraft powered and bound to TX
- MAVLink flowing from aircraft (check Lua script telemetry)

### Range is poor

**Check:**
- Antennas properly connected (especially aircraft)
- Antenna orientation (dipoles should be perpendicular)
- RF environment (interference, obstacles)
- Packet rate (lower = longer range)
- TX power settings

---

## Safety Notes

### Pre-Flight

- ✅ GPS 3D lock with good HDOP
- ✅ Compass calibrated
- ✅ Accelerometer calibrated  
- ✅ RC failsafe configured (RTH or Land)
- ✅ Battery voltage adequate
- ✅ Geofence configured (optional but recommended)
- ✅ Mission validated in simulator first

### In-Flight

- ⚠️ Maintain visual line of sight (regulations)
- ⚠️ Monitor RSSI/LQ (don't fly to edge of range)
- ⚠️ Always have RC override ready
- ⚠️ Monitor battery voltage
- ⚠️ Weather conditions appropriate

### Legal Compliance

- 📋 Follow Transport Canada drone regulations (Canada)
- 📋 Advanced operations certificate if required
- 📋 Maintain required documentation
- 📋 Respect airspace restrictions
- 📋 Privacy considerations for mapping

---

## Future Upgrades

### Optional Enhancements

1. **900MHz ELRS for extended range**
   - Dual-band LR1121 modules
   - 10-50+ km practical range
   - Better obstacle penetration

2. **Directional antenna on ground**
   - MOXON or patch antenna
   - Antenna tracker (auto-points at aircraft)
   - Significantly extends range

3. **Companion computer**
   - Raspberry Pi or similar
   - AI/computer vision for advanced missions
   - Real-time image processing

4. **RTK GPS**
   - Centimeter-level accuracy
   - Professional surveying grade
   - Integration with base station

---

## Resources

### Documentation

- **ArduPilot Wiki:** https://ardupilot.org/
- **ExpressLRS Docs:** https://www.expresslrs.org/
- **Mission Planner:** https://ardupilot.org/planner/
- **Flywoo Products:** https://flywoo.net/

### Communities

- **ArduPilot Discourse:** https://discuss.ardupilot.org/
- **ExpressLRS Discord:** https://discord.gg/expresslrs
- **Mission Planner Support:** ArduPilot forums

### Your Background Resources

- **WebODM:** For processing mapping imagery
- **QGIS:** For geospatial analysis
- **Your existing forestry/wildfire tools**

---

## Project Summary

**You're building:** A professional autonomous mapping drone with wireless telemetry

**Total new hardware cost:** ~$157 (FC + aircraft ELRS module)

**Key innovation:** Using Josh Bardwell's WiFi backpack technique eliminates all cables and separate telemetry hardware while maintaining professional capabilities

**Result:** A clean, cable-free ground station with full MAVLink telemetry for autonomous mapping missions in support of forestry management and wildfire applications.

---

**Questions or need clarification on any steps? This is a comprehensive build but very achievable given your 12+ years of UAV experience!**
