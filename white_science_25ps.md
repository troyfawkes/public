# DSP — White Science Production Chain
## Target: 25 universe_matrix / second

**Defaults:** Re-Composing Assembler (4.00×) · Negentropy Smelter (3.00×) · Quantum Chemical Plant (2.00×) · Matrix Lab (1.00×) · Oil Refinery (1.00×) · Miniature Particle Collider (1.00×) · Mk.III Belt with 4× stacking (120/s, 100% efficiency) · Mk.III Proliferator (+25% output)

**Hydrogen & Deuterium:** Supplied by Orbital Collectors on a gas giant. Assumptions: VU level 5, gas giant displays 1.5/s hydrogen and 0.3/s deuterium. At VU5 each collector yields 15.22/s net hydrogen and 3.04/s net deuterium after self-consumption. **5 collectors** cover both demands (deuterium is the binding constraint), producing 76.1/s hydrogen and 15.2/s deuterium — well above the 10.938/s and 13.75/s required respectively.

---

| Recipe | Building | Machines | Items Produced | Output /s | Mk.III Belts (4×) | Consumed by |
|---|---|---|---|---|---|---|
| universe_matrix | Matrix Lab | 300 | universe_matrix | 25.000 | 1 | Research |
| electromagnetic_matrix | Matrix Lab | 48 | electromagnetic_matrix | 20.000 | 1 | universe_matrix |
| energy_matrix | Matrix Lab | 96 | energy_matrix | 20.000 | 1 | universe_matrix |
| structure_matrix | Matrix Lab | 128 | structure_matrix | 20.000 | 1 | universe_matrix |
| information_matrix | Matrix Lab | 160 | information_matrix | 20.000 | 1 | universe_matrix |
| gravity_matrix | Matrix Lab | 192 | gravity_matrix | 20.000 | 1 | universe_matrix |
| quantum_chip | Re-Composing Assembler | 10 | quantum_chip | 8.333 | 1 | gravity_matrix |
| plane_filter | Re-Composing Assembler | 8 | plane_filter | 3.333 | 1 | quantum_chip |
| casimir_crystal | Re-Composing Assembler | 1 | casimir_crystal | 1.250 | 1 | plane_filter |
| titanium_glass | Re-Composing Assembler | 1 | titanium_glass | 2.000 | 1 | plane_filter |
| titanium_crystal | Re-Composing Assembler | 13 | titanium_crystal | 16.250 | 1 | structure_matrix, casimir_crystal |
| graviton_lens | Re-Composing Assembler | 10 | graviton_lens | 8.333 | 1 | gravity_matrix |
| processor | Re-Composing Assembler | 22 | processor | 36.667 | 1 | information_matrix, quantum_chip |
| particle_broadband | Re-Composing Assembler | 26 | particle_broadband | 16.250 | 1 | information_matrix |
| microcrystalline_component | Re-Composing Assembler | 6 | microcrystalline_component | 15.000 | 1 | processor |
| circuit_board | Re-Composing Assembler | 4 | circuit_board | 40.000 | 1 | electromagnetic_matrix, processor |
| particle_container | Re-Composing Assembler | 3 | particle_container | 3.750 | 1 | strange_matter |
| electromagnetic_turbine | Re-Composing Assembler | 1 | electromagnetic_turbine | 2.500 | 1 | particle_container |
| electric_motor | Re-Composing Assembler | 1 | electric_motor | 2.500 | 1 | electromagnetic_turbine |
| gear | Re-Composing Assembler | 1 | gear | 5.000 | 1 | electric_motor |
| magnetic_coil | Re-Composing Assembler | 2 | magnetic_coil | 20.000 | 1 | electromagnetic_matrix, electromagnetic_turbine, electric_motor |
| carbon_nanotube | Quantum Chemical Plant | 6 | carbon_nanotube | 7.500 | 1 | particle_broadband |
| graphene | Quantum Chemical Plant | 4 | graphene | 6.667 | 1 | casimir_crystal, particle_container, carbon_nanotube |
| sulfuric_acid | Quantum Chemical Plant | 1 | sulfuric_acid | 1.667 | 1 | graphene |
| organic_crystal | Quantum Chemical Plant | 8 | organic_crystal | 3.333 | 1 | titanium_crystal |
| plastic | Quantum Chemical Plant | 8 | plastic | 6.667 | 1 | particle_broadband, organic_crystal |
| crystal_silicon | Negentropy Smelter | 4 | crystal_silicon | 7.500 | 1 | particle_broadband |
| high_purity_silicon | Negentropy Smelter | 5 | high_purity_silicon | 9.375 | 1 | microcrystalline_component, crystal_silicon |
| glass | Negentropy Smelter | 1 | glass | 1.875 | 1 | titanium_glass |
| diamond | Negentropy Smelter | 13 | diamond | 24.375 | 1 | structure_matrix, graviton_lens |
| titanium_ingot | Negentropy Smelter | 7 | titanium_ingot | 13.125 | 1 | titanium_glass, titanium_crystal, carbon_nanotube |
| energetic_graphite | Negentropy Smelter | 25 | energetic_graphite | 46.875 | 1 | energy_matrix, graphene, plastic, diamond |
| iron_ingot | Negentropy Smelter | 4 | iron_ingot | 15.000 | 1 | circuit_board, electric_motor, gear, strange_matter |
| copper_ingot | Negentropy Smelter | 3 | copper_ingot | 11.250 | 1 | circuit_board, microcrystalline_component, magnetic_coil, particle_container |
| magnet | Negentropy Smelter | 2 | magnet | 5.000 | 1 | magnetic_coil |
| strange_matter | Collider | 11 | strange_matter | 1.719 | 1 | graviton_lens |
| mass_energy_storage | Collider | 16 | antimatter (20.000), hydrogen co-product (20.000) | 20.000 | 1 | universe_matrix |
| plasma_refining | Oil Refinery | 13 | refined_oil (8.125), hydrogen co-product (4.063) | 8.125 | 1 | plastic, sulfuric_acid, organic_crystal |
| iron_ore | Raw | - | iron_ore | 5.333 | 1 | iron_ingot, magnet |
| copper_ore | Raw | - | copper_ore | 3.000 | 1 | copper_ingot |
| silicon_ore | Raw | - | silicon_ore | 5.000 | 1 | high_purity_silicon |
| coal | Raw | - | coal | 25.000 | 1 | energetic_graphite |
| titanium_ore | Raw | - | titanium_ore | 7.000 | 1 | titanium_ingot |
| stone | Raw | - | stone | 2.333 | 1 | sulfuric_acid, glass |
| water | Raw | - | water | 2.400 | 1 | titanium_glass, sulfuric_acid, organic_crystal |
| crude_oil | Raw | - | crude_oil | 6.500 | 1 | plasma_refining |
| hydrogen | Raw (Orbital Collector) | 5 collectors | hydrogen | 10.938 | 1 | energy_matrix (32.0), casimir_crystal (3.0) — gross 35.0, offset by antimatter co-product (20.0) and plasma_refining co-product (4.063) |
| deuterium | Raw (Orbital Collector) | 5 collectors | deuterium | 13.750 | 1 | strange_matter |
| critical_photon | Raw | - | critical_photon | 16.000 | 1 | mass_energy_storage |

