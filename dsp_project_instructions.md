# Dyson Sphere Program — Production Planning Instructions

## Factory Building Levels & Speed Multipliers

All production buildings operate at a base speed multiplier. Higher-tier buildings run faster but require more advanced materials to construct.

### Assemblers
| Building | Speed Multiplier |
|---|---|
| Assembling Machine Mk.I | 0.75× |
| Assembling Machine Mk.II | 1.00× |
| Assembling Machine Mk.III | 1.50× |
| Re-Composing Assembler | 4.00× |

### Smelters
| Building | Speed Multiplier |
|---|---|
| Arc Smelter | 1.00× |
| Plane Smelter | 2.00× |
| Negentropy Smelter | 3.00× |

### Chemical Plants
| Building | Speed Multiplier |
|---|---|
| Chemical Plant | 1.00× |
| Quantum Chemical Plant | 2.00× |

### Other Production Buildings
| Building | Speed Multiplier |
|---|---|
| Oil Refinery | 1.00× |
| Matrix Lab (produce mode) | 1.00× |
| Miniature Particle Collider | 1.00× |
| Fractionator | 1.00× |

When calculating machine counts, divide the required rate by `(recipe output rate × building speed multiplier × proliferator multiplier)`. Default ratio analysis assumes **Assembling Machine Mk.II (1.00×)** and **Arc Smelter (1.00×)** unless otherwise specified.

---

## Recipe Data

### Source
All recipe data is sourced from the DSP wiki (`Module:Recipe/Data`) and stored in a minimal JSON format at:

```
https://raw.githubusercontent.com/troyfawkes/public/refs/heads/main/dsp_recipes.json
```

Always fetch this URL directly before doing any production chain calculations. If the URL is inaccessible, **do not fall back to wiki searches or cached knowledge** — ask the user to grant access to `raw.githubusercontent.com` before proceeding.

### Format
Each recipe entry contains:
- `id` — snake_case unique identifier
- `inputs` — map of item keys to quantities consumed per cycle
- `outputs` — map of item keys to quantities produced per cycle
- `time` — craft duration in **seconds** at 1× building speed
- `at` — producing building type: `assembler`, `smelter`, `chemical`, `refinery`, `collider`, `research`, `fractionator`

### Rare vs. Standard Resources

Some recipes have alternate versions that use **rare vein resources**. These are not available on all planets and require deliberate sourcing.

Rare resources include: `fire_ice`, `kimberlite_ore`, `fractal_silicon`, `grating_crystal`, `stalagmite_crystal`, `unipolar_magnet`, `organic_crystal` (vein variant).

**Default behavior:** Use only standard (non-rare) recipes unless a rare resource route is explicitly requested. When a rare resource route is used, flag it clearly in the production chain so the player knows that resource must be sourced and transported.

Alternate recipes using rare resources are identified by the `_advanced` suffix in their recipe `id` (e.g. `casimir_crystal_advanced`, `graphene_advanced`, `carbon_nanotube_advanced`).

### Chain Depth

A production chain covers the **target item and its direct recipe inputs — one level deep**. Stop expanding at any item whose inputs are raw resources (ores, crude oil, stone, coal, water). Do not expand further unless explicitly asked.

---

## Belt Speeds

Conveyor belt throughput is measured in **items per second**.

| Belt | Items / Second |
|---|---|
| Conveyor Belt Mk.I | 6 /s |
| Conveyor Belt Mk.II | 12 /s |
| Conveyor Belt Mk.III | 30 /s |

### Stackers (Automatic Piler)

An Automatic Piler placed on a belt merges two items into one stacked item, effectively **doubling the throughput** of the belt downstream of the piler. A second piler can stack again (4×).

| Configuration | Effective Mk.III Throughput |
|---|---|
| No stacker | 30 /s |
| 1× stacker (stack of 2) | 60 /s |
| 2× stackers (stack of 4) | 120 /s |

Stacked items are accepted directly by all buildings and stations — no unstacking is required. Use stackers freely on any belt to increase throughput without upgrading belt tier.

---

## Proliferation (Productivity Mode)

Proliferators sprayed onto input materials via a Spray Coater can either **speed up production** or **add extra output**. For factory design purposes, we **almost always use productivity mode** (extra products), not speed mode.

### Productivity Bonus by Proliferator Tier

| Proliferator | Extra Output |
|---|---|
| Proliferator Mk.I | +12.5% |
| Proliferator Mk.II | +20.0% |
| Proliferator Mk.III | +25.0% |

**Proliferator Mk.III is the standard assumption** unless otherwise noted. This means every machine effectively produces 1.25× its nominal output.

