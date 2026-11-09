# THE LAST NUMBER EXISTENCE — Universe Systems Bible v0.1
Author / creative director: Victor Andrei Manolescu
Project: Saga Studios | Status: design specification, not a shipped game

## Creative north star
One persistent science-fantasy multiverse supports character discovery, 3D MOBA, story RPG, RTS/civilization strategy, racing, mech customization, research, and world authoring. Every existence is playable in parallel once its discovery threshold is met. The Last Number is the final high-level **Security Existence**, where players can safely author worlds using the same tools previously learned through play. The Last Number's actual numeral is **intentionally unassigned** pending the creator's final decision.

## Canon and source boundaries
The literary Cosmogony of Repairing the Stars and the game can share cosmological motifs and references, but no game document overwrites the book's editorial canon. The book's father remains a memory, and the Altar storyline is reserved for later Library exploration. Red Alert, Rise of Civilizations, Need for Speed, GTA, and Dragon Ball are *design comparisons*, not licensed IP or assets. Develop original factions, vehicles, characters, settings, and mechanics.

## Existence architecture
Existences are simultaneous game lenses over a shared persistent world rather than disconnected save games:
1. **Discovery** — recruit, study, and build relationships with characters, species, totems and factions.
2. **Arena** — three-dimensional team MOBA; roles: Mirror (reflection/position swapping), Resonance (team buffs), Bastion (mech tank).
3. **Chronicle** — story RPG with branching perspectives, towns, dungeons, ethical decisions.
4. **Command** — RTS, base construction, supply chains, unit production, territory defense.
5. **Civilizations** — city-scale diplomacy, eras, culture, planetary research and infrastructure.
6. **Velocity** — street-to-orbit racing, body shops, terrain and track editing, pursuit/hunter modes.
7. **Expedition** — ground, sky and team-world dimensional exploration, monsters, elders, research expeditions.
8. **Laboratory** — materials, creature behavior, inventions, AI agents, scientific trials and tutorials.
9. **Sanctuary** — portable miniature-tree homes and nested pocket habitats with defensive ecosystems.
LAST NUMBER / **Security Existence** — one coherent world-authoring layer integrating every previous mode. Its numeric index is reserved.

Each lens changes UI, permissions, camera, objectives and tools; position, history, relationships, resources and world changes remain shared. Game servers enforce constraints, never trust client-reported resources or abilities.

## The twins and the evolving Codex
The twins are two distinct playable protagonists whose relationship anchors the core storyline. Each owns a Codex that initially records discoveries, then evolves through mastery of research, building, mobility, diplomacy and defense.
- Codex phases: Archive → Instrument → Exoskeleton → Modular Mech → Mobile Foundry → World Loom.
- **Transforming mech**: bipedal traversal, wheeled road mode, aerial glide, command/foundry mode. Transformations have energy, mass and terrain constraints; no unrestricted instant victory mode.
- **RTS factory in a character**: deploy construction drones, prefab structures, defensive towers and squads from a bounded inventory. Blueprint cost, supply radius, fabrication time and power are visible.
- **Sword-car symbiosis**: a signature vehicle and melee weapon share a morphable material core, preserving tune history and abilities. A player can drive, dismount into blade mode, or transform into mech.
- **Twin synergy**: one twin can survey and mirror blueprints while the other fabricates and stabilizes; solo players can assign an AI companion to the second role. Co-op adds joint abilities without locking solo progression.
- **Custom abilities**: players equip researched skills from encountered characters through a slot, cost, cooldown and compatibility budget. The Codex records provenance and avoids unrestricted stacking.

## Last Number: the Security Existence
Arrival presents the entire familiar game world decades later, viewed through an older version of the protagonist. This is a *future perspective*, not irreversible aging; time-layer travel is a first-class mechanic. The central circular **Arena of Instruments** contains every unlocked lab tool, simulation gate, tutorial, build station and audit console.

Players may:
- construct cities across allowed world surfaces and vertical layers, including car body shops at the bases of towers;
- attach snowball defense turrets or other nonlethal, researchable defenses to buildings;
- author racing tracks and hunter pursuits, enter interiors, and switch seamlessly between vehicles, suits, and character control;
- visit alien planets, negotiate with elders, research species, challenge creatures, and establish alliances;
- build miniature-tree pocket homes with recursive interiors, but with explicit nesting depth and resource quotas;
- send armies and research agents on bounded expeditions to gather items, investigate, trade or defend territory;
- open time layers and connected dimensions with controlled history forks, never silently rewriting another player's world;
- create an entire personal multiverse from validated templates, then invite collaborators or publish snapshots.

**Security is gameplay, not just a setting**: authorship permissions, blueprint signatures, visitor roles, economy isolation, consent for PvP, safe simulations, rollback and moderation are presented as in-world engineering tools. A player may experiment in a sandbox without griefing the persistent shared world.

