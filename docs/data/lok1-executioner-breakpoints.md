---
tags:
    - breakpoints
    - data
    - lok-1
    - engineer
    - executioner
    - overclock
    - hazard-6
    - hazard-6x2
---

# LOK-1 Executioner Overclock Breakpoints (Hazard 6x2, 4 Players Scaling)

Important Upgrades:

- Tier 1: **Damage** vs. **Ammo** (+6 Damage) (+72 Ammo)
- Tier 3: **Electro-Chemical Rounds** (+20% Damage to Burning Targets, +20% Damage to Electrified
  Targets, Stacks)
- Tier 5: **Electric Generator Mod** (Triple-Locked Targets are Electrified) vs. **Unstable Lock
  Mechanism** (+20% Damage to Fully Locked Burst)

## Grunt, Guard, and Slasher Shot Count

!!! info "Assumptions"

    - Assumes all *weakpoint* shots hit.
    - Assumes enemies are *not* electrified or burning, except when inflicted by *Electric Generator
      Mod*.

    Death to Electric damage is denoted by +E. Fully locked bursts fired by
    *Unstable Lock Mechanism* denoted as FB; partial bursts denoted as PB.

| Build           | Grunt Head | Grunt Body[^1] | Guard Head[^2] | Guard Body  | Slasher Head | Slasher Body |
|-----------------|------------|----------------|----------------|-------------|--------------|--------------|
| 1XXX2 dmg, ULM  | 2FB / 2PB  | 4FB / 4-5PB    | 4FB / 6PB      | 10FB / 12PB | 2FB / 4PB    | 6FB / 7PB    |
| 1X1X1 dmg, EGM  | 2          | 4 / 3+E        | 5-6            | 10          | 3            | 6            |
| 2XXX2 ammo, ULM | 2FB / 3PB  | 6FB / 6-7PB    | 5FB / 8-9PB    | 13FB / 16PB | 3FB / 5PB    | 8FB / 9PB    |
| 2X1X1 ammo, EGM | 3          | 5 / 4+E        | 5-7            | 13 / 12+E   | 4 / 3+E      | 7            |

[^1]: Consistency against lightly armored enemies depends largely on Armor Break. If one shot in the
    burst breaks an armor plate, the burst will usually consume one less ammo as long as *one or more
    additional* bullets in the burst hit the exposed plate.
[^2]: LOK-1 interacts strangely with guard heads. I'm unsure what the exact issue is, but if you
    attempt to kill them in two partial bursts, you have a small chance of your burst consuming an
    extra bullet. With Electric Generator Mod, this makes sense, as it's unlikely the LOK-1 takes
    into account Electric DoT ticks when calculating whether or not to spend another bullet; I have
    no idea why this happens with Unstable Lock Mechanism.

Interesting Notes:

- Variable Electric tick rates cause highly inconsistent ammo consumption; fortunately this only
  slightly impacts TTK.

## Spitters and Weak Mactera Shot Count

!!! info "Assumptions"

    - Assumes all *weakpoint* shots hit.
    - Assumes enemies are *not* electrified or burning, except when inflicted by *Electric Generator
      Mod*.

    Death to Electric damage is denoted by +E. Fully locked bursts fired by
    *Unstable Lock Mechanism* denoted as FB; partial bursts denoted as PB.

| Build           | Web Body  | Acid Head | Acid Body   | Spawn WP    | Spawn Body  | Brundle WP     | Trijaw WP | Trijaw Body |
|-----------------|-----------|-----------|-------------|-------------|-------------|----------------|-----------|-------------|
| 1XXX2 dmg, ULM  | 2FB / 2PB | 2FB / 3PB | 5FB / 6-7PB | 2FB / 4PB   | 9FB / 10PB  | 7FB / 12PB     | 3FB / 6PB | 13FB / 16PB |
| 1X1X1 dmg, EGM  | 2         | 2         | 5 / 4+E     | 2           | 8 / 7+E     | 6-7            | 3         | 12 / 11+E   |
| 2XXX2 ammo, ULM | 2FB / 3PB | 2FB / 4PB | 6FB / 7-8PB | 3FB / 5PB   | 11FB / 13PB | 12-13FB / 17PB | 4FB / 7PB | 17FB / 20PB |
| 2X1X1 ammo, EGM | 2+E       | 3+E       | 6 / 5+E     | 3 / 3+E[^3] | 9           | 8-10[^4] / 9+E | 4         | 15 / 14+E   |

[^3]: If you are unlucky enough to hit a Spawn's leg with one bullet, the Electric proc will finish it off regardless.
[^4]: It is possible but difficult to kill a Brundle in one WP burst; it is likely that a few bullets will hit a leg or the wrong armor plate.

Interesting Notes:

- All three of these Mactera have a 50% Electric weakness.

## Big Targets Shot Count

!!! info "Assumptions"

    Assumes a relatively high percentage of weakpoint shots hit (est. ~15% margin of error). Exact
    breakpoints are not particularly helpful against some enemies as, in a practical situation,
    hitting every single shot on a weakpoint is extremely rare. As it is relatively uncommon for
    enemies to be ignited and electrocuted simultaneously, except for one special case noted below,
    stacked breakpoints will only be provided for Electric Generator Mod builds.

    Ignition is denoted by (F); electrocution is denoted by (E). For simplicity, assumes all
    Unstable Lock Mechanism shots are in full bursts.Enemies ignited by Burning Hell's fire cone or
    (for ULM builds) electrocuted by GK2's Electrifying Reload for minimal additional damage.

