# Static Protocol

A cyberpunk interactive story, played entirely on your phone — and looping until you get it right.

You're a runner working a data heist. Five jobs come through your phone tonight — a rooftop extraction, a fixer's booth, a corp server room, a confrontation, and one final call on what to do with what you stole. Each one plays out inside a real app on your screen: a tracker pings an incoming threat, a messages thread waits on your reply, a hacking tool needs a pattern matched under pressure, a call comes in you can't ignore, a transmit screen waits on a destination.

Every choice triggers a live **SYNC** sequence — a short, tense minigame tuned to what's happening in the scene: reflex dodging for evading a drone scan, a timing bar for talking your way past a fixer, a memory pattern for a stealth hack, a quick-draw reaction duel for a street confrontation, and a mashed-up climax that throws all of it at you at once. Clean it and your choice plays out exactly as intended. Fumble it and the job gets forced sideways, whether you meant it to or not.

**The server room branches for real.** Whichever side you're leaning toward trusting after the fixer — Corp, the Street, or just yourself — changes which job you actually run next: a corp clearance you have to bluff your way through, the original stealth break-in with street intel backing you, or a solo job with nobody covering you if it goes wrong. Different scene, different choices, different SYNC mechanic — not just re-flavoured text.

**Five tracked stats**, not three: who you trust, how you get things done, how much heat you've drawn, your resolve (it drops every time a SYNC goes sideways, and burning out changes how the night ends even if you technically make it), and your notoriety (get famous enough and buying your silence costs a lot more). Recruiting the rogue AI only pays off later if you actually earned its trust first.

**It's a loop.** Every ending except one sends you back to try again — the game remembers, across sessions, how many times you've been through tonight. Only a flawless run, every single SYNC clean, breaks it for good.

## Playing it

Open `index.html` — no build step, no dependencies. The title screen is a full page of its own; New Game drops you into the phone, which fills the real screen edge to edge on mobile or renders as a device mockup on desktop, since the whole point is that you're holding someone's phone.

Controls: tap, or arrow keys / WASD / Space during a SYNC sequence.

## How it's built

Single self-contained HTML file — vanilla JS, no framework, no bundler. The state machine (branching nodes, tracked flags, five SYNC minigame engines, the ending resolver, loop persistence via localStorage) is fully decoupled from the presentation layer, which is why the whole "phone OS" shell — a separate title screen, home screen with a real app grid, live notifications routing you into the right app — could be rebuilt without touching the underlying game logic. Every SYNC mode, however different it looks, ultimately reports the same clean/partial/fail result back to one shared resolver, so new minigames and new story branches drop in without touching the ending logic at all.
