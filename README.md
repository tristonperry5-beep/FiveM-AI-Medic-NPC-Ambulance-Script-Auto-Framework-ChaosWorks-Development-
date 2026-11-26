# Teedargyy × Chaos Works

**Chaos Works Development**

```
  TEES-NPCMEDIC
  ---------------------------------
  SIGNAL     live pulse
  LOCKOUT    30s, then press E
  UNIT       ambulance inbound
  TREAT      25s CPR, then he leaves
```

A downed player watches the monitor. The lockout ends. They press E. A medic drives in, talks them through every step of CPR, gets back in the van, and disappears down the road.

## Drop-in

1. Place `tees-npcmedic` in your `resources` folder.
2. Start it after your core and your ambulance resource.

```
ensure tees-npcmedic
```

3. Restart. The console prints `field medic ready` and the framework it found.

`config.lua` stays open after Tebex escrow. Price, timers, and his lines all live there.

## Frameworks

`Config.Framework` is `auto`. Qbox is chosen before QBCore, because Qbox also provides `qb-core`.

| Core | Death is cleared by |
| --- | --- |
| Qbox | `qbx_medical` |
| QBCore | `qb-ambulancejob` |
| ESX | `esx_death`, or `esx_ambulancejob` if that is what you run |

## On scene

| | |
| --- | --- |
| Monitor | Live pulse, lockout, then the E prompt |
| Arrival | Drives in. After 25 seconds with no path, he and the van are placed beside you |
| CPR | 25 seconds. Speech bubble above his head and on the monitor |
| Exit | He gets in, drives off, then both despawn |
| Voice | Muted while dead or bleeding out |
| Fee | $100,000 from cash, then bank. Refunded if the revive fails |

Every downed player gets their own medic. One call does not block another.
