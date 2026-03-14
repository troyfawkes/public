# DSP — Utility Production Chain
## Space Warpers (100/s) + Proliferator Mk.III (covers 25/s white science build)

**Defaults:** Re-Composing Assembler (4.00×) · Negentropy Smelter (3.00×) · Quantum Chemical Plant (2.00×) · Matrix Lab (1.00×) · Oil Refinery (1.00×) · Miniature Particle Collider (1.00×) · Mk.III Belt with 4× stacking (120/s, 100% efficiency) · Mk.III Proliferator (+25% output)

**Hydrogen & Deuterium:** Supplied by Orbital Collectors. Assumptions: VU level 5, gas giant displays 1.5/s hydrogen and 0.3/s deuterium. At VU5 each collector yields 15.22/s net hydrogen and 3.04/s net deuterium. Deuterium demand is 27.5/s (binding), requiring **10 collectors**. Hydrogen net demand is 46.875/s, requiring **4 collectors** — deuterium remains the binding constraint at 10 collectors, producing 30.4/s deuterium and 152/s hydrogen against 27.5/s and 46.875/s required respectively.

**Proliferator consumption:** Mk.III gives 60 sprays per unit; proliferated Mk.III gives 75 sprays per unit. Total demand is 18.956/s: 7.493/s for the 25/s white science chain and 11.463/s for this utility chain itself.

---

## Space Warper + Gravity Matrix Chain

