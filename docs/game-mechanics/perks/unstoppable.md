---
tags:
    - perks
    - unstoppable
---

# Unstoppable

!!! info "Game Version"

    Title Update 36, Patch 6

<figure markdown>
  ![Unstoppable](./perk-icons/unstoppable.png){ loading=lazy, align=left, width=128 }
  <figcaption>Unstoppable Perk</figcaption>
</figure>

**Unstoppable** is a *passive perk* that mitigates "**environmental slow-down effects**" and allows
you to walk faster while carrying heavy objects. The in-game description for the max tier
Unstoppable Perk states:

!!! quote "Unstoppable"

    Nothing holds you back! Environmental slow-down effects are reduced by 50%! You move 25% faster
    while carrying heavy objects!

However, Unstoppable doesn't *only* mitigate environmental slowdown effects -- it apparently also
mitigates slowdown effects from some non-environmental sources too, such as Slasher slow. Here is
an incomplete list of environmental and non-environmental slowdown effects that Unstoppable seems to
mitigate:

!!! warning "Incomplete List"

    This list is **incomplete**.

- Cobwebs
- Goo (both naturally generated, like in Fungus Bogs, and those produced by Goo Bombers)
- Deep snow (naturally occuring in Glacial Strata)
- Storms (ice storms and sand storms)
- Earthquakes (like in Magma Core and Glacial Strata)
- Frost Praetorian Frost Spray
- Electric Crystals (Crystalline Caverns)
- Slasher attack slow
    - `FSD\Content\Enemies\Spider\Grunt\Attacker\STE_GruntAttacker_Slow.uasset`
- Shocker slow (Dense Biozone, Glacial Strata)
    - `FSD\Content\Landscape\ReactiveTerrain\STE_ElectricJelly_Stun.uasset`

Pending verification:

- Creeper vines DoT and SideDamage (Hollow Bough)
    - `FSD\Content\Landscape\ReactiveTerrain\STE_CreeperVine_DoT.uasset`,
    - `FSD\Content\Landscape\ReactiveTerrain\STE_CreeperVine_SideDamage.uasset`
- Hollow Bough branches `FSD\Content\Landscape\ReactiveTerrain\STE_HollowBoughBranches.uasset`
- Hot Rock (Magma Core) `FSD\Content\Landscape\ReactiveTerrain\STE_HotRockRT-DoT.uasset`
- Low Friction Ice (Glacial Strata)
  `FSD\Content\Landscape\ReactiveTerrain\STE_LowFrictionIceRT.uasset`

Notably unaffected:

- Pickaxe slow when you use it `FSD\Content\WeaponsNTools\Pickaxe\STE_Pickaxe_SlowUser.uasset`

## Experimental Footage

<figure markdown>
  <iframe width="560" height="315" src="https://www.youtube.com/embed/M8wAqeL2tRI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
  <figcaption>Unstoppable works against Electric Crystal slow-down effect</figcaption>
</figure>

## References

- [Unstoppable | Deep Rock Galactic Wiki](https://deeprockgalactic.fandom.com/wiki/Unstoppable)
- `FSD-WindowsNoEditor\FSD\Content\GameElements\KPI\Perks\PERK_StrongBack.uasset`
    - `PST_MovementSpeedPenaltyReduction`

!!! construction "Pending Game Files and Empirical Verification"

    The list here isn't verified via game files yet. Looking for method to search through all
    `STE_*` files that have a `PST_MovementSpeedEnvironmentalPenalty` or `PST_MovementSpeedPenalty`
    property. Examples:

    - `FSD\Content\Landscape\Biomes\Biomes_Ingame\SandblastedCorridors\STE_SandStorm-Slowdown.uasset`
    - `FSD\Content\Enemies\FlyingBug\Bomber\STE_BomberPuddle.uasset`
    - `FSD\Content\Enemies\Spider\Grunt\Attacker\STE_GruntAttacker_Slow.uasset`

    The game also seem to use multiple properties that are related to movement speed and penalities
    affecting it:

    - `PST_MovementSpeed`
    - `PST_MovementSpeedPenalty`
    - `PST_MovementSpeedEnvironmentalPenalty`
