# DSP — White Science Production Chain
## Target: 1 universe_matrix / second

**Defaults:** Mk.II Assembler · Arc Smelter · Chemical Plant · Matrix Lab · Miniature Particle Collider — all at 1.00× speed · Mk.III Belt (30/s) · Mk.III Proliferator (+25% output) · No stackers

---

| Recipe | Building | Machines | Items Produced | Output /s | Mk.III Belts | Consumed by |
|---|---|---|---|---|---|---|
| universe_matrix | Matrix Lab | 12 | universe_matrix | 1.000 | 1 | Research |
| electromagnetic_matrix | Matrix Lab | 2 | electromagnetic_matrix | 0.833 | 1 | universe_matrix |
| energy_matrix | Matrix Lab | 4 | energy_matrix | 0.833 | 1 | universe_matrix |
| structure_matrix | Matrix Lab | 6 | structure_matrix | 0.938 | 1 | universe_matrix |
| information_matrix | Matrix Lab | 7 | information_matrix | 0.875 | 1 | universe_matrix |
| gravity_matrix | Matrix Lab | 8 | gravity_matrix | 0.833 | 1 | universe_matrix |
| processor | Mk.II Assembler | 5 | processor | 2.083 | 1 | information_matrix (1.4), quantum_chip (0.667) |
| circuit_board | Mk.II Assembler | 2 | circuit_board | 5.000 | 1 | electromagnetic_matrix (0.667), processor (3.333) |
| microcrystalline_component | Mk.II Assembler | 6 | microcrystalline_component | 3.750 | 1 | processor (3.333) |
| particle_broadband | Mk.II Assembler | 5 | particle_broadband | 0.781 | 1 | information_matrix (0.7) |
| titanium_crystal | Mk.II Assembler | 4 | titanium_crystal | 1.250 | 1 | structure_matrix (0.75), casimir_crystal (0.5) |
| casimir_crystal | Mk.II Assembler | 2 | casimir_crystal | 0.625 | 1 | plane_filter (0.583) |
| titanium_glass | Mk.II Assembler | 3 | titanium_glass | 1.500 | 1 | plane_filter (1.167) |
| graviton_lens | Mk.II Assembler | 2 | graviton_lens | 0.417 | 1 | gravity_matrix (0.333) |
| quantum_chip | Mk.II Assembler | 2 | quantum_chip | 0.417 | 1 | gravity_matrix (0.333) |
| plane_filter | Mk.II Assembler | 7 | plane_filter | 0.729 | 1 | quantum_chip (0.667) |
| magnetic_coil | Mk.II Assembler | 3 | magnetic_coil | 7.500 | 1 | electromagnetic_matrix (0.667), electromagnetic_turbine (3.0), electric_motor (2.5) |
| electromagnetic_turbine | Mk.II Assembler | 3 | electromagnetic_turbine | 1.875 | 1 | particle_container (1.5) |
| electric_motor | Mk.II Assembler | 5 | electric_motor | 3.125 | 1 | electromagnetic_turbine (3.0) |
| gear | Mk.II Assembler | 2 | gear | 2.500 | 1 | electric_motor (2.5) |
| particle_container | Mk.II Assembler | 3 | particle_container | 0.938 | 1 | strange_matter (0.75) |
| iron_ingot | Arc Smelter | 10 | iron_ingot | 12.500 | 1 | circuit_board (4.0), electric_motor (5.0), gear (2.0), strange_matter (0.75) |
| copper_ingot | Arc Smelter | 8 | copper_ingot | 10.000 | 1 | circuit_board (2.0), microcrystalline_component (3.0), magnetic_coil (3.0), particle_container (1.5) |
| magnet | Arc Smelter | 8 | magnet | 6.667 | 1 | magnetic_coil (6.0) |
| energetic_graphite | Arc Smelter | 17 | energetic_graphite | 10.625 | 1 | energy_matrix (1.333), graphene (5.0), plastic (2.0), diamond (2.0) |
| diamond | Arc Smelter | 4 | diamond | 2.500 | 1 | structure_matrix (0.75), graviton_lens (1.333) |
| high_purity_silicon | Arc Smelter | 12 | high_purity_silicon | 7.500 | 1 | microcrystalline_component (6.0), crystal_silicon (1.0) |
| crystal_silicon | Arc Smelter | 2 | crystal_silicon | 1.250 | 1 | particle_broadband (1.25) |
| glass | Arc Smelter | 2 | glass | 1.250 | 1 | titanium_glass (1.2) |
| titanium_ingot | Arc Smelter | 8 | titanium_ingot | 5.000 | 1 | titanium_glass (1.2), titanium_crystal (3.0), carbon_nanotube (0.5) |
| graphene | Chemical Plant | 5 | graphene | 4.167 | 1 | casimir_crystal (1.0), particle_container (1.5), carbon_nanotube (1.5) |
| carbon_nanotube | Chemical Plant | 2 | carbon_nanotube | 1.250 | 1 | particle_broadband (1.25) |
| sulfuric_acid | Chemical Plant | 2 | sulfuric_acid | 1.667 | 1 | graphene (1.667) |
| plastic | Chemical Plant | 6 | plastic | 2.500 | 1 | particle_broadband (0.625), organic_crystal (1.667) |
| organic_crystal | Chemical Plant | 5 | organic_crystal | 1.042 | 1 | titanium_crystal (1.0) |
| mass_energy_storage | Collider | 1 | antimatter (1.25), hydrogen (1.25) | 1.250 | 1 | universe_matrix (0.8) |
| deuterium | Collider | 2 | deuterium | 5.000 | 1 | strange_matter (3.75) |
| strange_matter | Collider | 3 | strange_matter | 0.469 | 1 | graviton_lens (0.333) |
| plasma_refining | Oil Refinery | 11 | refined_oil (6.875), hydrogen (3.438) | 6.875 | 1 | plastic (4.0), sulfuric_acid (2.0), organic_crystal (0.833) |
| iron_ore | Raw | - | iron_ore | 15.333 | 1 | iron_ingot (10.0), magnet (5.333) |
| copper_ore | Raw | - | copper_ore | 8.000 | 1 | copper_ingot (8.0) |
| silicon_ore | Raw | - | silicon_ore | 12.000 | 1 | high_purity_silicon (12.0) |
| coal | Raw | - | coal | 17.000 | 1 | energetic_graphite (17.0) |
| titanium_ore | Raw | - | titanium_ore | 8.000 | 1 | titanium_ingot (8.0) |
| stone | Raw | - | stone | 4.667 | 1 | sulfuric_acid (2.667), glass (2.0) |
| water | Raw | - | water | 3.367 | 1 | titanium_glass (1.2), sulfuric_acid (1.333), organic_crystal (0.833) |
| crude_oil | Raw | - | crude_oil | 5.500 | 1 | plasma_refining (5.5) |
| hydrogen | Raw | - | hydrogen | 10.646 | 1 | energy_matrix (1.333), casimir_crystal (6.0), deuterium (8.0) — net of mass_energy_storage co-product (1.25) and plasma_refining co-product (3.438) |
| critical_photon | Raw | - | critical_photon | 1.000 | 1 | mass_energy_storage (1.0) |

