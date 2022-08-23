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

The following is a list of effects that are considered "*environmental slow-down effects*" by
the game (non-exhaustive):

!!! warning "Incomplete List"

    This list is **incomplete**.

- Cobwebs
- Goo (both naturally generated, like in Fungus Bogs, and those produced by Goo Bombers)
- Heavy snow (naturally occuring in Glacial Strata)
- Storms (ice storms and sand storms)
- Earthquakes (like in Magma Core and Glacial Strata)
- Frost Praetorian Frost Spray
- Electric Crystals (Crystalline Caverns)

!!! error "Environmental?"

    The in-game description of the perk states "environmental" slow-down effects, even though some
    of these effects could be interpreted as "enemy-induced" slow-down effects.

## Experimental Footage

<figure markdown>
  <iframe width="560" height="315" src="https://www.youtube.com/embed/M8wAqeL2tRI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
  <figcaption>Unstoppable works against Electric Crystal slow-down effect</figcaption>
</figure>

## References

- [Unstoppable | Deep Rock Galactic Wiki](https://deeprockgalactic.fandom.com/wiki/Unstoppable)
- `FSD-WindowsNoEditor\FSD\Content\GameElements\KPI\Perks\PERK_StrongBack.uasset`
    - `PST_MovementSpeedPenaltyReduction`
        - `EPawnStatType::Additive`

!!! construction "Pending Game Files Verification"

    The list here isn't verified via game files yet. Looking for method to search through all
    `STE_*` files that have a

    ```json
    StatChangeStatusEffectItem {
        Stat {
            PST_MovementSpeedEnvironmentalPenalty: -10 // for example
        }
    }
    ```

    property. Examples:

    - `FSD-WindowsNoEditor\FSD\Content\Landscape\Biomes\Biomes_Ingame\SandblastedCorridors\STE_SandStorm-Slowdown.uasset`
    - `FSD-WindowsNoEditor\FSD\Content\Enemies\FlyingBug\Bomber\STE_BomberPuddle.uasset`
