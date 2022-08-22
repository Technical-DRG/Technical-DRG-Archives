---
tags:
    - modded
    - guide
---

# An Introduction to Modded Difficulties

| Post Info          |                                                                                          |
|--------------------|------------------------------------------------------------------------------------------|
| Author             | u/littlebobbytables9                                                                     |
| Date               | 2022-06-07                                                                               |
| Original Post Link | <https://www.reddit.com/r/technicaldrg/comments/v6l5hf/an_intro_to_modded_difficulties/> |

Since a lot of the posts in here are going to reference difficulty mods, I thought it would be good
to have a quick overview of the various mods and the effect those have on gameplay.

## Why Difficulty Mods?

Haz 5 has an upper limit when it comes to testing skill and builds. Past a certain individual skill
level solo stops being interesting very quickly unless you attempt increasingly arcane self-imposed
challenges like random builds, no-mod builds, and the like. You can do an ok job testing individual
skill in multiplayer by carrying very poor teammates, but finding those teams is inconsistent and
ultimately it's only a test of your individual skill. Ultimately, there is no way for haz 5 to test
good teamplay, because a good team will steamroll any vanilla content put in front of them, so we
have to turn to mods for missions where good teamplay is required.

Similarly it's also hard to test builds in haz 5. Essentially any build with sufficient individual
skill is enough to excel and even carry in haz 5, so it's difficult to test comparative statements
about different builds. You can take builds or even team compositions entirely devoted to either
single target or AOE with none of the other, and it doesn't have much of an impact on success rate
simply because neither of those things are required to succeed in haz 5. Worse, even what "good"
means is warped by the environment- if winning is practically guaranteed no matter what, builds or
strategies that have high ceilings but require more setup or time end up looking impotent as
everyone else kills all the enemies before you can execute- in the extremes, a "kill stealing meta"
where having high kills on the score screen is seen as proof of a good build even if their
contributions ultimately amounted to nothing, because contributing nothing isn't punished by vanilla
content.

So that's where difficulty mods come in, or at least the difficulty mods that we at
[r/technicaldrg](https://www.reddit.com/r/technicaldrg/) are interested in (see the breakdown later
in the post). They provide an environment that tests both individual skill and also teamplay in
multiplayer. They provide an environment that makes it very obvious the differences in power level
between builds. They require balanced compositions with strong single target and AOE. The good ones
preserve vanilla balance as much as possible. And they're very fun to play.

What they are not, ideally, is a power fantasy. While combining difficulty mods with other mods that
buff weapons or make other changes is a perfectly legitimate way to play the game, here we focus on
preserving the vanilla game as much as possible. All of the changes are there to make the game
harder, with a few exceptions out of necessity: if you don't increase doretta health and reduce the
nitra cost of resupplies it makes unfun failstates much too likely, much more likely than in
vanilla. Doing this keeps balance aligned with vanilla while still making the game much harder/more
skill testing. Therefore even if you're only interested in haz 5, the posts in this subreddit will
still be valid.

## How to Use Difficulty Mods

While there still exist standalone mods for some of these on mod.io, the Custom Difficulty mod has
basically made them obsolete since it can reproduce any other difficulty mod while also allowing
fine-grained control of any of the variables, changing difficulties without having to disband the
lobby, changing resupply cost and enemy cap without additional mods, and many other advantages.

