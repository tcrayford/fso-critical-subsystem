# fso-critical-subsystem

This is a lua script for Freespace 2 Open that adds a HUD Gauge for "critical subsystems".
The player can press (by default) the `d` key to select the next critical subsystem.

You define critical subsystems by using the `lua-add-critical-subsystem` sexp from FRED.

The HUD gauge hides itself if there are no more critical subsystems left.

This script hasn't been tested and likely won't work for multiplayer missions.

# Getting Started

Add the two files in `data/tables` to your mod.

You need to configure the HUD gauges used at the top of the script.
By default they're only compatible with blue planet complete (tested as of version 1.0.5).

```
    self.HudGaugeTitle = "BPLowerRightMFD"
    self.HudGauges = { "BPLowerRightMFDA", "BPLowerRightMFDB", "BPLowerRightMFDC", "BPLowerRightMFDD", "BPLowerRightMFDE", "BPLowerRightMFDF", "BPLowerRightMFDG", "BPLowerRightMFDH" }
```

The first of these is a "title" hud element which displays `MONITORING`

The second piece of configuration is a table that lists out a hud element which displays a line of the monitored subsystems.

You can't display more critical subsystems than the length of this table.

### SEXPs

`lua-add-critical-subsystem`

Usage: `( lua-add-critical-subsystem "GTD Bastion" "Engines" )`

Adds a critical subsystem to the list.
This doesn't target the subsystem in question.

`lua-next-critical-subsystem`

Targets the next critical subsystem.

`lua-remove-critical-subsystem`

Usage: `( lua-remove-critical-subsystem "GTD Bastion" "Engines" )`

Removes a critical subsystem to the list.