### Impact on Machine Counts

When proliferation is active, the **effective output rate** of each machine increases by the proliferator bonus. To hit a target throughput, you need **fewer machines** than the non-proliferated calculation suggests.

```
machines_needed = target_rate / (nominal_rate × speed_multiplier × 1.25)
```

Proliferators are delivered via **logistics bots** (see Logistics Philosophy) so they do not consume a PLS belt slot.

### Important Notes
- Proliferation applies to **inputs consumed**, not to recipe time. Power consumption increases.
- Fluids **can** be proliferated.
- Research matrices **can** be proliferated for extra output at the Matrix Lab.

---

## Logistics Stations

### Planetary Logistics Station (PLS)

- **Belt slots:** 12 total belt connections (inputs + outputs combined)
- **Item slots:** 4 — maximum 4 distinct items can be configured to request or supply
- **Drone slots:** up to 50 logistics drones
- Drones operate **within the same planet only**
- Each belt slot can carry up to 30 /s (Mk.III), or more with stackers

The 4-item slot limit is the primary design constraint. A module requiring 5+ distinct item flows must use **multiple PLS stations**. Multiple belt slots can be assigned to the same item to increase throughput (e.g. 4 belts × 30 /s = 120 /s for one item, consuming only 1 item slot).

### Interstellar Logistics Station (ILS)

- **Belt slots:** 12 total belt connections (inputs + outputs combined)
- **Item slots:** 5 — maximum 5 distinct items can be configured to request or supply
- **Drone slots:** up to 50 logistics drones (planetary)
- **Vessel slots:** up to 10 logistics vessels (interstellar)
- Can supply/demand items **across star systems**

### Key Constraint

A single belt slot on Mk.III carries **30 items/s**. Stackers multiply this without consuming additional slots. The **item slot count** (4 for PLS, 5 for ILS) is typically the binding design constraint, not the belt slot count.

---

## Logistics Philosophy

Factory design follows a three-tier logistics hierarchy:

### Tier 1 — Star System ILS Hub
A dedicated planet in each star system hosts an **Interstellar Logistics Station** that acts as the system-wide import/export hub.

### Tier 2 — Polar Planetary ILS Hub
Each production planet has a **polar ILS** that connects it to the star system hub.

### Tier 3 — Black Box PLS Designs
Individual production modules use one or more **Planetary Logistics Stations** as a self-contained black box. Each PLS module:
- Accepts input materials on its belt slots (demand)
- Outputs finished products on its belt slots (supply)
- Is designed around the **PLS item slot constraint** (4 distinct items max; use multiple PLS if more are needed)
- Is fully self-contained — internal ratios are balanced without relying on external buffering

### Proliferator & Low-Volume Item Delivery
- **Proliferators** are always delivered via **logistics bots**, never a belt slot. This frees all PLS slots for production materials.
- **Very low-throughput required items** (e.g. a single odd ingredient needed at <1 /s) may also be supplied via logistics bots to avoid wasting a full PLS belt slot on a near-empty belt.

---

## Clarifying Questions

Before producing a chain, ask the following — in a single message, not across multiple turns.

### Step 1 — Confirm or update assumptions
First ask: **"Use current defaults (Mk.II assembler / Arc smelter / Mk.III belt / Mk.III prolif / maximize belts / no input stacking)?"**

If yes, skip to Step 3. If no, ask Step 2.

### Step 2 — Collect tier and mode
Ask all of the following together:
- Belt tier (Mk.I / Mk.II / Mk.III)
- Assembler tier (Mk.I / Mk.II / Mk.III / Re-Composing)
- Smelter tier (Arc / Plane / Negentropy) — only if recipe involves smelting
- Design mode: maximize belts / target machine count / target output rate
- Input stacking level: do items arrive at the PLS pre-stacked? (none / 1× / 2×) — default: **none (30 /s per input belt)**

### Step 3 — Recipe-specific questions
Only ask if something is genuinely ambiguous from the request (e.g. a building name that also names a product, or a recipe with multiple variants). Skip entirely if the request is clear.

---

## Production Chain Guidance Format

When providing a production chain, present it in the following structure:

## Workings
Show all calculations: per-machine rates, belt ratio derivation, column sizing, output belt check, column count. This section is for transparency — keep it concise but complete.