---

## Building Totals

| Building | Count |
|---|---|
| Matrix Lab | 924 |
| Re-Composing Assembler | 109 |
| Negentropy Smelter | 64 |
| Quantum Chemical Plant | 27 |
| Collider | 27 |
| Oil Refinery | 13 |
| Orbital Collector | 5 |
| **Total** | **1169** |

---

## How This Document Was Built

### Recipe source

All recipe data was fetched from `https://raw.githubusercontent.com/troyfawkes/public/refs/heads/main/dsp_recipes.json`. Each entry contains the producing building type, craft time in seconds at 1× speed, and exact input/output quantities per cycle. No wiki searches or cached knowledge were used — the file is the single source of truth, and any calculation done here can be re-verified against it directly.

### Machine count formula

```
machines = ceil( demand_rate / output_rate_per_machine )

output_rate_per_machine = (output_qty / craft_time) × building_speed × prolif_multiplier
```

Building speeds used: Re-Composing Assembler 4.00×, Negentropy Smelter 3.00×, Quantum Chemical Plant 2.00×, all others 1.00×. Prolif multiplier 1.25 throughout.

### Why 25/s and 300 labs

300 is the minimum universe_matrix lab count at which all six matrix lab tiers produce exact integer machine counts simultaneously (LCM of the sub-matrix lab denominators = 75 labs at 6.25/s; 300 = 4× that, giving 25/s). All sub-matrix labs land exactly on 20.000/s output with zero rounding waste at this scale.

