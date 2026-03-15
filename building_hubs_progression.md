# DSP — Building Production Hubs (Progression-Based)
## 13 hubs covering all buildings + ammunition + ships & drones

Each hub uses a sushi belt carrying all listed inputs. Chain dependencies (mk1→mk2→mk3 etc.) are co-located and feed each other directly. Proliferators delivered via logistics bots.

---

### Hub 1 — Early Infrastructure
**11 inputs · 14 buildings**

Produces: conveyor_belt mk1/mk2/mk3 · sorter mk1/mk2/mk3 · pile_sorter · splitter · traffic_monitor · automatic_piler · depot mk1/mk2 · storage_tank · foundation

| Input | Used by |
|---|---|
| circuit_board | sorter_mk1, splitter, traffic_monitor |
| electric_motor | sorter_mk2 |
| electromagnetic_turbine | conveyor_belt_mk2, sorter_mk3 |
| gear | conveyor_belt_mk1, splitter, traffic_monitor, automatic_piler |
| glass | storage_tank, traffic_monitor |
| graphene | conveyor_belt_mk3 |
| iron_ingot | conveyor_belt_mk1, sorter_mk1, splitter, traffic_monitor, depot_mk1, storage_tank |
| processor | pile_sorter, automatic_piler |
| steel | automatic_piler, depot_mk2, foundation |
| stone_brick | depot_mk1, depot_mk2, storage_tank, foundation |
| super_magnetic_ring | conveyor_belt_mk3, pile_sorter, automatic_piler |

---

### Hub 2 — Assemblers, Mining & Basic Power
**10 inputs · 8 buildings**

Produces: assembling_machine mk1/mk2/mk3 · mining_machine · water_pump · wind_turbine · thermal_power_plant · arc_smelter

| Input | Used by |
|---|---|
| circuit_board | assembling_machine_mk1, mining_machine, water_pump, arc_smelter |
| electric_motor | water_pump |
| gear | assembling_machine_mk1, mining_machine, thermal_power_plant |
| graphene | assembling_machine_mk2 |
| iron_ingot | assembling_machine_mk1, mining_machine, water_pump, wind_turbine, thermal_power_plant, arc_smelter |
| magnetic_coil | mining_machine, wind_turbine, thermal_power_plant, arc_smelter |
| particle_broadband | assembling_machine_mk3 |
| processor | assembling_machine_mk2 |
| quantum_chip | assembling_machine_mk3 |
| stone_brick | water_pump, arc_smelter, thermal_power_plant |

---

### Hub 3 — Power Towers, Oil & Chemical
**12 inputs · 10 buildings**

Produces: matrix_lab · chemical_plant · oil_extractor · oil_refinery · tesla_tower · wireless_power_tower · satellite_substation · signal_tower · fractionator · spray_coater

| Input | Used by |
|---|---|
| circuit_board | matrix_lab, chemical_plant, oil_extractor, oil_refinery, spray_coater |
| crystal_silicon | signal_tower |
| frame_material | satellite_substation |
| glass | matrix_lab, chemical_plant, fractionator |
| iron_ingot | matrix_lab, tesla_tower |
| magnetic_coil | matrix_lab, tesla_tower |
| microcrystalline_component | spray_coater |
| plasma_exciter | wireless_power_tower, oil_extractor, oil_refinery, spray_coater |
| processor | fractionator |
| steel | oil_extractor, oil_refinery, fractionator, spray_coater, signal_tower |
| stone_brick | chemical_plant, oil_extractor, oil_refinery, fractionator |
| super_magnetic_ring | satellite_substation |

---

### Hub 4 — Logistics & Energy
**9 inputs · 6 buildings**

Produces: planetary_logistics_station · interstellar_logistics_station · logistics_bot · logistics_drone · logistics_distributor · energy_exchanger