**Column definition steps:**
1. Calculate consumption rate per machine for each input item
2. Find the ratio of those rates — this gives the natural belt ratio (e.g. 2:1 means 2 belts of item A per 1 belt of item B)
3. Find the smallest integer machine count where each input item's assigned belt count (per the ratio) is filled to ≥95% without exceeding capacity
4. The belts-per-column for each item is the integer from the ratio — all belts fill together at approximately the same utilization %
5. **Cap:** total belts per column (inputs + output) must not exceed **6**. If the natural ratio produces more than 6 belts per column, scale down proportionally until the total fits within 6, reserving 1 slot for the output. The user may override this cap explicitly.

Present the column definition as:

| Item | Consumption /machine/s | Belt ratio | Belts/column | Machines to fill | Belt utilization |
|---|---|---|---|---|---|

## Build Specification

### Recipe: [item name]
State building tier, belt tier, proliferator level, design mode, input stacking level, and any rare resource flags on a single summary line.

Then provide the Column Summary, Machine Count table, PLS tables, Output Belt Utilization, and Notes as described in the sections below.

### Column Summary
- X machines per column
- N columns
- X×N machines total
- Each column requires:
  - N× [item] belt
  - N× [item] belt
  - (repeat for all inputs)
  - 1× output belt (stacked if output /s per column exceeds the belt tier's maximum throughput)

### Machine Count Table

| Step | Recipe | Building | Machines | Output /s |
|---|---|---|---|---|

### PLS Allocation
Map every distinct item to a PLS item slot. Each PLS supports **4 distinct items**; split across multiple PLS stations numbered sequentially (PLS 1, PLS 2, etc.) as needed.

**Column count** = `floor(total belt slots / belts per column)`, where belts per column = input belts + output belts (each column has its own dedicated output belt connecting directly to the PLS).

An item may appear in multiple PLS stations (one item slot per station) to absorb otherwise-idle belt slots — preferred over leaving slots empty.

**PLS 1**
| Slot | Item | Belts | Individual Belt /s | Total Belt /s | Demand /s |
|---|---|---|---|---|---|

After all station tables, report:

- **Belt slots used:** X / Y total
- **Unused belt slots:** Z

### Output Belt Utilization
For each output belt, report individual belt capacity /s (applying 80% derating if stacked) and utilization % per belt.

### Notes
Call out any bottlenecks, rare resource dependencies, or design constraints.

---

## Production Module Design: PLS Belt Slot Constraints

A production module is **bounded by its PLS input/output belt slots**. Designing a module that overloads a belt slot, or uses more slots than the PLS has, is invalid.

### Rules

1. **Each PLS supports exactly 4 distinct item slots.** If a module requires more than 4 distinct item flows (inputs + outputs combined), it must use multiple PLS stations. Plan slot allocation explicitly before sizing the module.

2. **Each PLS has 12 belt connections.** Multiple belts can be assigned to the same item to scale throughput. For example, assigning 4 Mk.III belts to one item gives 120 /s on that item while consuming only 1 item slot.

3. **Each belt slot carries a maximum of 30 /s on Mk.III.** Use stackers to multiply throughput on a single belt without consuming additional item slots. Stacked items are accepted directly — no unstacking required.

4. **Do not build more machines than the input belts can feed.** Cap machine count to what the allocated input belts can supply — additional machines beyond that point are starved and wasted.

5. **Machine count is determined by the tighter of two constraints:**
   - The output throughput target, or
   - The input belt capacity (belts × 30 /s × stacker multiplier) divided by the recipe's input consumption rate

6. **All item flows — including fluids — use belt slots.** DSP has no pipes; all materials including liquids travel on conveyor belts and count against the item slot and belt budget.

7. **Output belt stackers are only 80% efficient.** Machines do not always fill stacked output belts evenly, so apply an 80% efficiency factor when calculating effective throughput on stacked output belts. For example, a stacked Mk.III output belt has a nominal capacity of 60 /s but should be sized assuming **48 /s** of reliable throughput. Input belt stackers are not subject to this derating.

8. **Design order:** Count distinct items required → assign to PLS item slots → allocate belt count per item → determine throughput ceiling (applying output stacker derating where applicable) → calculate machine counts → verify internal ratios balance at that throughput.

---

## Worked Example: antimatter

## Workings

**Recipe:** 2× critical_photon → 2× antimatter + 2× hydrogen, 2s, Miniature Particle Collider (1.00×, prolif +25%)

**Per-machine rates:**
- critical_photon consumed: 2/2 = 1.000 /s
- antimatter output: (2/2) × 1.25 = 1.250 /s

**Belt ratio:** 1 input only → 1 belt per column

**Machines to fill one input belt:** 30 / 1.000 = 30 machines → 100% utilization

**Output per column:** 30 × 1.250 = 37.5 /s — exceeds unstacked Mk.III (30 /s), requires 1× stacked output belt per column (48 /s effective, 78% utilized)

**Belts per column:** 1 input + 1 stacked output = 2 belts

**Column count:** floor(12 / 2) = 6 columns, 12 / 12 belt slots used

**Co-product handling:** hydrogen is a co-product and is discarded — no belt slot required.

---

## Build Specification

### Recipe: antimatter

**Miniature Particle Collider · Mk.III belt · Mk.III prolif · Maximize belts**

**Column summary:**
- 30 Particle Colliders per column
- 6 columns
- 180 Particle Colliders total
- Each column requires:
  - 1× critical_photon belt
  - 1× stacked output belt

**Machine Count**

| Step | Recipe | Building | Machines | Output /s |
|---|---|---|---|---|
| antimatter | 2 critical_photon → 2 antimatter | Miniature Particle Collider | 180 | 225 /s |

**PLS 1** (12 / 12 belt slots used)
| Slot | Item | Belts | Individual Belt /s | Total Belt /s | Demand /s |
|---|---|---|---|---|---|
| 1 | critical_photon | 6 | 30 /s | 180 /s | 180 /s |
| 2 | antimatter | 6 | 48 /s | 288 /s | 225 /s |

- **Belt slots used:** 12 / 12
- **Unused belt slots:** 0

**Output Belt Utilization**
- Each column: 37.5 /s on a 48 /s stacked belt = **78% per belt**

### Notes
- Hydrogen co-product is discarded — no belt slot required.
- Input belt utilization is exactly 100% — no headroom; critical_photon supply must be reliable.

---

## Worked Example: particle_container (advanced)

## Workings

**Recipe:** 10× unipolar_magnet + 2× copper_ingot → 1× particle_container, 4s, Mk.II Assembler (1.00×, prolif +25%)

**Per-machine rates:**
- unipolar_magnet: 10/4 = 2.500 /s
- copper_ingot: 2/4 = 0.500 /s
- particle_container output: (1/4) × 1.25 = 0.3125 /s

**Natural belt ratio:** 2.500 / 0.500 = 5:1 → 5 unipolar + 1 copper = 6 input belts + 1 output = 7 belts per column — exceeds 6-belt cap.

**Apply cap:** 6 total belts, reserve 1 output → 5 input belts. Distribute proportionally at 5:1 → 4 unipolar + 1 copper (closest integers fitting in 5).

**Machines per column:** 4 × 30 / 2.500 = 48 machines
- copper demand: 48 × 0.500 = 24 /s → 1 belt, 80% utilized ✓
- output: 48 × 0.3125 = 15 /s → below Mk.III belt speed (30 /s), unstacked ✓

**Column count:** floor(12 / 6) = 2 columns, 12 / 12 belt slots used

| Item | Consumption /machine/s | Belt ratio | Belts/column | Machines to fill | Belt utilization |
|---|---|---|---|---|---|
| unipolar_magnet | 2.500 | 4 | 4 | 48 | 100% |
| copper_ingot | 0.500 | 1 | 1 | 48 | 80% |

---

## Build Specification

### Recipe: particle_container (advanced)

**Mk.II Assembler · Mk.III belt · Mk.III prolif · Maximize belts · No input stacking · Rare resource: unipolar_magnet**

**Column summary:**
- 48 Assemblers per column
- 2 columns
- 96 Assemblers total
- Each column requires:
  - 4× unipolar_magnet belt
  - 1× copper_ingot belt
  - 1× output belt

**Machine Count**

| Step | Recipe | Building | Machines | Output /s |
|---|---|---|---|---|
| particle_container | 10 unipolar_magnet + 2 copper_ingot → 1 | Mk.II Assembler | 96 | 30 /s |

**PLS 1** (12 / 12 belt slots used)
| Slot | Item | Belts | Individual Belt /s | Total Belt /s | Demand /s |
|---|---|---|---|---|---|
| 1 | unipolar_magnet | 8 | 30 /s | 240 /s | 240 /s |
| 2 | copper_ingot | 2 | 30 /s | 60 /s | 48 /s |
| 3 | particle_container | 2 | 30 /s | 60 /s | 30 /s |

- **Belt slots used:** 12 / 12
- **Unused belt slots:** 0

**Output Belt Utilization**
- Each column: 15 /s on a 30 /s unstacked belt = **50% per belt**

### Notes
- unipolar_magnet is a rare vein resource — must be sourced and transported deliberately.
- Output belt is 50% utilized — a consequence of the 6-belt-per-column cap.
- copper_ingot at 80% per belt per column.
