# Failed Automation: Cubase Orchestral Template Builder

## Objective
Create an automated orchestral template builder for Cubase 15 using Sonuscore "The Orchestra" with the following structure:
- Woodwinds: Flute 1, Flute 2, Oboe, Clarinet in Bb, Bassoon (3 articulations each)
- Brass: Horns (2), Trumpets (2) (3 articulations each)
- Percussion: Timpani, Bass Drum, Snare Drum, Triangle, Cymbals/Tam-tam
- Keys/Harp: Harp, Piano/Celeste (3 articulations each)
- Strings: Violin I, Violin II, Viola, Cello, Double Bass (3 articulations each)

---

## Attempts & Failures

### 1. Track Archive XML Generation
**What:** Python script to generate Cubase Track Archive XML file for import via File → Import → Track Archive.

**Why it failed:**
- Cubase's Track Archive format is proprietary and undocumented
- Format uses `<tracklist2>` root with binary plugin data, GUIDs, and complex nested structures
- Three different XML format variations attempted—all rejected by Cubase with "Track Archive cannot be imported"

### 2. UI Automation (pyautogui)
**What:** Python script using pyautogui/pywin32 to control Cubase via simulated keyboard/mouse.

**Why it failed:**
- Python command not recognized (`python` vs `py`)
- Windows blocked Python installation (sideloading policy)
- Script ran but didn't create tracks—timing and menu navigation issues
- UI automation too fragile for complex DAW interaction

### 3. PowerShell/Batch Automation
**What:** Batch files to orchestrate Python scripts and open Cubase.

**Why it failed:**
- Dependent on Python scripts which didn't work
- No direct Cubase control available

---

## Root Causes

1. **No public Cubase API** for programmatic track creation
2. **Proprietary Track Archive format** not documented by Steinberg
3. **UI automation unreliable** for complex DAW workflows
4. **Environment issues** (Python paths, Windows policies)

---

## Future Solutions to Try

1. **Steinberg Remote API / MIDI Remote Scripts**
   - Investigate Cubase 15's MIDI Remote scripting capabilities
   - May allow programmatic control via JavaScript-like scripts

2. **Cubase Macro Recording**
   - Record macros within Cubase for track creation
   - Export and share macro sequences

3. **AutoHotkey with precise timing**
   - More robust Windows automation than pyautogui
   - Requires careful timing calibration per system

4. **Reverse-engineer real Track Archive**
   - Export a complete template manually from Cubase
   - Analyze XML structure in detail
   - Attempt to replicate exact format including binary chunks

5. **Steinberg SDK / VST SDK**
   - Investigate official development tools
   - May require developer license

6. **Third-party tools**
   - Research if tools like Vienna Ensemble Pro or other template managers offer automation

---

## Outcome

**Result:** Manual template creation required (30-40 minutes one-time setup).

**Files created:** Manual guides, track lists, and step-by-step instructions provided as alternative.

---

*Date: December 2025*

