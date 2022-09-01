---
tags:
    - animation-cancelling
    - grenade
    - throwable
    - tips-and-tricks
    - double-bind
    - game-settings-ini
---

# Grenade Cancelling

!!! info "Version"

    Working as of Update 36, Patch 6.

Description by Virryn at [How to Double Bind Grenade Cancelling in Deep Rock
Galactic](https://gist.github.com/Virryn/d6385d3a262b17039e6602c5b34ef01c) reproduced here:

1. In-game, set your Grenade keybind to whatever you wish (for this example, `MiddleMouseButton`).
2. Find `steam\steamapps\common\Deep Rock Galactic\FSD\Saved\Config\WindowsNoEditor`.
3. Open `GameUserSettings.ini` in a text editor.
4. Scroll down to `CustomKeyBindings`. Note that this will not display default keybindings; only
actions with a custom keybinding (including manually unbound actions).

    - This is under the `[/Script/FSD.FSDGameUserSettings]` section.

5. Find or make `CustomKeyBindings=(ActionName="LaserPointer",Index=1,Key=???)`. The Laser Pointer
is most recommended, as it does not cancel your sprint and does not swap your weapon. Pickaxe and
weapon swap are also viable; I am unsure what their exact `ActionName`s are.

    - `Index=0` means that keybind is the *main* keybind.
    - `Index=1` means an *alternate* keybind.

6. It is recommended to change only the alternate keybinds, i.e. those with `Index=1`.
7. Set `Key=` to your Grenade keybind (which can be found under `ActionName="Grenade"`; for this
example, `MiddleMouseButton`) When pressed multiple times in quick succession, the middle mouse
button should now quickly throw multiple grenades.

!!! example "Using Laser Pointer's Alterative Keybind to Grenade Cancel"

    ```ini
    [/Script/FSD.FSDGameUserSettings]
    ...
    # Grenade is thrown using `G` key here.
    CustomKeyBindings=(ActionName="Grenade",Index=0,Key=G)
    CustomKeyBindings=(ActionName="Grenade",Index=1,Key=None)
    # Use Laser Pointer to grenade cancel; set alternative keybind to share the same keybind as
    # grenade toss.
    CustomKeyBindings=(ActionName="LaserPointer",Index=0,Key=LeftControl)
    CustomKeyBindings=(ActionName="LaserPointer",Index=1,Key=G)
    ```

## References

- MountAndDewMe:

!!! quote "How to Double Bind (aka a technique to grenade/axe cancel with only ONE key)"

    How to Double Bind (aka a technique to grenade/axe cancel with only ONE key)
    Open the following file:
    `C:\Program Files (x86)\Steam\steamapps\common\Deep Rock Galactic\FSD\Saved\Config\WindowsNoEditor\GameUserSettings.ini`.

    - Scroll down to `CustomKeyBindings` section.
    - Edit the second `CustomKeyBindings` for `LaserPointer`:
      `CustomKeyBindings=(ActionName="LaserPointer",Index=1,Key=G)`. If you don't have it, just
      make one. (Note you can use other keybinds that allows you to cancel animation like Pickaxe or
      Previous Weapon, but `LaserPointer` is the most useful because 1) it does not cancel your
      sprint and 2) it pulls out `LaserPointer` which reveals the HUD).
    - Take note here that the specific `CustomKeyBinding` entry you're editing has Index not equal
      to 0 and Key must be whatever key you have set for the Grenade keybind (Note: Although this
      guide says double binding, you can technically set multiple binds for a specific action; i.e.,
      you have more than two `CustomKeyBinds` for a specific action. The `CustomKeyBind` you're
      editing just has to not be `Index=0` to not edit the main keybind).

    Example:

    One of the keybinds to use my grenade is set to `G`. Thus, I need to set the alternate key
    (`Index=1`) for `LaserPointer` to the same key, `G`:

    ```ini
    CustomKeyBindings=(ActionName="Grenade",Index=0,Key=G)
    ...
    CustomKeyBindings=(ActionName="LaserPointer",Index=1,Key=G)
    ```

    So in my case, my primary keybind `(Index=0)` for grenade is `R`. Therefore I have to set the alternate key (which is what `Index=1` stands for) for `LaserPointer` to `R`:

    ```ini
    CustomKeyBindings=(ActionName="Grenade",Index=0,Key=R)
    CustomKeyBindings=(ActionName="Grenade",Index=1,Key=None)
    CustomKeyBindings=(ActionName="LaserPointer",Index=0,Key=ThumbMouseButton2)
    CustomKeyBindings=(ActionName="LaserPointer",Index=1,Key=R)
    ```

- Virryn: [How to Double Bind Grenade Cancelling in Deep Rock Galactic](https://gist.github.com/Virryn/d6385d3a262b17039e6602c5b34ef01c)