---

## How This Document Was Built

### Recipe source

All recipe data was fetched from `https://raw.githubusercontent.com/troyfawkes/public/refs/heads/main/dsp_recipes.json`. Each entry contains the producing building type, craft time in seconds at 1× speed, and exact input/output quantities per cycle. No wiki searches or cached knowledge were used — the file is the single source of truth, and any calculation done here can be re-verified against it directly.

### Machine count formula

For every item, the number of machines is:

```
machines = ceil( demand_rate / output_rate_per_machine )

output_rate_per_machine = (output_qty / craft_time) × building_speed × prolif_multiplier
                        = (output_qty / craft_time) × 1.00 × 1.25
```

Proliferator Mk.III (+25%) increases output rate only — it does not change how fast a single machine consumes its inputs. So a machine producing 1 item every 4 seconds without prolif produces 1.25 items every 4 seconds with prolif, consuming exactly the same inputs per second at the machine level. However, because you need ~20% fewer machines to hit the same throughput target, total input consumption across the factory is also ~20% lower. Prolif saves both machines and raw resources proportionally. Without prolif, this chain would require approximately 30+ additional machines and a corresponding increase in all raw resource rates.

### Consumption propagation

The chain was solved top-down: start with the final output rate (1 universe_matrix/s), compute what each sub-matrix lab consumes per second, then trace every input recursively until hitting a raw resource (ore, crude oil, water, stone, coal). Items with multiple consumers (e.g. circuit_board, magnetic_coil, titanium_ingot) had their demands summed before machine counts were calculated. The full traversal required two passes on graphene and energetic_graphite because carbon_nanotube — a mid-chain item — also consumes graphene, which was easy to miss on a first pass.