| Recipe | Building | Machines | Items Produced | Output /s | Mk.III Belts (4×) | Consumed by |
|---|---|---|---|---|---|---|
| space_warper_advanced | Re-Composing Assembler | 25 | space_warper | 100.000 | 1 | Export |
| gravity_matrix | Matrix Lab | 97 | gravity_matrix | 10.104 | 1 | space_warper_advanced |
| graviton_lens | Re-Composing Assembler | 5 | graviton_lens | 4.167 | 1 | gravity_matrix |
| quantum_chip | Re-Composing Assembler | 5 | quantum_chip | 4.167 | 1 | gravity_matrix |
| plane_filter | Re-Composing Assembler | 16 | plane_filter | 6.667 | 1 | quantum_chip |
| casimir_crystal | Re-Composing Assembler | 5 | casimir_crystal | 6.250 | 1 | plane_filter |
| titanium_glass | Re-Composing Assembler | 6 | titanium_glass | 12.000 | 1 | plane_filter |
| strange_matter | Collider | 22 | strange_matter | 3.438 | 1 | graviton_lens |
| particle_container | Re-Composing Assembler | 5 | particle_container | 6.250 | 1 | strange_matter |
| electromagnetic_turbine | Re-Composing Assembler | 4 | electromagnetic_turbine | 10.000 | 1 | particle_container |
| electric_motor | Re-Composing Assembler | 7 | electric_motor | 17.500 | 1 | electromagnetic_turbine |
| gear | Re-Composing Assembler | 3 | gear | 15.000 | 1 | electric_motor |
| magnetic_coil | Re-Composing Assembler | 3 | magnetic_coil | 30.000 | 1 | electromagnetic_turbine, electric_motor |
| processor | Re-Composing Assembler | 4 | processor | 6.667 | 1 | quantum_chip |
| microcrystalline_component | Re-Composing Assembler | 5 | microcrystalline_component | 12.500 | 1 | processor |
| circuit_board | Re-Composing Assembler | 2 | circuit_board | 20.000 | 1 | processor |
| titanium_crystal | Re-Composing Assembler | 4 | titanium_crystal | 5.000 | 1 | casimir_crystal |
| organic_crystal | Quantum Chemical Plant | 10 | organic_crystal | 4.167 | 1 | titanium_crystal |
| graphene | Quantum Chemical Plant | 13 | graphene | 21.667 | 1 | casimir_crystal, particle_container |
| sulfuric_acid | Quantum Chemical Plant | 6 | sulfuric_acid | 10.000 | 1 | graphene |
| plastic | Quantum Chemical Plant | 8 | plastic | 6.667 | 1 | organic_crystal |
| high_purity_silicon | Negentropy Smelter | 11 | high_purity_silicon | 20.625 | 1 | microcrystalline_component |
| diamond | Negentropy Smelter | 8 | diamond | 15.000 | 1 | graviton_lens |
| glass | Negentropy Smelter | 6 | glass | 11.250 | 1 | titanium_glass |
| titanium_ingot | Negentropy Smelter | 12 | titanium_ingot | 22.500 | 1 | titanium_glass, titanium_crystal |
| energetic_graphite | Negentropy Smelter | 24 | energetic_graphite | 45.000 | 1 | graphene, plastic, diamond |
| iron_ingot | Negentropy Smelter | 17 | iron_ingot | 63.750 | 1 | circuit_board, electric_motor, gear, strange_matter |
| copper_ingot | Negentropy Smelter | 11 | copper_ingot | 41.250 | 1 | magnetic_coil, microcrystalline_component, circuit_board, particle_container |
| magnet | Negentropy Smelter | 10 | magnet | 25.000 | 1 | magnetic_coil |
| plasma_refining | Oil Refinery | 42 | refined_oil (26.250), hydrogen co-product (13.125) | 26.250 | 1 | sulfuric_acid, plastic, organic_crystal |
| iron_ore | Raw | - | iron_ore | 71.000 | 1 | iron_ingot, magnet |
| copper_ore | Raw | - | copper_ore | 33.000 | 1 | copper_ingot |
| silicon_ore | Raw | - | silicon_ore | 33.000 | 1 | high_purity_silicon |
| coal | Raw | - | coal | 72.000 | 1 | energetic_graphite |
| titanium_ore | Raw | - | titanium_ore | 36.000 | 1 | titanium_ingot |
| stone | Raw | - | stone | 34.000 | 1 | sulfuric_acid, glass |
| water | Raw | - | water | 20.933 | 1 | titanium_glass, sulfuric_acid, organic_crystal |
| crude_oil | Raw | - | crude_oil | 21.000 | 1 | plasma_refining |
| hydrogen | Raw (Orbital Collector) | 10 collectors | hydrogen | 46.875 | 1 | casimir_crystal (60.000) — net of plasma_refining co-product (13.125) |
| deuterium | Raw (Orbital Collector) | 10 collectors | deuterium | 27.500 | 1 | strange_matter |

---

## Proliferator Mk.III Chain

| Recipe | Building | Machines | Items Produced | Output /s | Mk.III Belts (4×) | Consumed by |
|---|---|---|---|---|---|---|
| proliferator_mk3 | Re-Composing Assembler | 8 | proliferator_mk3 | 20.000 | 1 | Spray Coaters (white science + utility) |
| proliferator_mk2 | Re-Composing Assembler | 7 | proliferator_mk2 | 35.000 | 1 | proliferator_mk3 |
| proliferator_mk1 | Re-Composing Assembler | 6 | proliferator_mk1 | 60.000 | 1 | proliferator_mk2 |
| carbon_nanotube | Quantum Chemical Plant | 13 | carbon_nanotube | 16.250 | 1 | proliferator_mk3 |
| graphene | Quantum Chemical Plant | 12 | graphene | 20.000 | 1 | carbon_nanotube |
| sulfuric_acid | Quantum Chemical Plant | 5 | sulfuric_acid | 8.333 | 1 | graphene |
| diamond | Negentropy Smelter | 15 | diamond | 28.125 | 1 | proliferator_mk2 |
| energetic_graphite | Negentropy Smelter | 25 | energetic_graphite | 46.875 | 1 | graphene, diamond |
| titanium_ingot | Negentropy Smelter | 4 | titanium_ingot | 7.500 | 1 | carbon_nanotube |
| plasma_refining | Oil Refinery | 16 | refined_oil | 10.000 | 1 | sulfuric_acid |
| coal | Raw | - | coal | 123.000 | 2 | proliferator_mk1 (48.0), energetic_graphite (75.0) |
| titanium_ore | Raw | - | titanium_ore | 12.000 | 1 | titanium_ingot |
| stone | Raw | - | stone | 13.333 | 1 | sulfuric_acid |
| water | Raw | - | water | 6.667 | 1 | sulfuric_acid |
| crude_oil | Raw | - | crude_oil | 8.000 | 1 | plasma_refining |