It can be a bit overwhelming at first, but Custom Difficulty is easy to use if you just copy-paste
difficulty strings from [this repo](https://github.com/trumank/drg-custom-difficulties) which has
strings for many of the common difficulties like haz 6, 7, and 6x2. If it doesn't have a string for
your desired difficulty and that difficulty exists as a standalone mod, you can simply enable both
mods and Custom Difficulty will import the mod allowing you to save it as a new difficulty string.

!!! info "Custom Difficulty Presets"

    Link: <https://github.com/trumank/drg-custom-difficulties>


If you'd like to try your hand at modifying an existing difficulty, creating a new difficulty, or
simply understanding what all these numbers mean, Virryn wrote a great guide to Custom Difficulty
that you can read
[here](https://docs.google.com/document/d/131FqOl0FnwiAslvvDSYkV35oBQXYx2kH0oZYwEpjoBI).

!!! info "Custom Difficulty Guide"

    Link: <https://docs.google.com/document/d/131FqOl0FnwiAslvvDSYkV35oBQXYx2kH0oZYwEpjoBI>

But I'll give special attention to the most important one here:

### The Enemy Count Modifier

The common factor with nearly every difficulty mod is that they all increase the
`EnemyCountModifier` field in the hazard file. This variable serves as a multiplier on nearly[^1]
all spawns in the game so turning it up means more bugs. Doubling it will cause twice the bugs to
spawn, so if you ever see "5x3" or "6x2" that means taking the base difficulty, in this case haz 5
or haz 6, and then multiplying `EnemyCountModifier` by the multiplier.

!!! example

    ```json
    {
        "EnemyCountModifier": [
            0.85, // 1 player scaling
            0.85, // 2 players scaling
            1.25, // 3 players scaling
            1.5   // 4 players scaling
        ],
        // ...
    }
    ```

[^1]: Excludes regular brood nexus swarmer spawns, swarmer egg spawns, rival enemies, and dreads.

### Enemy Cap

The game has a limit on the number of enemies on the map at any one time, which by default is 60
swarmers and 60 enemies. Playing mods that increase the Enemy Count will quickly run into this cap,
blunting the effect of the increased spawns. Playing even just 5x2 will feel very different with the
vanilla enemy cap compared to a higher enemy cap, and if you want to play very high modifiers like
5x6 or 4x20 for the memes, you'll need to raise your cap extremely high. For most difficulties
people actually play, though, a cap of `[90, 120, 180, 180]` is going to be sufficient, where the
array goes from 1 player to 4 players.

!!! example

    ```json
    {
        "MaxActiveEnemies": [
            90,  // 1 player scaling
            120, // 2 players scaling
            180, // 3 players scaling
            180  // 4 players scaling
        ],
        // ...
    }
    ```

Another cap that exists in the game is the enemy aggro cap. By default only 32 enemies can be
aggroed on a given player at any time, so if you have more than 32 enemies on the map in a solo
mission (or more than 128 enemies in a 4 player mission) then the other enemies just path around
randomly until a slot opens up. Unfortunately, there is no way to change this with mods, at least
not yet, and it means that very high multipliers become more frustrating than difficult, as once you
fill the map with bugs they'll only come to you at a relatively slow but continuous trickle rather
than all at once.

## Common Difficulty Mods

!!! example "A Path to Hazard 6x2"

    For people who have never played modded difficulties or are new to modded difficulties, a
    reasonable progression from Hazard 5 to harder difficulties (e.g. Hazard 6x2) is to play
    the following chain of difficulties, becoming more comfortable in each before progressing to
    the next difficulty:

    \( \text{Hazard 6} \to \text{Hazard 5x2} \to \text{Hazard 6x1.5} \to \text{Hazard 6x2} \)

    - Hazard 6 lets you become more familiar with increased enemy movement speed, more disruptive
      enemies, increased attack damage, and other stats that are changed from Hazard 5.
    - Hazard 5x2 lets you become more familiar with larger swarm sizes.
    - Hazard 6x1.5 is harder than Hazard 6, but still not as hard as Hazard 6x2, letting you become
      more familiar with larger Hazard 6 swarms.
    - And finally is Hazard 6x2.

### Starship Troopers / Starship Troopers Elite

The most common difficulty mod by far, starship troopers is equivalent to haz 4 with a x2 modifier
and STE a x3 modifier. Haz 4 movement speed means that being able to kite is basically a cheat code
and in combo with halfway reasonable AOE removes much of the difficulty.

### Hazard 5 with Multipliers

The second most popular difficulty mod, most people play 5x2 with some 5x3 and the occasional 5xtoo
much lobby. Many people view these as just AOE fests, which is mostly true. While increasing the
enemy count modifier does lead to more bugs, making AOE better, it does also increases the number of
menaces, mactera, praetorians, etc. so there is also an increase in the value of or need for single
target damage. But haz 5 speed and damage means these difficulties are still pretty forgiving, so
they can be a good intro to modded difficulties.

### Hazard 6

Finally the good stuff. A longer explanation from Ike himself is here, but the general idea is that
Haz 6 started with a straightforward extrapolation from the jump from haz 4 to 5, and then was
adjusted with the goal of making a fun higher difficulty that preserved the base game balance as
much as possible. Note that some of the information in that document about what various difficulty
fields do is wrong, refer to virryn's document to be safe.

Enemy speed and damage is increased in haz 6, making kiting less effective (though still obviously
useful) and punishing poor movement or being out of position. Large enemy health increases, and
higher Enemy Diversity means a larger portion of the swarm is the more interesting enemies rather
than just grunts. Stationary enemy spawn rates are kicked way up, much higher than a straight
extrapolation, which makes different mission types feel very unique and further increases the value
of single target damage.

Overall ike did a good job making single target damage just as necessary as AOE clear. It's arguably
more valuable, since you'll usually want at least 2 single target focused teammates while generally
only needing 1 focused on AOE, though that's more a product of how each functions- twice as many
grunts requires barely any more AOE to deal with, while twice as many menaces will require twice as
much single target.

This is the difficulty I would most recommend to people starting to get bored with haz 5.

### Hazard 7

7 is pretty much just more of 6. Even higher enemy speed and projectile speed makes it very
punishing, especially with higher enemy damage on top. Very difficult and very much a test of
individual skill- it's easy to die to haz 7 bullshit if you aren't 100% paying attention (and
sometimes when you are lol). Slows, like that from sticky flames, become less effective since base
move speed is so high, so to actually hold a position with sticky requires more lines or additional
CC on top. Single target damage is arguably more important than AOE since there are so many special
and disruptive enemies.

### Hazard 6x2

Haz 6 with a x2 multiplier. This is the hardest difficulty that is commonly played. Compared to haz
7 it has more but more forgiving enemies. Compared to 5x2 there is a much higher need for single
target damage because of the swarm composition changes and the increase to stationary difficulty and
enemy health, making it very balanced. In contrast to 7 it's more a test of team composition and
synergy rather than individual skill (as much). Working effectively with your team and mastering
group movement through the cave is very important.

### Hazard 5x2 Spicy Edition

This one is new and actively updated, but aims to be a middle ground between 5x2 and 6x2 to aid in
that adjustment (or allow more experienced players to play a similar difficulty with more room for
not tryharding). Several variants exist at various points on the spectrum from 5x2 and 6x2.

### Hazard 7x1.5, 7x2, 6x3, etc.

Steps up from 6x2, these difficulties are rarely played and require a solid team. 7x1.5 is the most
comparable, generally being more punishing to mistakes but having a slightly smaller number of
enemies compared to 6x2. If you're playing these you probably didn't need to read this post lol.

*[STE]: Starship Trooper Elite
