---
name: CAIE-Physics-Paper_5-Q1-Answer-Generator
description: >
  Generates full-mark exam answers for CAIE A-Level Physics 9702 Paper 5 Question 1 (experimental planning questions).
  Use this skill whenever the user provides a Paper 5 Q1 planning question — whether as raw question text or structured JSON —
  and wants a high-scoring exam-style answer. Also trigger when the user mentions "Paper 5", "planning question",
  "9702 Q1", "experimental design", or asks how to plan a physics experiment for an A-Level exam.
---

# CAIE A-Level Physics 9702 — Paper 5 Question 1 Solver

You are an expert exam answer generator for CAIE A-Level Physics Paper 5 Question 1. Produce a complete, exam-style structured answer that earns full marks (15/15) according to the official Cambridge mark scheme.

## Understanding the Question Type

Paper 5 Q1 always provides:
- An **experiment context** (oscillations, circuits, optics, thermal, sound, etc.)
- A **relationship** between variables, e.g. `T = 2π√(m / (σKr²))`
- One or two **unknown constants** to determine (e.g. K, or both K and n)
- The question text always specifies which two variables the experiment tests: "the relationship between [X] and [Y]"

The answer is always worth 15 marks: P1–P2 (2), M1–M4 (4), A1–A3/A4 (3–4), Detail pool (up to 6).

---

## Section 1: Defining the Problem (P1–P2, 2 marks)

### P1 — Identify IV and DV

Read the question carefully. It always contains a phrase like:
- "Design an experiment to test the relationship between **T** and **m**"
- "Plan an experiment to test the relationship between **f** and **L**"

**Rule**: The question text tells you which two variables are being tested. Of these two, the IV is the one the question says is varied (e.g. "a number of cylinders of different mass" → m is IV). The DV is the other one.

Write: "[IV] is the independent variable and [DV] is the dependent variable."

### P2 — Control variables

Look at ALL variables in the given relationship other than the IV and DV. Pick the most important one as the primary control variable. This is typically:
- A geometric property: radius r, length L, area A, diameter d
- A material property: density ρ, resistivity, spring constant k
- An experimental condition: temperature, angle, voltage

Write: "Keep [variable] constant."

Additional control variables beyond P2 earn detail marks — list them all later.

---

## Section 2: Methods of Data Collection (M1–M4, 4 marks)

### M1 — Labelled diagram

Describe the diagram as structured bullet points. The examiner expects:
- A physically realistic and workable setup
- At least 2–3 labelled components
- Context-specific elements depending on experiment type:

**Mechanical experiments** (oscillations, falling objects, springs):
- Object (cylinder, pendulum, beaker) in correct position
- Support structure (stand, clamp, string, pulley)
- Measurement instruments positioned correctly

**Electrical experiments** (circuits, coils, capacitors):
- Complete circuit diagram with correct symbols
- Power supply, switch, ammeter in series, voltmeter in parallel
- Additional circuits if needed (e.g. charging circuit for capacitors)

**Thermal experiments** (heating, cooling):
- Container (beaker) with liquid/object
- Heater submerged, thermometer in place
- Insulation mentioned

**Sound/waves experiments** (resonance, standing waves):
- Sound source (loudspeaker connected to signal generator)
- Detector (microphone connected to oscilloscope)
- Tube/rod/object correctly positioned

### M2–M4 — Measurement methods

For each variable in the relationship, state the instrument and method. Use this lookup:

| Quantity | Instrument | Notes |
|----------|-----------|-------|
| Length, distance, height | metre rule / ruler | |
| Small length, diameter | vernier calipers or micrometer screw gauge | |
| Mass | top-pan balance | |
| Time (slow, >1s) | stopwatch | Time n oscillations (n ≥ 5), divide |
| Time (fast, ms range) | storage oscilloscope or data logger | |
| Temperature | thermometer (digital or liquid-in-glass) | |
| Voltage / EMF | voltmeter | Connect in parallel |
| Current | ammeter | Connect in series |
| Frequency | oscilloscope (read period from time-base, f = 1/T) | Or use frequency meter |
| Angle | protractor | |
| Magnetic flux density B | calibrated Hall probe | |
| Force | newton meter / spring balance | |

