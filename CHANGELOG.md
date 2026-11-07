# Changelog

All notable changes to ApexShock are documented in this file.

The format is based on Keep a Changelog, and this project adheres to Semantic Versioning.

## [v0.3.1] - 2026-11-07

### Added
- Godot 4.3 2D HDR Glow and WorldEnvironment post-processing pipeline:
  - Enabled viewport 2D HDR buffer (`rendering/viewport/hdr_2d=true`) in project configuration.
  - Added WorldEnvironment with Canvas background mode, Screen blend mode, ACES tonemapping, 1.20 saturation, and 1.12 contrast enhancement.
- Overhauled destructible barrier obstacles (`scenes/arena/destructible_cover.gd`):
  - Replaced primitive flat rectangle drawing routines with textured 3D isometric metallic structures (`assets/props/metalStructure_NE.png`).
  - Added ambient occlusion drop shadows, gunmetal foundation chassis, and glowing HDR energy conduits with damage-reactive color shifts.
- Volumetric particle textures and dynamic illumination:
  - Integrated CC0 textured smoke puffs (`smoke_04.png`) and spark lens flares (`spark_05.png`, `light_01.png`) into `ImpactSparks`.
  - Added dynamic PointLight2D illumination to the central crystal mine pit (`scenes/arena/gem_mine.gd`) and the top-center Aegis Reactor Core (`scenes/arena/arena.gd`).
  - Added cel-shaded silhouette outline passes to hero character sprites (`src/combat/brawler.gd`) for sharp cartoon contrast.
  - Added star lens flare bursts to muzzle flashes and volumetric plasma coronas to tactical combat VFX.
  - Upgraded Overdrive foot aura and projectile energy trails with luminous HDR bloom channels.
- 3D Pickups, Crates and Showcase Polish:
  - Replaced flat diamond pickups with 2.5D faceted isometric crystals (`scenes/arena/gem_pickup.gd`) featuring hover bobbing, ground drop shadows, and sparkle glints.
  - Upgraded Power Cube crates (`scenes/arena/power_cube_crate.gd`) with 3D alloy textures and glowing emerald cores.
  - Added spotlight stage cones, orbiting pedestal energy nodes, and cel-shaded hero showcases in the Armory hub (`src/ui/lobby_armory_menu.gd`).
- Luminous HDR Aiming Indicators and Dual Touch Controls:
  - Upgraded line, cone, and lob targeting reticles (`src/combat/aim_reticle.gd`) with luminous HDR laser cores, dark high-contrast backings, and precision crosshair pips.
  - Added pulsating golden HDR bloom rings and emblem flares to the Super ability virtual joystick (`src/ui/virtual_joystick.gd`) when fully charged.
- Volumetric Showdown Storm and Combat Floating Text:
  - Added 36 volumetric billowing smoke particles around the contracting toxic fog perimeter (`scenes/modes/showdown_mode.gd`) with dynamic hazard tinting.
  - Upgraded floating damage popups (`src/combat/floating_damage_label.gd`) with 4-pass comic black outline shadows and star lens flares on critical hits.
- End-of-Match Victory Splash and Sprint Locomotion Juice:
  - Added full-screen Victory and Defeat end-of-match modal splash (`src/ui/match_hud.gd`) featuring frosted glass backdrop, Star Player MVP banner, 3-tier reward progression cards (+8 Trophies, +60 Credits, +140 Mastery XP), and replay controls.
  - Added dynamic athletic sprint tilt and low-health pulsating danger warning halos (`src/combat/brawler.gd`) when hero vitality drops below 30%.

## [v0.3.0] - 2026-10-24

### Added
- Original Solaris Rift 3D visual identity and environment assets:
  - 65-degree top-down 3D Solaris Rift arena background (`assets/sprites/solaris_rift_arena_bg.png`) and 3,000 HP Aegis Reactor Core objective (`assets/sprites/prop_reactor_core.png`).
  - Original 3D Vanguard Hero roster (`assets/sprites/hero_*.png`): Volt (Kinetic Shock Tank), Valkyrie (Solar Marksman), Cinder (Magma Artillery), Bastion (Siege Juggernaut), Tesla (Arc Technomancer), and Phantom (Void Skirmisher).
  - Original 3D tactical arena props (`prop_alloy_crate.png`, `prop_plasma_cells.png`, `prop_flora.png`) and extruded Neo-Alloy barriers (`DestructibleCover`).
- 4-Tier Hero Skill System and Max-Tier Overdrive Transformation (`AbilityController`, `Brawler`):
  - Primary Attack, Super Ability, 2 selectable Active Gadgets per Hero (3 charges per match, 5.0s cooldown), and 2 selectable Star Passive skills per Hero.
  - Max-Tier Overdrive transformation (`[H]` or Overdrive button) granting +25% movement speed, +25% attack damage, +20% phase shield, and a neon-purple lightning aura ring for 5.0 seconds.
