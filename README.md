# Static Protocol

A cyberpunk interactive story, played entirely on your phone.

You're a runner working a data heist. Five jobs come through your phone tonight — a rooftop extraction, a fixer's booth, a corp server room, a confrontation, and one final call on what to do with what you stole. Each one plays out inside a real app on your screen: a tracker pings an incoming threat, a messages thread waits on your reply, a hacking tool needs a pattern matched under pressure, a call comes in you can't ignore, a transmit screen waits on a destination.

Every choice triggers a live **SYNC** sequence — a short run of timed glyph prompts. Clean it and your choice plays out exactly as intended. Fumble it and the job gets forced sideways, whether you meant it to or not. Two runs with identical choices can still end differently, depending on how steady your hands were.

**Ten endings**, resolved from three tracked flags (who you trusted, how you got things done, how much heat you drew) plus your final choice and how well you synced it: Ghost, Martyr, Revolution Spark, Corporate Puppet, Merged, Hunted Down, Betrayed, Vigilante, Walk Away, Reconditioned.

## Playing it

Open `index.html` — no build step, no dependencies. On a phone it fills the real screen edge to edge; on a desktop browser it renders as a device mockup, since the whole point is that you're holding someone's phone.

Controls: tap, or arrow keys / WASD during a SYNC sequence.

## How it's built

Single self-contained HTML file — vanilla JS, no framework, no bundler. The state machine (five nodes, tracked flags, the SYNC minigame, the ending resolver) is fully decoupled from the presentation layer, which is why the whole "phone OS" shell — lock screen, home screen with a real app grid, live notifications routing you into the right app — could be rebuilt twice without touching the underlying game logic.