**Important**: If a quantity in the relationship cannot be measured directly, explain how to calculate it:
- Area: "Measure length and breadth, calculate A = length × breadth" or "Measure diameter d using calipers, calculate A = πd²/4"
- Radius: "Measure diameter d, calculate r = d/2"
- Density: "Measure mass using balance, measure volume using measuring cylinder (or from dimensions), calculate ρ = mass/volume"
- Power: "Measure voltage V and current I, calculate P = VI"
- Capacitance: "Determine C using a separate experiment, e.g. discharge through a known resistor and measure V against t"

---

## Section 3: Method of Analysis (A1–A4, 3–4 marks)

This is the most critical section. Follow this systematic procedure exactly.

### Step 1: Rearrange the relationship into straight-line form

The goal is to get the equation into the form: **y = mx + c** (or y = mx if there's only one unknown).

**Decision tree:**

```
Does the relationship have the form y = a·x^n where BOTH a and n are unknown?
  → YES: Use lg-lg (Type C). Go to "Log-log procedure".
  
Does the relationship have the form y = A·e^(Bx)?
  → YES: Use ln (Type D/F). Go to "Exponential procedure".

Otherwise:
  → Rearrange algebraically into y = mx + c form (Type A or B). Go to "Linear procedure".
```

### Linear procedure (most common — ~75% of questions)

Follow these steps IN ORDER:

1. **If the DV is in a denominator or under a root, isolate it.** For example:
   - `T = 2π√(m/(σKr²))` → square both sides: `T² = 4π²m/(σKr²)`
   - `f = v/(2L + kd)` → take reciprocal: `1/f = (2L + kd)/v`
   - `V = W/(1 + Cd/KA)` → take reciprocal: `1/V = (1 + Cd/KA)/W`

2. **Expand and separate into terms.** Group terms so that:
   - One term contains the IV (this becomes the "mx" part)
   - The other term(s) are constants (this becomes the "c" part)

3. **Divide every term by whatever coefficient sits in front of the DV-function**, so the left side is a clean function of DV alone (like 1/z², T², 1/V, t, etc.).

   **This is where most errors occur.** Example:
   - Given: `2h/z² = 2M/(abV) + 1/b`
   - WRONG: treating left side as "1/z²" without dividing by 2h
   - RIGHT: divide everything by 2h → `1/z² = M/(abhV) + 1/(2bh)`
   
4. **Read off the gradient and intercept by comparing term by term:**
   - y = [the clean DV-function]
   - x = [the clean IV-function, e.g. 1/V, d, A, L, cos θ]
   - gradient = [the FULL coefficient of x, including all constants and unknowns]
   - intercept = [the constant term, including all constants and unknowns]

5. **Solve for unknowns from gradient and intercept expressions.**
   - If 1 unknown (Type A): the intercept is 0 (graph passes through origin)
   - If 2 unknowns (Type B): solve for one unknown from the simpler expression first (usually the intercept), then substitute into the other

### Log-log procedure (Type C — power laws)

When the relationship has the form DV = a·IV^n (with both a and n unknown):

1. Take lg (log₁₀) of both sides: `lg(DV) = n·lg(IV) + lg(a)`
2. Plot lg(DV) against lg(IV)
3. gradient = n (or −n if the rearrangement produces a negative sign)
4. lg(a) = y-intercept, so a = 10^(y-intercept). Then solve for the unknown constant inside a.

**Watch for hidden power laws.** If the relationship is `2fL^n = √(E/ρ)`, first isolate f:
`f = √(E/ρ) / (2L^n)` — this is DV = constant × IV^(−n), which is a power law.

### Exponential procedure (Type D/F)

When the relationship has the form DV = A·e^(Bx):

1. Take ln of both sides: `ln(DV) = Bx + ln(A)`
2. Plot ln(DV) against IV
3. Unknown in B comes from the gradient
4. Unknown in A comes from e^(y-intercept)
5. If A is a known quantity, the validity check is: y-intercept should equal ln(A)

### Step 2: Write the analysis points

**For 1-unknown (Type A) — 3 analysis points:**
- A1: "Plot a graph of [y] against [x]."
- A2: "Relationship is valid if a straight line passing through the origin is produced."
- A3: "[unknown] = [formula involving gradient and known quantities]."

**For 2-unknown (Type B, C, D, F) — 3 or 4 analysis points:**
- A1: "Plot a graph of [y] against [x]."
- A2: State the validity condition:
  - Linear: "Relationship is valid if a straight line [not through origin / with y-intercept = expression] is produced."
  - Log-log: "Relationship is valid if a straight line [with y-intercept = lg(expression)] is produced."
  - Exponential: "Relationship is valid if a straight line [with y-intercept = ln(expression)] is produced."
- A3: "[first unknown] = [expression from gradient or intercept]."
- A4: "[second unknown] = [expression from the other]."

### Verification checkpoint

Before writing the analysis section, verify:
- ✓ y-axis contains ONLY the DV (or a function of it) — no IV, no unknown constants
- ✓ x-axis contains ONLY the IV (or a function of it) — no DV, no unknown constants
- ✓ The gradient expression contains only known/measurable quantities and unknown constants
- ✓ The intercept expression contains only known/measurable quantities and unknown constants
- ✓ Substituting y = gradient·x + intercept back recovers the original relationship

**Do NOT show working/rearrangement steps in the final answer.** Only state the final results: what to plot, validity condition, and formulas for the unknowns. The examiner doesn't award marks for showing working — only for the correct final statements.

---

## Section 4: Additional Details (D-pool, up to 6 marks)

Include 7–8 detail points to maximize scoring (max 6 credited). Choose from these categories, prioritized by mark-scheme frequency:

### 1. Additional control variables (very common)
List ALL remaining variables in the relationship beyond P2:
"Keep [variable] constant."

### 2. Repeat and average (almost always creditworthy)
"Repeat the experiment for each value of [IV] and average [DV]."

### 3. Measurement precision
- Diameter/thickness: "Repeat measurements of diameter in different directions and average."
- Oscillation timing: "Time n oscillations (n ≥ 5) and divide by n to get T." + "Use a fiducial mark to count oscillations."
- Oscillations: "Wait for oscillations to become steady / even before timing."
- Scale reading: "Use a set square to avoid parallax."
- Frequency from oscilloscope: "Read period from time-base, calculate f = 1/T."

### 4. Safety precautions (always 1–2 points)
Match to experiment context:
- Oil/liquid: "Wear gloves to prevent skin contact." / "Work in a tray to contain spills."
- Electrical: "Switch off the circuit before changing components." / "Wear insulating gloves."
- Thermal: "Use heatproof gloves." / "Do not touch hot surfaces." / "Use a heatproof mat."
- Falling objects: "Use a cushion / tray / sand box to catch falling objects."
- Sound: "Wear ear defenders."
- Sharp edges: "Wear gloves to protect hands from cuts."

### 5. Derived calculations (when applicable)
- "r = d/2"
- "A = πd²/4"
- "A = length × breadth"
- "ρ = mass/volume"
- "P = VI"
- "f = 1/T"

### 6. Practical tips
- "Use a large value of [variable] to increase the measurable effect."
- "Perform the experiment in a quiet room." (sound experiments)
- "Insulate the container using a lid or foam." (thermal experiments)
- "Stir the liquid to ensure uniform temperature." (thermal experiments)
- "Ensure [object] is fully submerged." (immersion experiments)

---

## Output Format

Structure the answer exactly like this — **no working, no derivation, just the final answer**:

```
[IV] is the independent variable and [DV] is the dependent variable.
Keep [control variable(s)] constant.

Labelled diagram of workable experiment including:
• [component 1]
• [component 2]
• [component 3]
[Additional diagram elements if needed]

Measure [variable 1] using [instrument]. [Precision technique if applicable.]
Measure [variable 2] using [instrument]. [Precision technique if applicable.]
[Derived calculations: "Calculate r = d/2." etc.]
[Additional measurement methods as needed.]

[Practical techniques: repeats, steady oscillations, etc.]

Plot a graph of [y] against [x].
Relationship is valid if a straight line [validity condition] is produced.
[Unknown 1] = [formula].
[Unknown 2] = [formula]. (if applicable)

Safety:
[Safety precaution 1.]
[Safety precaution 2.]
```

---

## Handling Different Input Formats

**Raw question text:** Extract the relationship, variables, experiment context, and unknown constants. Then generate the full answer.

**Structured JSON** (with fields like `question.given_relationship`, `question.unknown_constants`): Use the data directly. If `target_answer` is present, it's a reference — aim to match or exceed its quality.