- Full-screen interactive Vanguard Lobby and Armory Skill Loadout Menu (`src/ui/lobby_armory_menu.gd`):
  - Toggled via `[TAB]` or `[M]` or the top-left Armory button, featuring a 3D Hero showcase pedestal, Offense/Defense/Utility stat bars, clickable Gadget and Star Passive loadout slots, Event Mode selector, and golden Battle deploy button.
- Upgraded Combat HUD and Typography (`src/ui/match_hud.gd`, `src/ui/hero_selector_hud.gd`):
  - Open-source OFL display fonts (`LilitaOne-Regular.ttf` and `RussoOne-Regular.ttf`) configured as project theme typography.
  - Custom 3D glossy skill and progression icons (`icon_overdrive.png`, `icon_gadget.png`, `icon_star_passive.png`, `icon_trophy.png`, `icon_shards.png`, `icon_credits.png`).
  - Ergonomic right-thumb Skill Cluster (`[G] Gadget` and `[H] Overdrive` circular buttons), top-right peripheral Kill and Objective Feed, bottom-left Equipped Loadout badge, and `[1]-[6]` Hero hot-swap bar.
- Polyphonic Combat Sound Manager (`src/core/sound_manager.gd`) and 6 synthesized 16-bit PCM `.wav` sound effects (`laser_shot.wav`, `plasma_impact.wav`, `super_surge.wav`, `reactor_breach.wav`, `ui_select.wav`, `victory_chime.wav`).
- Expanded automated headless unit test suite to 24 tests covering Overdrive multipliers and Armory slot selection.

## [v0.2.0-alpha] - 2026-10-24

### Added
- Four distinct brawler archetypes with unique tactical combat behaviors:
  - Vanguard (Marksman): Precision sniper rifle with fast long-range velocity.
  - Colossus (Tank): Heavy shotgun burst and Tank Trait passive (incoming damage converts to Super charge).
  - Specter (Assassin): Poison daggers dealing damage-over-time ticks and high-velocity jump Super leap.
  - Mortar (Artillery): Parabolic lob shells bypassing walls with area-of-effect impact detonation.
- Tactical AbilityController managing 3-charge active Gadgets and Star Power passives:
  - Vanguard Gadget: Quick-reload restoring 2 ammo slots immediately.
  - Colossus Gadget: Reactive shield absorbing 40% incoming damage for 3.5 seconds.
  - Specter Gadget: Smoke bomb providing 3.0 seconds stealth.
  - Mortar Gadget: Defensive close-range shockwave knockback burst.
- Solo Showdown Battle Royale game mode controller:
  - Continuously contracting lethal poison fog ring forcing brawlers to the arena center.
  - Destructible Power Cube crates spawning collectible stat-boosting cubes.
  - Collectible Power Cubes granting permanent +400 max health and +10% attack damage scaling.
  - Survival evaluation tracking last brawler standing.
- Decoupled EventBus signals for gem drops, team gem totals, and brawler gem inventory tracking.
- Expanded headless unit test suite from 11 to 22 tests covering archetypes, gadgets, star powers, and showdown mechanics.
- Deployed pre-compiled binary bytecode package (.gdc) to GitHub Releases.

## [v0.1.0-alpha] - 2026-10-24

### Added
- Core mobile engine foundation built for Godot 4.3 Vulkan Mobile renderer.
- Dual-stick virtual touch controls with floating dynamic movement stick and aimed combat stick.
- Dynamic targeting reticle supporting line, cone, and parabolic lob trajectories.
- Quick-tap auto-aim targeting system acquiring the closest hostile brawler in range.
- Segmented 3-slot ammo controller with independent progressive reload timers.
- Tactical out-of-combat health regeneration controller (+14% max HP/sec after 3.0s idle).
- Zero-allocation projectile, impact spark, and floating combat text recycling via ObjectPool.
- Stealth high-grass bush zones providing line-of-sight concealment.
- Destructible barriers absorbing standard fire and demolished by Super abilities.
- Objective gem mine producing kinetic crystals and 15-second victory countdown logic.
- Autonomous offline Bot AI driven by a three-state Finite State Machine (Patrol, Engage, Retreat).
- Trauma-based 2D screen shake camera with non-linear decay.
- Automated release packaging pipeline with AES-256 bytecode encryption in scripts/build_secure_release.ps1.
- Unit test suite in tests/unit/test_brawler_combat.gd covering ammo depletion, reload timers, health regeneration delays, and super meter charging.
- Full architectural and security documentation suite.

### Changed
- Upgraded the arena from 2v2 to a complete 3v3 offline match.
- Replaced immediate team gem scoring with brawler-carried gems that drop on elimination.