| Enemy                  | 1X1X2 dmg, ULM                               | 1X1X1 dmg, EGM (E)   | 2X1X2 ammo, ULM                                | 2X1X1 ammo, EGM (E)  | Notes                                                                                                                                                                                |
|------------------------|----------------------------------------------|----------------------|------------------------------------------------|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Praetorian             | 28 / 22 (F) / 22 (E)                         | 26 (E) / 21 (E+F)    | 35 / 27 (F) / 27 (E)                           | 33 (E) / 26 (E+F)    |                                                                                                                                                                                      |
| Oppressor              | 33 / 30 (F)                                  | 39 (E) / 35 (E+F)    | 42 / 38 (F)                                    | 50 (E) / 45 (E+F)    | immune to Electric                                                                                                                                                                   |
| Warden (organ)         | ~14 / ~8 (F) / ~12 (E)                       | ~13 (E) / ~12 (E+F)  | ~17 / ~12 (F) / ~14 (E)                        | ~20 (E) / ~15 (E+F)  | Wardens flinch, making landing bursts difficult                                                                                                                                      |
| Menace                 | ~18 / ~12 (F) / ~13 (E)                      | ~16 (E) / ~13 (E+F)  | ~20 / ~15 (F) / ~16 (E)                        | ~20 (E) / ~15 (E+F)  | Menaces will flinch                                                                                                                                                                  |
| Goo Bomber             | 23 / 14 (F) / 15 (E)                         | 23 (E) / 13 (E+F)    | 35 / 22 (F) / 24 (E)                           | 33 (E) / 24 (E+F)    | sacks pop after 3 bullets; weak to fire, but not Electric                                                                                                                            |
| Grabber                | ~7 / ~5 (F) / ~6 (E)                         | ~8 (E) / ~6 (E+F)    | ~9 / ~7 (F) / ~8 (E)                           | ~9 (E) / ~7 (E+F)    | difficult but possible to land a full burst on WP; status effects make threshold more forgiving and keep Grabber idle for longer                                                     |
| Breeder                | 20 / 16 (F) / 16 (E)                         | 18 (E) / 15 (E+F)    | 24 / 19 (F) / 20 (E)                           | 24 (E) / 19 (E+F)    |                                                                                                                                                                                      |
| Patrol Bot             | 11 / 9 (E)                                   | 11 (E)               | 14 / 11 (E)                                    | 14 (E)               | 30% Electric weakness                                                                                                                                                                |
| Bulk (WP's)            | 48+74 / 48+34 (F) / 48+34 (E) / 48+ ~5 (E+F) | 48+68 / 48+31 (E+F)  | 48+104 / 48+50 (F) / 48+50 (E) / 48+ ~17 (E+F) | 48+96 / 48+46 (E+F)  | it takes more than one 8-bullet burst to pop a weakpoint; assumes all bursts that pop WPs are still full 8-bursts; simultaneous ignition achieved with Hellfire + Electric Trail mod |
| Bulk (IFG'd, WP's) (I) | 48 (I) / ~38 (I+F)                           | 48+24 (I) / 42 (I+F) | 48+10 (I) / 48 (I+F)                           | 48+31 (I) / 46 (I+F) | IFG overrides Electric status                                                                                                                                                        |
| Shellback (rolled)     | ~22 / ~24 (F)                                | ~32 (E) / ~26 (E+F)  | ~36 / ~28 (F)                                  | ~48 (E) / ~36 (E+F)  | depends highly on armor RNG; immune to Electric status                                                                                                                               |
| Shellback (eyes)       | N/A                                          | N/A                  | N/A                                            | N/A                  | unless you have a height advantage, very difficult to reliably hit eyes                                                                                                              |
| Youngling (rolled)     | ~6 / ~3 (F)                                  | ~6 (E) / ~5 (E+F)    | ~7 / ~4 (F)                                    | ~7 (E) / ~5 (E+F)    | depends highly on armor RNG; immune to Electric status                                                                                                                               |

Interesting Notes:

- While most enemies have neither an Electric nor a Fire resistance/weakness, the Fire DoT typically
  does more damage on its own than Electric does, so ignited bugs will often die in fewer shots than
  electrified bugs

## Conclusion

EGM builds are marginally better against smaller stuff. The Electric DoT helps chip them down faster
and sooner than ULM can. The slow from Electric can also be quite helpful against quick moving
targets like Praetorians, and can keep Grabbers off your back longer than they otherwise would be.

The main reason to take ULM is Bulks and Dreads. Dreads have Electric resistance, so there's no
contest there. Against Bulks, there are plenty of team-wide options for consistently proccing both
Electric (or IFGs) and Fire; almost any team worth their salt is likely to have one or the other,
and more often than not they'll have one or more of each. In this department, the difference in ammo
consumption and TTK between ULM and EGM is a gulf. If your team is bringing a [Volatile
Bullets](../builds/volatile-bullets.md) gunner to be the designated Bulk shredder, you can take EGM
and your conscience will be scot-free; but if you're the main weakpoint hammerer, you'll dearly miss
having ULM.


*[OC]: Overclock
*[FB]: Full Bursts
*[PB]: Partial Bursts
*[ULM]: Unstable Lock Mechanism
*[EGM]: Electric Generator Mod
*[DoT]: Damage Over Time
*[TTK]: Time to Kill
*[WP]: Weakpoint