| Input | Used by |
|---|---|
| engine | logistics_bot |
| iron_ingot | logistics_bot, logistics_drone, logistics_distributor |
| particle_container | planetary_logistics_station, energy_exchanger |
| plasma_exciter | logistics_distributor |
| processor | planetary_logistics_station, logistics_bot, logistics_drone, logistics_distributor, energy_exchanger |
| steel | planetary_logistics_station, energy_exchanger |
| thruster | logistics_drone |
| titanium_alloy | interstellar_logistics_station, energy_exchanger |
| titanium_ingot | planetary_logistics_station |

---

### Hub 5 — Advanced Power
**11 inputs · 4 buildings**

Produces: mini_fusion_power_plant · geothermal_power_station · solar_panel · accumulator

| Input | Used by |
|---|---|
| carbon_nanotube | mini_fusion_power_plant |
| circuit_board | solar_panel |
| copper_ingot | geothermal_power_station |
| crystal_silicon | accumulator |
| high_purity_silicon | solar_panel |
| iron_ingot | accumulator |
| photon_combiner | geothermal_power_station |
| processor | mini_fusion_power_plant |
| steel | geothermal_power_station |
| super_magnetic_ring | mini_fusion_power_plant, geothermal_power_station, accumulator |
| titanium_alloy | mini_fusion_power_plant |

---

### Hub 6 — Plane Smelter, Collider & Dyson Support
**12 inputs · 4 buildings**

Produces: plane_smelter · miniature_particle_collider · em_rail_ejector · ray_receiver

| Input | Used by |
|---|---|
| arc_smelter | plane_smelter |
| frame_material | plane_smelter, miniature_particle_collider |
| gear | em_rail_ejector |
| graphene | miniature_particle_collider |
| high_purity_silicon | ray_receiver |
| photon_combiner | ray_receiver |
| plane_filter | plane_smelter |
| processor | miniature_particle_collider, em_rail_ejector, ray_receiver |
| steel | em_rail_ejector, ray_receiver |
| super_magnetic_ring | miniature_particle_collider, em_rail_ejector, ray_receiver |
| titanium_alloy | miniature_particle_collider |
| unipolar_magnet | plane_smelter |

---

### Hub 7 — Quantum Chemical Plant, Vertical Silo & Artificial Star
**8 inputs · 3 buildings**

Produces: quantum_chemical_plant · vertical_launching_silo · artificial_star

| Input | Used by |
|---|---|
| annihilation_constraint_sphere | artificial_star |
| chemical_plant | quantum_chemical_plant |
| frame_material | vertical_launching_silo |
| graviton_lens | vertical_launching_silo |
| quantum_chip | quantum_chemical_plant, vertical_launching_silo, artificial_star |
| strange_matter | quantum_chemical_plant |
| titanium_alloy | quantum_chemical_plant, vertical_launching_silo, artificial_star |
| titanium_glass | quantum_chemical_plant |

---

### Hub 8 — End Game
**11 inputs · 3 buildings**

Produces: advanced_mining_machine · orbital_collector · self_evolution_lab

| Input | Used by |
|---|---|
| accumulator_full | orbital_collector |
| dark_fog_matrix | self_evolution_lab |
| frame_material | advanced_mining_machine |
| grating_crystal | advanced_mining_machine |
| interstellar_logistics_station | orbital_collector |
| matrix_lab | self_evolution_lab |
| quantum_chip | advanced_mining_machine, self_evolution_lab |
| reinforced_thruster | orbital_collector |
| silicon_based_neuron | self_evolution_lab |
| super_magnetic_ring | advanced_mining_machine, orbital_collector |
| titanium_alloy | advanced_mining_machine |

---

### Hub 9 — Turrets: Basic
**12 inputs · 6 buildings**

Produces: gauss_turret · missile_turret · implosion_cannon · laser_turret · sr_plasma_turret · battlefield_analysis_base

| Input | Used by |
|---|---|
| circuit_board | gauss_turret, missile_turret, implosion_cannon, laser_turret, battlefield_analysis_base |
| electric_motor | missile_turret, implosion_cannon |
| engine | missile_turret, battlefield_analysis_base |
| gear | gauss_turret |
| iron_ingot | gauss_turret |
| magnetic_coil | gauss_turret |
| microcrystalline_component | battlefield_analysis_base |
| photon_combiner | laser_turret |
| plasma_exciter | laser_turret, sr_plasma_turret |
| processor | sr_plasma_turret |
| steel | laser_turret, implosion_cannon, missile_turret, sr_plasma_turret, battlefield_analysis_base |
| super_magnetic_ring | implosion_cannon, sr_plasma_turret |

