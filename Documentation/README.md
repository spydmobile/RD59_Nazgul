# RD-59 "Nazgul" Documentation Index

**Drone Designator**: RD-59
**Code Name**: Nazgul
**Operator**: SpyD (Franco Nogarin)
**Platform**: Nazgul DC5 ECO V1.1 - 5" Freestyle Quadcopter

---

## 🚨 Current Status (as of November 10, 2025)

| Status | Value |
|--------|-------|
| **Airworthiness** | ❌ NOT AIRWORTHY |
| **Flight Status** | Not yet flown by current operator |
| **Acquisition Date** | July 15, 2025 |
| **Days Since Acquisition** | 118 days |
| **Days Parts On Hand** | 109 days (since July 24, 2025) |
| **Test Flights** | 0 |
| **Total Incidents** | 0 |
| **Total Modifications** | 0 completed, 4 pending |

**Installation Plan**: Install RX + VTX → Get it flying → Everything else later

**Phase 1 - Critical** (on hand, ready to install):
- ✓ HappyModel ELRS EP1 Dual RX (MOD-001)
- ✓ Walksnail Avatar HD Moonlight VTX Kit (MOD-002)

**Phase 2 - Optional** (install after test flights):
- ✓ SpeedyBee RGB LEDs (MOD-003)
- ✓ VIFLY GPS-mate w/ Finder 2 (MOD-004)

---

## 📋 Quick Reference

### As-Purchased Configuration (July 15, 2025)

| Component | Status | Notes |
|-----------|--------|-------|
| **Frame** | ✓ Operational | Nazgul DC5 240mm DeadCat |
| **Flight Controller** | ✓ Operational | BLITZ ATF435 (untested) |
| **ESC** | ✓ Operational | BLITZ E55S 4-in-1 60A (untested) |
| **Motors** | ✓ Operational | XING-E Pro 2207 1800KV (x4, untested) |
| **GPS** | ✓ Operational | iFlight GPS |
| **Battery Connector** | ✓ Operational | XT60 with anti-spark |
| **Props** | ✓ Available | Nazgul F5 (5-inch) |
| **Receiver** | ❌ NOT INSTALLED | Never included, needs installation |
| **Video System** | ❌ REMOVED | DJI O4 stripped by previous owner |

### Key Differences from Factory Spec

| Component | Factory Spec | As-Purchased | Impact |
|-----------|-------------|--------------|--------|
| **Video System** | DJI O4 Air Unit Pro (4K) | REMOVED | No FPV capability |
| **Receiver** | Not included (sold separately) | Not included | No control capability |
| **Weight** | ~450g dry | ~420g dry (lighter without video) | Less weight |

---

## 📚 Primary Documentation

### Core Documents

1. **[RD-59_AsBuilt_Parts_List.md](./RD-59_AsBuilt_Parts_List.md)**
   - **Purpose**: Single source of truth for current configuration
   - **Use When**: Checking component specs, verifying configuration, planning repairs/upgrades
   - **Last Updated**: 2025-11-10
   - **Key Sections**: Operational components, missing components, pending installations

2. **[RD-59_Incident_Log.md](./RD-59_Incident_Log.md)**
   - **Purpose**: Comprehensive crash reports and damage tracking
   - **Use When**: After any crash, incident, or damage
   - **Incidents Recorded**: 0 (not yet flown)
   - **Key Sections**: Incident reports, damage assessments, repair tracking

3. **[RD-59_Modifications_Log.md](./RD-59_Modifications_Log.md)**
   - **Purpose**: Track all engineering changes and upgrades
   - **Use When**: Planning or completing any modification
   - **Modifications Recorded**: 0 completed, 2 pending (MOD-001: Receiver, MOD-002: Video System)
   - **Key Sections**: Planned modifications, completed modifications, rationale

4. **[RD-59_Build_Timeline.md](./RD-59_Build_Timeline.md)**
   - **Purpose**: Chronological project history and future planning
   - **Use When**: Tracking milestones, planning future work, reviewing history
   - **Project Duration**: 118 days since acquisition (July 15 - Nov 10, 2025)
   - **Key Sections**: Acquisition history, phases, milestones, lessons learned

---

## 📖 Reference Materials

### Factory Documentation

1. **[reference/Nazgul_DC5_ECO_Factory_Specs.md](./reference/Nazgul_DC5_ECO_Factory_Specs.md)**
   - **Purpose**: Original factory specifications from iFlight
   - **Use When**: Comparing to original spec, understanding design intent, verifying compatibility
   - **Key Information**: Complete factory specs, performance data, original components

