# RD-59 "Nazgul" Documentation Repository

**Drone Designator**: RD-59
**Code Name**: Nazgul
**Operator**: SpyD (Franco Nogarin)
**Platform**: Nazgul DC5 ECO V1.1 - 5" Freestyle Quadcopter

This repository serves as the **authoritative source of truth** for RD-59 "Nazgul" - a Nazgul DC5 ECO V1.1 acquired from Devon "Toasty" Felker on July 15, 2025.

---

## 🚨 Current Status

| Status | Value |
|--------|-------|
| **Airworthiness** | ❌ NOT AIRWORTHY (VTX swap in progress) |
| **VTX Status** | TX800 removed (Dec 30, 2025) - failed bench test Nov 14. Harness + antenna still installed. |
| **Next Step** | Install GEPRC RAD Mini 1W (on hand) |
| **Acquisition Date** | July 15, 2025 |
| **Test Flights** | 0 (not yet flown by current operator) |
| **Incidents** | 0 |
| **Modifications** | 1 completed (RX), 1 in progress (VTX swap), 2 pending |

---

## 📖 Origins

**Acquisition Story**:

This aircraft was purchased from **Devon "Toasty" Felker** in Hay River on **July 15, 2025** for **$273.12 CAD**.

The aircraft is a **Nazgul DC5 ECO V1.1** (iFlight pre-built 5" freestyle drone) that was sold as a **partial build**:

- **Removed by previous owner**: DJI O4 Air Unit Pro (camera + VTX)
- **Never included**: Receiver (not part of factory package)
- **Included**: Frame, flight controller, ESC, motors, GPS, props, battery connector

This is where RD-59 Nazgul's story with the current operator begins.

---

## 📚 Documentation

Complete technical documentation is maintained in the `/Documentation/` directory:

### 📋 Core Documents

- **[Documentation/README.md](./Documentation/README.md)** - Documentation hub and quick reference
- **[RD-59_AsBuilt_Parts_List.md](./Documentation/RD-59_AsBuilt_Parts_List.md)** - Current configuration and component inventory
- **[RD-59_Incident_Log.md](./Documentation/RD-59_Incident_Log.md)** - Crash reports and damage tracking
- **[RD-59_Modifications_Log.md](./Documentation/RD-59_Modifications_Log.md)** - Engineering changes and upgrades
- **[RD-59_Build_Timeline.md](./Documentation/RD-59_Build_Timeline.md)** - Project history and milestones

### 📖 Reference Materials

- **[Factory Specifications](./Documentation/reference/Nazgul_DC5_ECO_Factory_Specs.md)** - Original iFlight specifications

### 🔗 External Resources

- **Photo Gallery**: [Google Photos Album](https://photos.google.com/album/AF1QipMQ81SgmNKcywQYFzFxxncO6l4DfiegxZddzp05)
- **Local Photos**: `/Users/franconogarin/localcode/spyd.com/public/drone-lab/drones/RD-59/`

---

## 🎯 Quick Links

**Starting Point**: 👉 [**Documentation/README.md**](./Documentation/README.md)

**Need to know**:

- Current configuration? → [As-Built Parts List](./Documentation/RD-59_AsBuilt_Parts_List.md)
- Crash history? → [Incident Log](./Documentation/RD-59_Incident_Log.md)
- Modifications made? → [Modifications Log](./Documentation/RD-59_Modifications_Log.md)
- Project timeline? → [Build Timeline](./Documentation/RD-59_Build_Timeline.md)

---

## 🚀 Next Steps to Airworthiness

**Current State**: TX800 failed bench test (Nov 14) and removed (Dec 30). Camera, harness, and antenna remain installed. RAD Mini ready.

### Phase 1: Critical (VTX Swap)

1. ✓ **Install Receiver** (MOD-001) - HappyModel ELRS EP1 Dual RX - COMPLETE
2. ⚠️ **VTX Swap** (MOD-002A) - TX800 FAILED → GEPRC RAD Mini 1W
   - ✓ TX800 removed (Dec 30, 2025)
   - ✓ Ratel 2 camera installed
   - ✓ Harness + TrueRC antenna in place
   - ⏳ Install RAD Mini (rewire power from 5V to VBAT)
   - ⏳ Bench test video
   - ⏳ Bind ELRS receiver
3. **Test flights** - Establish baseline with analog system

### Phase 1B: Optional Digital Upgrade (If Analog Insufficient)

- **Walksnail Avatar HD** (MOD-002B) - on hand as backup if needed
- Trade-off: Better video quality, but 40-50% flight time penalty

### Phase 2: Optional Enhancements (After Flying)

1. *Optional*: Install RGB LEDs (MOD-003)
2. *Optional*: Install GPS-mate (MOD-004)

**Status**: RAD Mini on hand. Swap requires power wire move (5V → VBAT) then bench test.

See [Modifications Log](./Documentation/RD-59_Modifications_Log.md) for detailed installation checklists and analog vs digital comparison.

---

## ℹ️ Important Notes

- **Source of Truth**: This repository contains verified technical specifications
- **Partial Build**: Aircraft acquired without video system or receiver
- **RX Installed**: ELRS EP1 Dual RX installed Nov 13, 2025 - needs binding
- **VTX Swap In Progress**: TX800 failed (Nov 14) and removed (Dec 30). RAD Mini ready to install.
- **Untested**: Not yet flown by current operator since acquisition

---

## 📧 For Claude Code Assistants

See **[CLAUDE.md](./CLAUDE.md)** for detailed instructions on:

- Your role as RD-59 Archivist & SME
- Documentation standards and procedures
- How to work with the operator
- Repository structure and guidelines

---

**Repository Established**: November 10, 2025
**Maintained by**: SpyD (Franco Nogarin) with Claude Code