---

### Hub 10 — Turrets: Advanced
**10 inputs · 3 buildings**

Produces: plasma_turret · jammer_tower · planetary_shield_generator

| Input | Used by |
|---|---|
| copper_ingot | jammer_tower |
| diamond | jammer_tower |
| electromagnetic_turbine | planetary_shield_generator |
| particle_container | planetary_shield_generator |
| plasma_exciter | plasma_turret, jammer_tower |
| processor | plasma_turret, jammer_tower |
| steel | plasma_turret, planetary_shield_generator |
| super_magnetic_ring | plasma_turret, planetary_shield_generator |
| titanium_alloy | plasma_turret |
| titanium_glass | plasma_turret |

---

### Hub 11 — Ammunition
**11 inputs · 10 buildings**

Produces: combustible_unit · magnum_ammo_box · titanium_ammo_box · superalloy_ammo_box · shell_set · high_explosive_shell_set · crystal_shell_set · missile_set · supersonic_missile_set · gravity_missile_set

| Input | Used by |
|---|---|
| circuit_board | missile_set |
| coal | combustible_unit |
| copper_ingot | magnum_ammo_box, shell_set, missile_set |
| crystal_explosive_unit | crystal_shell_set, gravity_missile_set |
| engine | missile_set |
| explosive_unit | high_explosive_shell_set, supersonic_missile_set |
| processor | supersonic_missile_set |
| strange_matter | gravity_missile_set |
| thruster | supersonic_missile_set |
| titanium_alloy | superalloy_ammo_box, crystal_shell_set |
| titanium_ingot | titanium_ammo_box, high_explosive_shell_set |

---

### Hub 12 — Advanced Ammunition
**6 inputs · 2 buildings**

Produces: plasma_capsule · antimatter_capsule

| Input | Used by |
|---|---|
| antimatter | antimatter_capsule |
| deuterium | plasma_capsule |
| graphene | plasma_capsule |
| hydrogen | antimatter_capsule |
| magnet | plasma_capsule |
| particle_container | antimatter_capsule |

---

### Hub 13 — Ships & Combat Drones
**12 inputs · 6 buildings**

Produces: prototype · precision_drone · attack_drone · corvette · destroyer · interstellar_logistics_vessel

| Input | Used by |
|---|---|
| circuit_board | prototype, precision_drone |
| electromagnetic_turbine | precision_drone, attack_drone |
| engine | prototype |
| frame_material | destroyer |
| iron_ingot | prototype |
| particle_container | attack_drone, corvette |
| photon_combiner | precision_drone |
| plasma_exciter | prototype |
| processor | attack_drone, corvette, interstellar_logistics_vessel |
| reinforced_thruster | corvette, destroyer, interstellar_logistics_vessel |
| strange_matter | destroyer |
| titanium_alloy | corvette, destroyer, interstellar_logistics_vessel |

---

## Notes

- **Hub 3** is the natural "second hub you build" after early game — it produces everything needed to get oil and research going.
- **Hub 7** groups quantum_chemical_plant with the two highest-tier buildings (vertical_launching_silo and artificial_star) because they share titanium_alloy, frame_material, and quantum_chip well.
- **Hub 8** end game buildings each require unique exotic inputs (grating_crystal, accumulator_full, dark_fog matrix, silicon_based_neuron) that can't be consolidated with anything else.
- **Hub 11** ammunition: explosive_unit and crystal_explosive_unit are chemical plant products — they arrive as imported inputs, not produced in this hub.
- **Hub 12** advanced ammunition has only 6 inputs and 2 spare slots — room to grow.
- All buildings verified against recipe JSON at `https://raw.githubusercontent.com/troyfawkes/public/refs/heads/main/dsp_recipes.json`.
