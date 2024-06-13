# Cursive

> [!IMPORTANT]
>
> **This addon requires you to have [SuperWoW](https://github.com/balakethelock/SuperWoW) installed.**
>
> It won't work without it. Really.

![image](https://github.com/pepopo978/Cursive/assets/149287158/801511af-29c7-4baf-b1ac-5e8c52f0f846)


Cursive combines ShaguScan unit scanning with curse tracking similar to DotTimer and the ability to automatically curse targets similar to Decursive.

### Recommended setup
Move the Cursive label to the desired position on the screen.  You can turn on 'Show Frame Background' in the settings to help with this.  Once you have it where you want it, turn off 'Show Frame Background' and turn on 'Allow clickthrough'
 so that it doesn't block your clicks when it's not displaying mobs.

## Commands
`/cursive` for commands, minimap icon to edit options.

### Curse
`/cursive curse <spellName:str>|<guid?:str>|<options?:str>`: Casts spell if not already on target/guid

EXAMPLE: `/cursive curse Corruption|target` will attempt to cast Corruption on your target if it's not already on them and they aren't cc'ed.

### Multicurse
`/cursive multicurse <spellName:str>|<priority?:str>|<options?:str>`: Picks target based on priority and casts spell if not already on target and they aren't cc'ed.  

EXAMPLE: `/cursive multicurse Corruption|HIGHEST_HP` will attempt to cast Corruption picking the target with the highest HP that doesn't already have it and will warn you if it does nothing.
## Priority Options
- HIGHEST_HP - Target highest HP enemy without a curse first.
- RAID_MARK  - Target largest raid mark enemy without a curse first.  Raid mark priority is as follows:
  - Skull = 8 (1st priority)
  - Cross = 7
  - Square = 6
  - Moon = 5
  - Triangle = 4
  - Circle = 3
  - Star = 2
  - Diamond = 1 (8th priority)
  - No mark = 0
- HIGHEST_HP_RAID_MARK - Target highest HP enemy with a raid (use raid mark priorities for identical hp), then highest HP enemy without a mark.


## Command Options
All commands can take the following options separated by commas:
- `warnings` : "Display text warnings when a curse fails to cast.",
- `resistsound` : "Play a sound when a curse is resisted.",
- `expiringsound` : "Play a sound when a curse is about to expire.",
- `allowooc` : "Allow out of combat targets to be multicursed.  Would only consider using this solo to avoid potentially griefing raids/dungeons by pulling unintended mobs.",
- `minhp=<number>` : "Minimum HP for a target to be considered.",
- `refreshtime=<number>` : "Time threshold below which to allow refreshing a curse.  Default is 0 seconds.",

EXAMPLE: `/cursive multicurse Corruption|HIGHEST_HP|warnings,resistsound,expiringsound,minhp=10000,refreshtime=2`

## Important info

All commands will prioritize targets within 28 yards of you first to have a better chance of being in range.

All commands will ignore targets with the following CCs on them:
- Sleep
- Entangling Roots
- Shackle Undead
- Polymorph
- Turn Undead
- Blind
- Sap
- Gouge
- Freezing Trap

Multicurse will only ever target enemies that are already in combat (except if you target a mob directly first) to prevent pulling things you didn't intend like marked patrols.
