# APOLLO 13: MISSION CRITICAL

**A real-time Mission Control crisis simulator built on real NASA data.**

April 13, 1970, 55:54:53 Ground Elapsed Time. Oxygen tank 2 in the Service Module explodes 200,000 miles from Earth. You are not an astronaut — you are the **Flight Director** in Mission Operations Control Room 2, Houston. Three men are alive at the other end of a radio loop, and for the next 87 hours every watt, every ounce of water, every breath of air, and every tenth of a degree of trajectory belongs to you.

This is not a story *inspired by* Apollo 13. It is the mission's own arithmetic, running live, with you in the chair.

**[► PLAY THE LIVE DEMO](https://prajith-vishnu.github.io/apollo13-mission-critical)** — sound on, desktop or mobile, ~20 minutes, saves automatically.

---

## Real NASA Data

Every number that governs this simulation is sourced from the historical record:

| Figure | Value in game | Source |
|---|---|---|
| LM descent battery capacity | **2,181 ampere-hours** | NASA Apollo 13 Mission Report |
| CO₂ danger thresholds | **15 mmHg** impairment, **~30 mmHg** fatal | NASA life support documentation |
| Crew water ration | **6 oz per person per day** (1/5 normal intake) | Space Center Houston historical record |
| Oxygen tank 2 explosion | **GET 55:54:53** | NASA detailed chronology (NSSDC) |
| Crew weight loss | **31.5 lbs combined** (Lovell alone lost 14) | NASA post-mission report |
| Cabin temperature | dropped below **40°F** (to 38°F) during power conservation | NASA Apollo 13 mission details |
| LM design rating | **2 crew × 2 days** — it carried 3 crew for nearly 4 | NASA Apollo 13 mission details |
| Oxygen remaining at LM jettison | **28.5 lbs** | NASA Apollo 13 mission details |
| Splashdown | **GET 142:54:41** | NASA detailed chronology |

The crisis events fire at their real GET timestamps: the free-return burn at 61:29:43, PC+2 at 79:27:38, the hand-flown MCC-5 at 105:18:28, "Farewell, Aquarius" at 141:30, the re-entry blackout that ran 87 seconds past prediction. The CO₂ "mailbox" puzzle uses the actual parts list — duct tape, flight-plan cardboard, an LCG stowage bag, a suit hose. The in-game **ABOUT** panel cites all of this from inside the console.

## How To Play

You manage four coupled resource systems simultaneously, in real time:

1. **POWER** — 2,181 Ah in the LM batteries. Every system on the bus draws real amps. At full draw the ship dies two days before Earth; you decide what goes dark, switch by switch.
2. **CO₂** — rises as three men breathe through scrubbers rated for two. At 15 mmHg the crew is impaired; at 30 they die. When the cartridges saturate, you build the adapter yourself, step by step, from what's actually aboard.
3. **WATER** — the cruel one: the tank mostly feeds the *sublimator*, which cools the electronics by boiling water into space. Every amp you leave running drinks your water. You also set the crew's ration — and pay for it in their performance.
4. **TRAJECTORY** — the entry corridor is 2.15° wide, hit from 240,000 miles away, and the ship drifts shallow continuously. You authorize burns at fixed windows; their accuracy depends on the condition of the crew you've been keeping cold and thirsty.

Crisis decisions arrive on a countdown (45 seconds; 20 when the border is red). Every option shows a uniform **COST / GAIN / RISK** readout. Choose with the mouse or keys **1–4** — controllers didn't use mice. After you commit, the **HISTORICAL RECORD** reveals what Mission Control actually did in April 1970. Four endings, graded against history, with a full debrief table comparing your numbers to the real mission's.

## Why I Built This

I've always been fascinated by NASA and by real mission data — not the movie version of events, but the actual numbers people had to work with. What grabbed me about Apollo 13 is that it wasn't saved by heroics in the spacecraft; it was saved by arithmetic on the ground, done fast, under pressure, by people who couldn't touch the machine they were fixing. I wanted to build something that taught the real story through gameplay rather than reading — where you don't just learn *that* they rationed water to 6 oz a day, you feel *why*, because the sublimator is drinking your tank and the burn windows are coming. Every number in this game is sourced from real NASA documentation, and the most surprising mechanics (the power–water coupling, the debris field faking the stars, powering up telemetry *last*) are the parts I didn't invent.

## Screenshots

*(coming soon)*

## Tech Stack

Vanilla HTML, CSS, and JavaScript. No frameworks, no build step, no assets — all audio (master alarm, Quindar beeps, radio static, telemetry) is synthesized at runtime with the **Web Audio API**. Analog gauges drawn on canvas. CRT scanlines and phosphor glow in pure CSS. Adaptive time compression keeps something happening every ~30 seconds without ever changing outcomes. Game state persists in localStorage — close the tab mid-crisis and the console re-energizes where you left it.

## Run Locally

```
git clone https://github.com/prajith-vishnu/apollo13-mission-critical.git
```

Then open `index.html` in any browser. That's the whole install. (`index.html` is the mission briefing; **[ ASSUME CONSOLE ]** launches the simulator in `game.html`.)

## License

[MIT](LICENSE) — fly it, fork it, break it, fix it.

## Acknowledgements

- NASA historical records and the [Apollo 13 mission details](https://www.nasa.gov/missions/apollo/apollo-13-mission-details/)
- NASA Apollo 13 Mission Report
- Space Center Houston
- NSSDC Apollo 13 Chronology
- The flight controllers of MOCR 2, April 1970 — *"Let's solve the problem, but let's not make it any worse by guessing."*

Built for [Hack Club Stardance](https://stardance.hackclub.com). See [AI_USAGE.md](AI_USAGE.md) for the AI assistance disclosure.
