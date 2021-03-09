# ExtendedCrackShot
The extended weapon inherits the attributes from the Parent weapon

mygun.yml
```yml
weapon1:
    Item_Information:
        Item_Name: "&9WEAPON1"
        Item_Type: IRON_HOE
        Inventory_Control: gun
    Shooting:
        ...
    Ammo:
        ...
    Reload:
        ...
    Abilities:
        ...
named_weapon1:
    Item_Information:
        Item_Name: "&dW&aE&eA&9P&cN"
        Item_Type: IRON_HOE
        Inventory_Control: gun
    # ↓ same weapon1 ↓
    ...
yet_another_named_weapon1:
    Item_Information:
        Item_Name: "Wha"
    # ↓ same weapon1 ↓
    ...
```
If you create the similar weapon or the named weapon or something else, it is cost to change values and modules. 

And files increases, your "./weapons" directory gets dirty

Collect to 1 file?  You will be using "search command" your editor

So I created the "extend" module. 

## Modules

**You have to save extended weapon file under "./plugins/CrackShot/weapons/extended/"!**

```yml
Weapon_Title:
    extend: <**The CrackShot Weapon_Title** that you wanna extend>
    data:
        <CrackShot Modules to override>
```

### Example
Situation => I wanna create "AK-47 Special" same specs as "AK-47". But **Special** weapon, so it increases weapon damage and projectile speed.
```
Directory:
plugins/CrackShot/weapons/
↪ extended/
   ↪ ak-47-special.yml <<<<<- Here
↪ ak-47.yml
```
```yml
AK-47-Special:
    extend: AK-47
    data:
        Item_Information:
            Item_Name: "&eAK-47 &dSpecial"
        Shooting:
            Projectile_Speed: 100
            Projectile_Damage: 10
```

CrackShot modules list is [this link](https://github.com/Shampaggon/CrackShot/wiki/List-of-Modules)

## Apply your plugin

1. Copy and Paste this code
2. Create new instance to your JavaPlugin
3. Execute "/shot config reload" (refresh weapons)
4. Call loadWeapons()

**WARNING: If you call loadWeapons() using your timing(ex. player command), you have to execute "/shot config reload" before.**
