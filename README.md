# What is this mod?

Did you ever have trouble searching the loot because enemies scattered around?
Ever wanted to keep track of the dead enemies to loot them later?
My friend, let me introduce to you the Loot Tracker!

# How it works?

When an NPC dies, it gets marked in the loot tracker quest. Once looted or explicitly requested to, the NPC gets unmarked.
Inspired by the dead enemy map markers in Witcher 3.

# Features

* Automatic activation after combat end (can be disabled)
* Automatic return to the interrupted quest
* Configurable delay before making the tracker active, for fast looters :)
*  Filters for different types of creatures, in case you don't want to track every dead mantis or dog :)

# Interaction

The quest is the primary part of the tracker. However, when the quest is selected as active, you can hit "Activate" button twice to bring up a context menu that lets you remove one or all targets.
NPCs get automatically unmarked once their inventory is open.

# Configuration

There's a config file `Data/Config/LootTracker <character name>.ini`.

`LootTracker Courier.ini` is the default config and works for character named "Courier". Make a copy of this config and rename it to match your character name.

# Requirements

The holy trinity: [xNVSE](https://www.nexusmods.com/newvegas/mods/67883), [JohnyGuitar](https://www.nexusmods.com/newvegas/mods/66927) and [JIP LN](https://www.nexusmods.com/newvegas/mods/58277).

# Recommendations

While not mandatory, it's extremely advised to be used together with JVO - Just Visual Objectives by carxt - yvileapsis

# Performance

This mod is designed to be as optimized as possible. From technical perspective, it doesn't use main loops/active waiting/polling/etc, and most of the code is event handlers that are set only when needed (e.g. input handlers are set only if the quest has targets etc).
The bottom line is, this mod should have absolutely no measurable impact on the performance/FPS.
You can test it with 10k dead NPCs and let me know later how it goes.

# Known issues

## Work in progress

While I consider this mod ready for public judgement and booing, there still might be things that I didn't consider (read miss). This is my first New Vegas mod ever. Please report them.

## JVO

JVO might cause unexpected behavior when using "In sight" action in the unmark prompt: sometimes the target that has JVO marker further from the crosshair gets removed. This happens because as per JVO code, for bipeds (humanoids) the on-screen marker is placed over the head, while from the generalized game logic point of view body's position anchor ("center") is around lower back. You can see the difference between the vanilla in-game compass and the JVO marker position. Basically, the biped that has lower back closer to the crosshair gets removed.
This may cause inconveniences only if enemy bodies are very close to each other, for example one on top of another, otherwise "In sight" will not cause any confusion