# Orchestra Criteria of Excellence
## Standard for All Chamber and Orchestral Compositions

### 1. RHYTHMIC PRECISION
- **Every measure must sum exactly to the time signature's total divisions**
  - 4/4 time: Exactly 48 divisions (12 divisions per quarter × 4 beats)
  - 3/4 time: Exactly 36 divisions (12 divisions per quarter × 3 beats)
  - 5/4 time: Exactly 60 divisions (12 divisions per quarter × 5 beats)
- **All tuplets (triplets, quintuplets, etc.) must be calculated correctly**
  - Triplets: 3 notes in time of 2 = proper duration distribution
  - Quintuplets: 5 notes in time of 4 = proper duration distribution with remainder handling
- **No rounding errors or missing divisions**
- **Verification: Every measure's note durations must sum to the exact measure duration**

### 2. HARMONIC COHERENCE
- **Consonant harmonies preferred over harsh dissonances**
- **Tonality Vault triad pairs: LH/RH combinations across instruments**
- **Smooth voice leading between chords**
- **Polychords and triad pairs distributed across all instrument families**
- **Key modulations must be musically logical and well-prepared**

### 3. MELODIC DEVELOPMENT
- **Clear, memorable motifs that develop organically**
- **Smooth morphing between motifs (no abrupt transitions)**
- **Melodic lines must be singable and flowing**
  - Primarily stepwise motion (2nds) for singability
  - Small leaps (3rds, 4ths) for interest
  - Large leaps (5ths+) only for dramatic effect
  - Clear melodic contour (arch, wave, ascending, descending)
- **Counter-melodies complement primary melodies**
  - Independent melodic lines in slow sections
  - Imitative entries (canon, fugato)
  - Inversion, retrograde, augmentation, diminution
- **Avoid excessive repetition - each measure should contribute to development**
- **Phrase structure:**
  - 4-measure phrases (antecedent-consequent)
  - 8-measure periods (question-answer)
  - Clear cadences (authentic, plagal, half)
  - Melodic sequences for development

### 4. STRUCTURAL INTEGRITY
- **Clear formal structure (e.g., Slow-Fast-Slow)**
- **Logical tempo changes with proper markings**
- **Time signature changes must be musically justified**
- **Key modulations serve the musical narrative**
- **Balanced phrase lengths and cadences**

### 5. ORCHESTRAL BALANCE
- **All instrument families utilized (winds, brass, strings)**
- **Proper range considerations for each instrument**
- **Correct transpositions (Bb clarinet, F horn)**
- **Appropriate clefs (treble, alto, bass)**
- **Dynamic balance across sections**
- **Rich dynamic contour:**
  - Dynamic markings every 2-4 measures
  - Crescendo/diminuendo hairpins (4-8 measures)
  - Terraced dynamics between sections
  - Subito dynamics for contrast
- **Articulations for expression:**
  - Legato (slurs) for melodic phrases
  - Staccato for light, playful passages
  - Tenuto for emphasized notes
  - Marcato for dramatic accents
  - Trills for ornamentation
  - Tremolo for texture
- **Expression marks:**
  - dolce, espressivo, cantabile, agitato, calmato
  - ritardando, accelerando, rubato, a tempo

### 6. NOTATION ACCURACY
- **Correct MusicXML structure**
- **No duplicate measure tags**
- **Proper measure numbering (1, 2, 3... no duplicates)**
- **All measures properly closed**
- **Correct note types, durations, and accidentals**
- **Proper slur, tie, and articulation markings**

### 7. MUSICAL INTEREST
- **Variety in rhythm, harmony, and texture**
- **Polyrhythms used effectively**
- **Contrast between sections**
- **Engaging melodic content**
- **Professional-level composition quality**
- **Textural variety:**
  - Solo (intimate) → Chamber (small groups) → Tutti (full orchestra)
  - Thin texture → Thick texture → Thin texture
  - High register → Low register → High register
  - Antiphonal (call and response) between sections
- **Counterpoint in slow sections:**
  - Multiple independent melodic lines
  - Imitative entries
  - Melodic bass lines (not just roots)
  - Layering: sparse → full → sparse
- **Section pacing:**
  - Avoid overly long sections (18-20 measures max per major section)
  - Add transitional measures between sections
  - Create frequent contrast (4-8 measure phrases)

### 8. TECHNICAL VERIFICATION
- **All measures verified to sum correctly before file generation**
- **Duration calculations tested for edge cases**
- **Remainder handling for non-even divisions**
- **File validates in professional notation software**
- **No structural errors or missing elements**

---

**Implementation Requirements:**
- Use `distribute_durations_evenly()` function for all variable-length note patterns
- Verify every measure with `verify_measure_total()` before closing
- Test all time signatures (4/4, 3/4, 5/4) independently
- Handle tuplets with proper `calculate_tuplet_durations()` function
- Never use simple integer division (`//`) without remainder handling

