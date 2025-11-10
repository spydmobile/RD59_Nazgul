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
| **Airworthiness** | ❌ NOT AIRWORTHY (parts on hand, pending installation) |
| **Parts Status** | All critical components acquired (July 24, 2025) |
| **Acquisition Date** | July 15, 2025 |
| **Test Flights** | 0 (not yet flown by current operator) |
| **Incidents** | 0 |
| **Modifications** | 0 completed, 5 pending |

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

**Installation Plan**: Install RX + Analog VTX → Get it flying → Evaluate → Upgrade if needed

### Phase 1: Critical (Install First - Analog for Maximum Flight Time)

1. ✓ **Install Receiver** (MOD-001) - HappyModel ELRS EP1 Dual RX
2. ✓ **Install Analog Video** (MOD-002A) - TX800 + Ratel 2 (lighter, 5-7 min flight time)
3. **Test flights** - Establish baseline with analog system

### Phase 1B: Optional Digital Upgrade (If Analog Insufficient)

- ✓ **Upgrade to Digital** (MOD-002B) - Walksnail Avatar HD (if needed)
- Trade-off: Better video quality, but 40-50% flight time penalty

### Phase 2: Optional Enhancements (After Flying)

1. *Optional*: Install RGB LEDs (MOD-003)
2. *Optional*: Install GPS-mate (MOD-004)

**Status**: All parts on hand. Starting with analog for best flight time, digital available if needed.

See [Modifications Log](./Documentation/RD-59_Modifications_Log.md) for detailed installation checklists and analog vs digital comparison.

---

## ℹ️ Important Notes

- **Source of Truth**: This repository contains verified technical specifications
- **Partial Build**: Aircraft acquired without video system or receiver
- **Untested**: All flight electronics are operational but untested by current operator
- **No Flight History**: Not yet flown by current operator since acquisition

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