---

## Building Totals

| Building | Count |
|---|---|
| Matrix Lab | 97 |
| Re-Composing Assembler | 120 |
| Negentropy Smelter | 143 |
| Quantum Chemical Plant | 67 |
| Collider | 22 |
| Oil Refinery | 58 |
| Orbital Collector | 10 |
| **Total** | **517** |

---

## How This Document Was Built

### Recipe source

All recipe data was fetched from `https://raw.githubusercontent.com/troyfawkes/public/refs/heads/main/dsp_recipes.json`. Machine count formula and building speeds are identical to the white science documents.

### Space warper target

`space_warper_advanced`: 1 gravity_matrix → 8 space_warper, 10s. At Re-Composing speed (4×), each assembler consumes 0.4/s gravity_matrix and outputs 4.0/s warpers. 25 assemblers → 100/s warpers, consuming 10/s gravity_matrix, requiring 97 Matrix Labs.

### Proliferator consumption calculation

Each item flowing into a machine requires one spray. Total items/s consumed across all machines in both chains is summed, then divided by 75 (sprays per proliferated Mk.III unit). White science: 561.95 items/s ÷ 75 = 7.493/s. Utility chain: 860.72 items/s ÷ 75 = 11.463/s. Total: 18.956/s → 8 Re-Composing Assemblers producing 20/s proliferator_mk3.

### Proliferator chain

proliferator_mk3 (2 mk2 + 1 carbon_nanotube → 1, 2s) → proliferator_mk2 (2 mk1 + 1 diamond → 1, 1s) → proliferator_mk1 (1 coal → 1, 0.5s). The diamond demand for proliferator_mk2 (28/s) dominates the smelter count in the prolif sub-chain. Carbon_nanotube requires its own graphene → sulfuric_acid → refined_oil chain, kept separate from the warper chain's graphene production.

### Orbital Collectors

Deuterium demand (27.5/s) is the binding constraint requiring 10 collectors at VU5. This produces 152/s hydrogen against a net demand of 46.875/s — large surplus, no concern.

### Instructions for scaling

Fetch `https://raw.githubusercontent.com/troyfawkes/public/refs/heads/main/dsp_recipes.json` and recalculate from scratch. If the white science build changes scale, recalculate prolif consumption for that chain first, then re-derive total prolif demand before sizing the proliferator sub-chain. The two coal demands in the prolif chain (48/s for proliferator_mk1, 75/s for energetic_graphite) are consolidated into a single 123/s row.

---

## Future Additions

The following items are planned for future blueprint modules. Each stands as a fully self-contained chain — none share production lines with the white science or warper builds, so they will need dedicated smelter, chemical, and refinery infrastructure.

- **Antimatter Capsule** — 1 Re-Composing Assembler → 2.5/s. Requires 20/s antimatter and 20/s deuterium from orbital collectors as external inputs.
- **Antimatter Fuel Rod** — 1 Re-Composing Assembler → 0.417/s. Best late-game mech and Artificial Star fuel. Hydrogen demand fully covered by plasma_refining co-product — no orbital collector needed.
- **High Explosive Shell Set** — 3 Re-Composing Assemblers → 5/s is the natural unit, but the chain is copper and coal intensive and does not share inputs with white science. Revisit scale target before building.