## Core gameplay loop
Discover → Research → Prototype → Test in a simulated arena → Build or equip → Explore / race / negotiate / battle → Collect evidence → Evolve Codex → Unlock new world-authoring permissions.
Combat is one research pathway, not the whole purpose. Creatures may be studied, befriended, avoided, or fought. Alien elders offer diplomacy, knowledge and quests rather than being reduced to enemies.

## Three spatial layers
- **Land**: buildings, underground facilities, forests, cities, roads, ground battles.
- **Sky**: floating structures, orbital transit, aircraft, vertical racing and sky bases.
- **Team World**: a shared tactical / social dimensional layer that projects squad abilities and team infrastructure into land and sky. All three coexist spatially; portals and phase shifts change accessibility.

## Unit and agentic operation contracts
Every autonomous squad mission has: owner, explicit objective, permitted actions, target region, resource budget, risk limit, time limit, return condition and readable event log. Agents cannot spend premium currency, destroy allied property, or cross worlds without explicit authorization. Failed missions return partial findings and explanation. Offline operations are simulated deterministically and resolved with server authority.

## Research engine
Knowledge is earned as evidence rather than simply XP. Each discovery has a hypothesis, tools, observation, uncertainty, reproducibility score and applications. The Super Intelligence Research System proposes experiments, flags unsafe combinations, recommends tutorials and generates explainable upgrades. It never pretends simulated science is a real-world proven result.

## Racing and construction fusion
Body shops are physical world businesses with lifts, material fabrication, aerodynamic testing, suspension, traction, energy cells and paint. Cars have modular chassis, mass distribution, terrain grip, drivetrain, energy use and damage. Tracks may cross buildings, sky bridges, planets and phase gates. RTS supply lines can deliver replacement parts and construct temporary ramps during races; competitive modes restrict live construction to balanced, announced rules.

## Progression and economy
Progression: discovery mastery + research evidence + social reputation + engineering certification + Codex evolution. Avoid pay-to-win. Cosmetic purchases, if ever added, cannot affect simulation outcomes. PvP and PvE use separate balancing profiles. Resource scarcity and environmental costs are tunable per world. Player-made worlds cannot mint transferable premium resources.

## Game data contract (draft)
World {id, owner_id, seed, ruleset_version, permissions, parent_world_id, time_branch_id}
Existence {id, lens_type, unlock_requirements, allowed_tools}
Codex {owner_id, phase, modules, blueprints, energy, skill_slots}
Blueprint {id, creator_id, version, recipe, dependencies, permissions, validation_hash}
AgentMission {id, owner_id, objective, allowed_actions, region, budget, deadline, status, event_log}
ResearchFinding {id, hypothesis, evidence_refs, confidence, reproducibility, unlocks}
Vehicle {id, morph_core_id, chassis, tuning, equipment, wear}
WorldEvent {id, world_id, tick, actor, action, payload, reversible}

## Technical architecture proposal
- Engine: Godot 4, GDScript for prototype; use modular ECS-like composition and resource-driven content.
- World: region streaming, authoritative simulation for shared zones, local/offline sandbox for solo mode.
- Services: accounts, world registry, character inventory, research graph, missions, blueprint validation, matchmaking, event log.
- Persistence: append-only world events with periodic snapshots; migration/version checks; player-owned fork/rollback.
- AI: optional assistive planner for tutorials and agent missions; deterministic simulation and validation remain conventional game code.
- Build security: sandbox user-authored scripts or, preferably, declarative blueprints; never execute untrusted code in the server process.
- Accessibility: scalable UI, remappable controls, reduced motion, solo-friendly progression, mobile-friendly command interface.

## Vertical slice — first genuinely playable milestone
One compact district with a street, tower, workshop, arena and small forest. Two twins; one Codex with Archive/Instrument/Exoskeleton phases. A vehicle with 3 tuning parameters and one short race. A 3D arena encounter. A mini RTS deployment of 2 drones and 1 defensive tower. A creature research quest. A pocket tree room. A controlled transition into a preview of the Last Number's Arena of Instruments.
Success tests: save/reload retains changes; solo and co-op objective parity; no unauthorized build; each mode can return to exploration; performance budget measured; agent orders show limits and logs.

## Development backlog
P0: lore/permissions contract, world coordinates and time-branch model, movement + save, Codex state machine.
P1: twin switching, mech traversal, modular vehicles, workshop, RTS deployables, research loop.
P2: arena combat, civilization prototype, alien expedition, pocket-tree interior, tutorials.
P3: persistent multiplayer, authored worlds, agentic missions, rollback, Last Number Security Existence.
P4: planetary scale, deep faction diplomacy, large battles, creator marketplace (subject to separate safety/economy review).

## Definition of done
A feature is done only after it has working implementation, tests, documented controls, balancing parameters, persistence checks, accessibility review and reproducible build instructions. This file is a **design deliverable**, not evidence that the game has been implemented.

## Reserved decision
The creator will supply the Last Number only after the other existences and mechanics are fully designed. Do not assign a number, imply an endpoint to infinity, or make that choice automatically.
