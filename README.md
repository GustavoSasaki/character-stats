# Easy Custom Movesets
This is an extension of Squishy6094 [character-select-coop](https://github.com/Squishy6094/character-select-coop). 

Its objective is to make customizing character movesets easier, such as increasing jump strengths, gravity, or swimming speed.

You can find examples in the [initial-characterstats-table.lua](https://github.com/GustavoSasaki/character-stats/blob/main/initial-characterstats-table.lua).


## Important Stats

| Name              | Explanation | Default Value | Observation |
| :---------------- | :------: | :-------: | :-------:|
| gravity       |   How much gravity affects the character (percentage).  | 100 | |
| jump_strength       |   How much higher all jumps are (percentage).  | 100 | Impacts only the jump constant. Single/double jump velocity depends on a constant and forward velocity.|
| walking_speed       |   How much faster the character can walk  (percentage).  | 100 | |
| in_air_speed       |   How much faster the character can move horizontally in the air  (percentage).  | 100 | |
| swimming_speed       |  How much faster the character can swim (percentage).  | 100 | |
| dive_velocity       |   Changes the constant forward velocity added when diving.   | 100 | |
| dive_max_velocity       |   Increases the max forward velocity cap for dives (percentage).  | 100 |  |
| long_jump_velocity_multiplier       |   When diving, an multiplier is applied to current forward velocity. Increases this multiplier (percentage). | 100 | The multiplier value is 1.5|
| long_jump_max_velocity       |  Increases the max forward velocity cap for long jumps (percentage).  | 100 |  |

## Less Important Stats

| Name              | Explanation | Default Value | Observation |
| :---------------- | :------: | :----: | :-------:|
| fall_gravity       |  Gravity effect when falling (y velocity < 0) (percentage).  | gravity (100) | |
| hold_walking_speed       |  How much faster the character can walk while holding something  (percentage). | walking_speed (100) | |
| crawling_speed       |  How much faster the character can crawl (percentage). | walking_speed (100) | |
| grounded_slowing_speed       |  How much faster the character moves while decelerating in the ground | 100 | The higher the value, the more slippery the character feels. Unfortunately, the forward velocity is always reset to zero when landing from a jump, making this stat harder to notice. |
| explode_on_death       |  Creates a small explosion on death.| false | A "troll" stat. |
| airborne_deceleration_speed       |  Changes deceleration speed in the air (percentage). | 100 |	The velocity change is minimal.|
| single_jump_strength       |   	Increases the height of single jumps (percentage). | 100 ||
| double_jump_strength       |   Increases the height of double jumps (percentage). | 100 | |
| triple_jump_strength       |  Increases the height of triple jumps (percentage). | 100 | |
| back_flip_strength       |   Increases the height of backflips (percentage).  | 100 | |
| side_flip_strength       |   Increases the height of side flips (percentage).  | 100 | |
| long_jump_strength       |   Increases the height of long jumps (percentage). | 100 | |
| kick_jump_strength       |   Increases the height of kick jumps (percentage). | 100 | |
| dive_y_vel       |  Adds vertical velocity when diving (units). | 0 |  Normally, diving gives no vertical velocity.|

## Instalation
- Download the character-select-coop ZIP file from [releases](https://github.com/Squishy6094/character-select-coop/releases) and unzip into mod folder
- Download the character-stats ZIP file from [releases](https://github.com/GustavoSasaki/character-stats/releases) and unzip into mod folder


## How customize your character

### Integrating your mod
Inside your main.lua, after **_G.charSelect.character_add** , you can change character stats by executing **_G.customMoves.character_add**.

```
    _G.charSelect.character_add("Custom Model", {"Custom Model Description", "Custom Model Description"}, "Custom Model Creator", {r = 255, g = 200, b = 200}, E_MODEL_CUSTOM_MODEL, CT_MARIO, get_texture_info("custom-icon"))
    if _G.customMovesExists then
        _G.customMoves.character_add({name="Custom Model",swimming_speed=500})
    end
```

### Integrating other people mod
If you can't modify the mod files directly, you can submit a pull request to update the file [initial-characterstats-table.lua](https://github.com/GustavoSasaki/character-stats/blob/main/initial-characterstats-table.lua).


## Mods Integrated
- [Azumanga Daioh](https://mods.sm64coopdx.com/mods/azumanga-daioh-64-pack.205/)
- [Cream the Rabbit](https://mods.sm64coopdx.com/mods/cs-cream-the-rabbit.282/)
- [Hatsune Miku](https://mods.sm64coopdx.com/mods/cs-hatsune-miku.418/)
- [Pepsiman](https://mods.sm64coopdx.com/mods/cs-pepsiman.88/)
- [SackBoy](https://mods.sm64coopdx.com/mods/cs-sackboy.459/)
- [Silver](https://mods.sm64coopdx.com/mods/silver-the-hedgehog-cs.398/)
- [Sonic Classic and Modern Pack](https://mods.sm64coopdx.com/mods/cs-sonic-classic-and-modern-pack.444/)