---

## 🔗 External Resources

### Visual Documentation

- **Google Photos Album**: [RD-59 Photo Gallery](https://photos.google.com/album/AF1QipMQ81SgmNKcywQYFzFxxncO6l4DfiegxZddzp05)
  - Comprehensive photo documentation
  - Build process and assembly
  - Component details
  - Acquisition photos (July 14-15, 2025)

- **Local Photo Directory**: `/Users/franconogarin/localcode/spyd.com/public/drone-lab/drones/RD-59/googlePhotos/`
  - Local copies of acquisition photos
  - July 14-15, 2025 timestamps

---

## 🎯 Common Tasks

### Finding Information

**"What components are currently installed?"**
→ See [RD-59_AsBuilt_Parts_List.md](./RD-59_AsBuilt_Parts_List.md)

**"What parts do I need to buy?"**
→ See "Missing Components" section in [RD-59_AsBuilt_Parts_List.md](./RD-59_AsBuilt_Parts_List.md)
→ See pending modifications in [RD-59_Modifications_Log.md](./RD-59_Modifications_Log.md)

**"Has this aircraft crashed?"**
→ See [RD-59_Incident_Log.md](./RD-59_Incident_Log.md) (currently 0 incidents)

**"What modifications have been made?"**
→ See [RD-59_Modifications_Log.md](./RD-59_Modifications_Log.md) (currently 0 completed, 2 pending)

**"When was this aircraft acquired?"**
→ See [RD-59_Build_Timeline.md](./RD-59_Build_Timeline.md) (July 15, 2025)

**"What are the original factory specs?"**
→ See [reference/Nazgul_DC5_ECO_Factory_Specs.md](./reference/Nazgul_DC5_ECO_Factory_Specs.md)

---

## 📝 Documentation Standards

### When to Update Documents

**After Purchasing Parts**:
1. Update `RD-59_Modifications_Log.md` with order details
2. Change modification status to "PENDING"
3. Update `RD-59_Build_Timeline.md` with milestone

**After Installing Parts**:
1. Update `RD-59_AsBuilt_Parts_List.md` with new configuration
2. Update `RD-59_Modifications_Log.md` to "COMPLETED"
3. Update `RD-59_Build_Timeline.md` with completion date
4. Update this README with new status

**After a Crash**:
1. Create new incident report in `RD-59_Incident_Log.md`
2. Document all damage in assessment table
3. Update incident counter
4. Link to any modifications required for repair

**After Test Flights**:
1. Update `RD-59_Build_Timeline.md` with flight milestone
2. Add performance notes to `RD-59_AsBuilt_Parts_List.md`
3. Document any issues discovered

---

## 🚀 Next Steps

**To make RD-59 airworthy**:

1. **Select Receiver** (MOD-001)
   - Research ELRS receiver options
   - Purchase receiver system
   - See: [RD-59_Modifications_Log.md](./RD-59_Modifications_Log.md#mod-001)

2. **Select Video System** (MOD-002)
   - Decide: Analog vs Digital
   - Research options in chosen category
   - Purchase video system
   - See: [RD-59_Modifications_Log.md](./RD-59_Modifications_Log.md#mod-002)

3. **Installation**
   - Install receiver (MOD-001)
   - Install video system (MOD-002)
   - Configure in Betaflight/INAV
   - Bench test all systems

4. **Test Flights**
   - Pre-flight safety checks
   - First hover test
   - First FPV flight
   - Establish baseline performance

---

## ℹ️ Important Notes

**Source of Truth**:
- This repository is the authoritative source for RD-59 technical specifications
- All specs come from operator or verified factory documentation
- Do not trust external AI analysis or visual component identification

**Acquisition Context**:
- Aircraft purchased as partial build from Devon "Toasty" Felker
- DJI O4 video system was removed by previous owner before sale
- No receiver was ever installed (not included in factory package)
- All flight electronics are untested by current operator

**Pre-Acquisition History**:
- Previous owner: Devon "Toasty" Felker (Hay River)
- Flight history by previous owner: Unknown
- Any incidents by previous owner: Unknown
- Original factory build: iFlight

---

## 📧 Repository Information

**Repository**: RD59_Nazgul
**Location**: `/Users/franconogarin/localcode/RD59_Nazgul`
**Documentation**: `/Users/franconogarin/localcode/RD59_Nazgul/Documentation`
**Guidelines**: See `../CLAUDE.md` for documentation standards and assistant guidelines

---

**Last Updated**: November 10, 2025
**Maintained by**: SpyD (Franco Nogarin) with Claude Code