### Orbital Collector formula

```
true_boost = (8 + 0.8 × VU) − 30 / (H_base × 9 + D_base × 9)
net_output_per_collector = true_boost × base_rate
```

Collectors burn a portion of their gross output (30 MW per collector) to power themselves. At VU 5, true_boost = 10.148. With H_base = 1.5 and D_base = 0.3, each collector yields 15.22/s net hydrogen and 3.04/s net deuterium. Deuterium is the binding constraint requiring 5 collectors; hydrogen demand (10.938/s net after co-product offsets) requires only 1.

### Belt column

`Mk.III Belts (4×) = ceil( output_rate / 120 )`. At 25/s every item fits on a single 4× stacked belt — the highest throughput item is energetic_graphite at 46.875/s, well within the 120/s ceiling.

### Consumption propagation

Top-down from universe_matrix, summing all consumer demands before calculating machine counts for multi-consumer items. Key multi-consumer items: circuit_board, magnetic_coil, titanium_ingot, titanium_crystal, graphene, processor, energetic_graphite, copper_ingot, iron_ingot.

### The oil loop

13 Oil Refineries running plasma_refining produce 8.125/s refined_oil against a demand of 7.667/s, consuming 6.5/s crude_oil and yielding 4.063/s hydrogen as co-product. The antimatter colliders return a further 20/s hydrogen co-product. Together these offset 24.063/s of the 35/s gross hydrogen demand, leaving 10.938/s to be supplied by orbital collectors.

---

## Instructions for Scaling This Document

### Recalculate from scratch — do not multiply

Machine counts cannot be derived by multiplying these figures. Always recalculate against the new target rate using the formula above, fetching fresh recipe data from the GitHub JSON first.

### Recipe data

Fetch `https://raw.githubusercontent.com/troyfawkes/public/refs/heads/main/dsp_recipes.json` before any calculation. Use this document only to understand chain structure and cross-check results.

### Items with multiple consumers

Always sum all consumer demands before calculating machine count. Key multi-consumer recipes: circuit_board, magnetic_coil, titanium_ingot, titanium_crystal, graphene, processor, energetic_graphite, copper_ingot, iron_ingot. The Consumed by column is the definitive list.

### Orbital Collectors

Recalculate collector count using the formula in the Orbital Collector formula section above with the actual gas giant's displayed H and D rates and the current VU level. Deuterium is typically the binding constraint. If VU level changes, both net rates improve but the self-consumption (30 MW flat) does not, so higher VU disproportionately benefits collector output.

### The oil loop

Design the refinery module to the refined_oil output rate shown in the table, then subtract the hydrogen co-product before sizing supplemental hydrogen supply from orbital collectors. Recipe choice (plasma_refining vs. reformed_refinement vs. x_ray_cracking) affects the hydrogen/refined_oil ratio and must match whichever output is the binding constraint.
