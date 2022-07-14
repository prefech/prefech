---
title: "Adding Zones"
weight: 50
---

Adding more zones is very simple.  
All you have to do is add the zone to the `config/zones.lua` file

Example new Zone:
```lua
Zones.GasStation = {
    ['Type'] = 'Sphere',
    ['Height'] = 60,
    ['BorderColor'] = {0, 255, 0},
    ['WeaponBypass'] = {},
    ['Coords'] = vec3(2004.90, 3774.25, 32.40),
    ['Range'] = 20,
}
```
Setting | value | Usage |
--- | --- | --- |
Type | This can be `Sphere` or `Polyzone` | Define what type of zone this is. |
Height | Needs to be a number | Only used for Polyzones to set the height. |
Border Color | `{0, 255, 0}` *RGB values* | Give the bored a nice color |
Weapon Bypass | `{'Weapon1, Weapon2'}` | Allow certain weapons to be used inside the zone. |
Coords | `{vec3(x, y, z), vec3(x, y, z)}` or `vec3(x, y, z),` | Depening on zone type this will be the middle on a Sphere and the corners on a Polyzone. | 
Range | number | Only used in Sphere zones. |


## This is the zones config.lua file
```lua
Zones = {}

Zones.Prison = {
    ['Type'] = 'PolyZone',
    ['Height'] = false,
    ['BorderColor'] = {0, 255, 0},
    ['WeaponBypass'] = {
        GetHashKey("WEAPON_STUNGUN"),
        GetHashKey("WEAPON_SNOWBALL"),
        GetHashKey("WEAPON_PISTOL")
    },
    ['Coords'] = {
        vec3(1818.45, 2611.60, 45.67),
        vec3(1809.37, 2611.65, 45.67),
        vec3(1809.40, 2620.69, 45.67),
        vec3(1817.80, 2642.32, 45.67),
        vec3(1834.40, 2688.87, 45.67),
        vec3(1829.39, 2703.25, 45.67),
        vec3(1776.49, 2746.40, 45.67),
        vec3(1761.95, 2751.73, 45.67),
        vec3(1662.50, 2748.09, 45.67),
        vec3(1648.50, 2740.81, 45.67),
        vec3(1585.35, 2679.40, 45.67),
        vec3(1576.11, 2666.74, 45.67),
        vec3(1548.48, 2591.62, 45.67),
        vec3(1547.82, 2576.09, 45.67),
        vec3(1551.37, 2483.35, 45.67),
        vec3(1559.03, 2469.66, 45.67),
        vec3(1652.85, 2410.46, 45.67),
        vec3(1668.09, 2408.40, 45.67),
        vec3(1748.59, 2420.63, 45.67),
        vec3(1762.12, 2427.29, 45.67),
        vec3(1808.14, 2474.48, 45.67),
        vec3(1812.84, 2488.88, 45.67),
        vec3(1805.69, 2535.65, 45.67),
        vec3(1807.59, 2568.37, 45.67),
        vec3(1808.22, 2592.08, 45.67),
        vec3(1818.65, 2592.08, 45.67)
    }
}

Zones.GasStation = {
    ['Type'] = 'Sphere',
    ['Height'] = 60,
    ['BorderColor'] = {0, 255, 0},
    ['WeaponBypass'] = {},
    ['Coords'] = vec3(2004.90, 3774.25, 32.40),
    ['Range'] = 20,
}
```