### Belt column

`Mk.III Belts = ceil( output_rate / 30 )`. At 1/s scale every item in this chain fits on a single belt. This column becomes meaningful at 10/s or 20/s targets, where items like iron_ore (15.333 × 10 = 153/s → 6 belts) and energetic_graphite (17 × 10 = 170/s → 6 belts) require multiple belts per output line.

---

## Instructions for Scaling This Document

### Recalculate from scratch — do not multiply

Machine counts cannot be derived by multiplying the 1/s figures. Ceiling effects at 1/s cause significant rounding overages (e.g. casimir_crystal requires 1.87 machines, rounded to 2). At 10/s the same recipe needs 18.7 → 19, a much smaller overage. Always recalculate against the new target rate using the formula in the Machine count formula section above, fetching fresh recipe data from the GitHub JSON first.

### Recipe data

Fetch `https://raw.githubusercontent.com/troyfawkes/public/refs/heads/main/dsp_recipes.json` before any calculation. Do not rely on values in this document as recipe inputs — use this document only to understand the chain structure (which items feed which) and to cross-check results. The JSON is the authoritative source for `inputs`, `outputs`, `time`, and `at` (building type) for every recipe.

### Items with multiple consumers

Several items in this chain feed more than one downstream recipe. Always sum all consumer demands before calculating machine count. The key multi-consumer items are: `circuit_board`, `magnetic_coil`, `titanium_ingot`, `titanium_crystal`, `graphene`, `processor`, `energetic_graphite`, `copper_ingot`, and `iron_ingot`. Missing a consumer is the most common source of error — the `Consumed by` column in the table above is the definitive list for this chain.

### Building tier changes

If building tiers change from the defaults above (e.g. Plane Smelter at 2× instead of Arc Smelter at 1×, or Mk.III Assembler at 1.5× instead of Mk.II at 1×), update the `building_speed` multiplier in the formula and recalculate all machine counts for the affected rows. Raw resource rates will change proportionally.

### The oil loop

`plasma_refining` produces both `refined_oil` and `hydrogen` as co-products (2 crude_oil → 2 refined_oil + 1 hydrogen, 4s). At 1/s scale, 11 refineries cover the 6.833/s refined_oil demand, consuming 5.5/s crude_oil and producing 3.438/s hydrogen as a co-product. That co-product offsets part of the hydrogen demand, leaving 10.646/s net hydrogen still needed from an additional source (more refineries, fractionators, or a gas giant orbital collector). At larger scales, design the refinery module to the exact `refined_oil` output rate shown in the table (multiplied by the scale factor), then account for the hydrogen co-product before sizing any supplemental hydrogen supply. The recipe choice (plasma refining vs. reformed refinement vs. X-ray cracking) affects the hydrogen/refined_oil ratio and must be matched to whichever output is the binding constraint.
