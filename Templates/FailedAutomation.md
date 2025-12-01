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

## Future Solutions to Try (Ranked by Likelihood of Success)

### 🥇 1. Cubase Built-in Macro Recorder (BEST OPTION)
- **How:** Devices → Macros → Record actions within Cubase
- **Why best:** Native to Cubase, designed for this purpose, no external tools needed
- **Effort:** Low
- **Success likelihood:** High

### 🥈 2. MIDI Remote Scripts (JavaScript)
- **How:** Create scripts in `%APPDATA%\Steinberg\Cubase 15\MIDI Remote\`
- **Why good:** Official Cubase 15 scripting system, JavaScript-based
- **Effort:** Medium (requires learning the API)
- **Success likelihood:** High

### 🥉 3. Project Logical Editor (PLE)
- **How:** Use Cubase's built-in batch processing for track operations
- **Why good:** Native tool, can rename/color/organize tracks in bulk
- **Effort:** Low-Medium
- **Success likelihood:** Medium-High (limited to existing tracks)

### 4. AutoHotkey
- **How:** Windows automation with better timing control than pyautogui
- **Why good:** More robust, better window detection, widely used
- **Effort:** Medium
- **Success likelihood:** Medium

### 5. Detailed Track Archive Reverse-Engineering
- **How:** Analyze binary chunks in exported XML, replicate exact structure
- **Why good:** Would create importable files
- **Effort:** High (complex binary data)
- **Success likelihood:** Medium

### 6. Third-Party Tools
- **Options:** Vienna Ensemble Pro, Divisimate, template management tools
- **Why good:** Purpose-built for orchestral workflows
- **Effort:** Low (but may cost money)
- **Success likelihood:** Medium

### 7. Steinberg SDK / VST SDK
- **How:** Official development tools
- **Why last:** Requires developer license, complex, overkill for this task
- **Effort:** Very High
- **Success likelihood:** High (but not practical)

---

## Outcome

**Result:** Manual template creation required (30-40 minutes one-time setup).

**Files created:** Manual guides, track lists, and step-by-step instructions provided as alternative.

---

*Date: December 2025*

