# Infinite Rewards, Civilizations and Multiverse Mobility — Design v0.2
Creative direction: Victor Andrei Manolescu
Status: specification, not implemented. Companion to UNIVERSE_SYSTEMS_BIBLE.md.

## 1. Reward principle
Every eligible completed activity—session objective, boss, research breakthrough, race, civilization campaign, character milestone, construction tutorial, or authored-world challenge—issues an immediate, claimable reward. No timers, no energy gates, no forced waiting. Mere log-in/AFK time does not count as a completed objective. Repeatable objectives have anti-farming caps that are communicated before play; repeatable play still earns baseline resources.

Rewards come from Common, Rare, Legendary and Event pools. Each pool may include cosmetic appearance, clues, research samples, blueprints, housing modules, vehicle skins, noncompetitive ability variants, or world decorations. Event boxes are earnable through published activities and archived for later acquisition to avoid permanent FOMO.

## 2. Legendary fragments
10 legendary fragments craft 1 Legendary box. Earnable via milestones, duplicate conversion, research and event progression. No expiry. The creator proposed an optional $1 per fragment acceleration route; **not approved for launch** until jurisdiction, platform, age-verification, consumer-protection and gambling/loot-box compliance reviews. Recommended launch alternative: fragments are earned only, while optional $1 purchases grant a **specific disclosed cosmetic item** (no random outcome). Never make payment necessary to access a gameplay system, boss, region or final existence.

For every random reward display exact drop probabilities, duplicates rules, pity guarantee if used, regional restrictions and reward valuation. Do not sell keys, attempts or fragments that directly purchase a randomized prize before legal review. Do not create gambling-like cash-out, transferable market value or real-money resale. Parental controls and spending limits are mandatory if monetization is introduced.

## 3. Starter discovery
A new player receives one free starter discovery box. It selects from a disclosed curated set of visually distinctive, functionally comparable starting inventions; none grants an insurmountable advantage. Examples:
- **Wayfarer private plane**: personalized multiverse transit hub, upgradeable cabin, research radar, hangar; flight and route permissions unlock naturally through play.
- **Orbital soccer sphere**: build a low-gravity sports arena and team-based challenge modes.
- **Pocket grove**: a miniature-tree home with expandable nested interior and ecological research.
- **Sword-car core**: a vehicle and blade sharing one transformation history.
- **Sky workshop**: mobile vehicle tuner and drone garage.
Players can eventually earn all starting archetypes; the initial roll only changes the opening story.

## 4. The prize is a new verb
Major discoveries must unlock an activity or interaction, not merely bigger numbers. Every major reward has:
identity, origin, rarity, acquisition paths, permissions, upgrade tree, energy/resource budget, cosmetic variants, lore clues, tradeability policy, and accessibility alternatives.

Example: Wayfarer aircraft progression
Scout → Research Plane → Interplanetary Shuttle → Dimensional Navigator → Mobile Laboratory → Multiverse Flagship.
Upgrades: propulsion, cabin interiors, defense, sensors, racing handling, cargo, team stations, AI expedition planning and visual customization. Competitive balance uses normalized performance classes; expensive cosmetics confer no combat advantage.

## 5. Red-alert-style RTS + civilization fusion (original IP)
Three original factions:
- **Helion Assemblies**: solar engineering, modular factories, high-speed rail and shield grids.
- **Verdant Concord**: living architecture, symbiotic creatures, ecological defense and adaptive terrain.
- **Umbra Cartographers**: phase gates, reconnaissance, time-layer archives and precision logistics.
A faction has civilians, elders, engineers, scouts, defenders, diplomacy, economy, culture, research and regional infrastructure. No faction is inherently evil; conflicts may be resolved by battle, trade, science or alliance.

RTS loop: survey → harvest responsibly → route supply → deploy mobile Codex foundry → build production and defense → train squads → scout neighboring societies → negotiate or engage → research → advance era.
Civilization loop: settlement → city → planetary federation → interstellar coalition → multiverse stewardship. Each stage inherits RTS-built infrastructure; strategic decisions change actual roads, shops, skyline and NPC life in the explorable world.

## 6. Cross-mode encounter: Tower District
Player drives a morph-core car to a tower workshop, tunes suspension, then enters a hunter race. A sky breach triggers a research alert. The player transforms Codex into mech, deploys a drone, builds a snowball-defense tower and protects civilians. The twins investigate the invaders' ecosystem, negotiate with an alien elder, gain a totem clue and complete a lab tutorial. A reward box gives a Wayfarer aircraft blueprint component. The player then enters a pocket tree home, stores the component, dispatches a bounded agent mission to retrieve materials and returns later to build the aircraft. All events update the same persistent district and research graph.

## 7. Last Number continuity
At the final Security Existence, the protagonist sees a future older self and the complete persistent world. The Arena of Instruments offers guided tools to edit land, sky, team-world, interiors, roads, ecosystems, faction AI and planet templates. Existing planes, sword-cars, totems, shops and character abilities retain their progression. Players may upgrade their aircraft into multiverse flagships, build new race routes and create personal dimensions. The Last Number's **numeral remains deliberately unset**.

## 8. Data model
RewardPool {id, version, rarity, entries:[{reward_id, weight}], disclosure, region_rules}
RewardGrant {id, player_id, activity_id, reward_pool_version, issued_at, claimed_at, rng_commit}
FragmentWallet {player_id, legendary_fragments, earned_ledger}
RewardItem {id, archetype, cosmetic, blueprint, capabilities, upgrade_tree, ownership_policy}
ProgressEvent {id, player_id, activity_id, eligibility_proof, reward_grant_id}
VehicleUpgrade {vehicle_id, module_id, level, cost, physics_profile_version}
CivilizationState {world_id, faction_id, settlements, supply_network, era, diplomacy}
WorldFork {parent_world_id, owner_id, permissions, time_branch, snapshot_id}

Server-side reward draw, audit logs, idempotent claims, duplicate conversion and probability regression tests are mandatory. No client-side reward authority.

## 9. Fairness and accessibility
No paid competitive power. Every gameplay capability has a clearly documented free acquisition path. No timers, streak pressure or dark-pattern near-miss animations. Reduced-flash option and skip animations. Box opening is optional; bulk open available. Players can inspect potential contents before opening. Region/age restrictions override monetization.

## 10. Build order and acceptance
1. Reward tables + deterministic seeded tests + idempotent grant ledger.
2. Earnable fragments and ten-to-one crafting.
3. Starter box and five functional archetype definitions.
4. Three factions, supply network, deployable foundry and city persistence.
5. One playable Tower District cross-mode mission.
6. Aircraft upgrade tree and last-existence persistence preview.
7. World-authoring tools, moderation, server authority and audits.
8. Legal review before *any* paid-fragment or randomized monetization feature.

Acceptance: 100% of eligible activities grant exactly one intended reward; box odds match published tables in statistical tests; every gameplay archetype can be earned without payment; no reward timer; items persist across existence changes; time forks cannot mutate other players' saves.

## Open decisions
Exact drop rates, game age rating, legal territories, platform targets, faction names, final Last Number numeral, and full economic balancing require creator approval or testing. Do not fabricate these as finalized.
