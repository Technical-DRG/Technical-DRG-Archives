---
tags:
    - game-mechanics
    - overclock
    - bullets-of-mercy
    - scout
    - gk2
---

# Bullets of Mercy (Scout GK2 Overclock)

!!! info "Game Version"

    Title Update 36, Patch 6

## What Triggers Bullets of Mercy Bonus Damage?

The OC's in game description states that

!!! quote "Bullets of Mercy in-game description"

    Deal bonus damage to burning, stunned, electrocuted, frozen, or poisoned targets.

However, that's not entirely clear. We dug through the game's assets, which lists:

!!! example "`FSD-WindowsNoEditor\FSD\Content\WeaponsNTools\AssaultRifle\Overclocks\OC_BonusesAndPenalties\OC_Bonus_DamageVsStatusAndState_GK2.uasset`"

    ```
    StatusEffects
        STE_Grenade_IFG_SlowMovement_C
        STE_ElectricSMG_C
        STE_ElecticPlant_slowdown_C
        STE_Electric_BurstPistolMines_C
        STE_M1000_Electrocution_C
        STE_Revolver_Neurotoxin_C
        STE_Grenade_Neurotoxin_C
        STE_Electric_Plasma_Linecutter_C
        STE_EnemySlowdown_LockOnRifle_C
        STE_TaserArrowArc_Enemies_Damage_C
        STE_Crossbow_TaserArrows_C
        STE_ElectricTrail_Coilgun_C
        STE_ContrailBase_CoilGun_C
        STE_Crossbow_Pheromone_C
        STE_Crossbow_ChemicalExplosion_C
        STE_EnemySlowdown_HeavyParticleCannon_C
        STE_EnemySlowdown_MicrowaveGun_C
        STE_HellfireTrail_CoilGun_C
        STE_RadiationEnemy_MicrowaveGun_C
        STE_RadiationCloud_MicrowaveGun_C
        STE_Radiation_MiniNuke_Enemy_C

    TargetStates
        ETargetStateDamageBonusType::Frozen
        ETargetStateDamageBonusType::OnFire
        ETargetStateDamageBonusType::Staggered
    ```

In other words, so as long as an enemy is affected by one of the listed status effects and/or
is under one of the listed `TargetStates`, Bullets of Mercy will deal bonus damage. The list, in
human-readable form:

- Status Effects:
    - IFG grenade slow
    - SMG electrocution (Engineer's stubby eletrocution status effect)
    - Electric crystal slowdown (Crystalline Caverns)
    - Electro Minelets mine electrocution (Gunner's BRT7 OC)
    - Electrifying Focus Round electrocution (Scout's M1000 OC)
    - Bulldog T5B Neurotoxin Coating (Gunner's secondary)
    - High-Voltage Crossover electrocution (Engineer's Breach Cutter OC)
    - Neuro-Lasso slowdown (Engineer's LOK-1 OC)
    - Taser Bolts, both individual bolt proximity DoT and the electric arc electrocution between
      bolts (Scout's Boltshark Crossbow, T1C)
    - Coilgun's electric trail (Gunner's secondary T5C)
    - Coilgun's base trail (Gunner's secondary)
    - Crossbow's pheromone bolts (Scout's Boltshark Crossbow, T1A)
    - Crossbow's chemical explosion bolts (Scout's Boltshark Crossbow, T1C)
    - Dazzler Module slowdown (Engineer's Shard Diffractor, T5C)
    - Densification Ray slowdown (Driller's Wave Cooker, T3A)
    - Hellfire's trail (Gunner's Coilgun OC)
    - Gamma Contamination radiation status effect (Driller's Wave Cooker OC)
    - Fat Boy's radiation status effect (Engineer's PGL OC)
- Target States:
    - Frozen (e.g. frozen from cryo bolts, cryo cannon, cryo grenades)
    - Ignited (e.g. from white phosphorous boomstick, TEF heat)
    - Stunned (e.g. M1000 stun, GK2 stun)

!!! warning

    The previous list is a whitelist, any status effects and target states not listed will not
    enable Bullets of Mercy bonus damage.

    Notably,

    - Turret Arc status effect will **not** enable BoM bonus damage. This is likely an oversight...

## References

- [Bullets of Mercy | Deep Rock Galactic Wiki](https://deeprockgalactic.fandom.com/wiki/Deepcore_GK2#Bullets_of_Mercy)
- `FSD-WindowsNoEditor\FSD\Content\WeaponsNTools\AssaultRifle\Overclocks\OC_BonusesAndPenalties\OC_Bonus_DamageVsStatusAndState_GK2.uasset`

*[OC]: Overclock
*[BoM]: Bullets of Mercy
*[IFG]: Inhibitor-Field Generator
*[DoT]: Damage over Time
*[TEF]: Thermal Exhaust Feedback
