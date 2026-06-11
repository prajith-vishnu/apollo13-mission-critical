# APOLLO 13: MISSION CRITICAL

A real-time Mission Control crisis simulator in a single HTML file. No frameworks, no build step, no audio files, no images — just one document and the Web Audio API.

**You are the Flight Director.** April 13, 1970, 55:52:00 Ground Elapsed Time. In about three minutes, oxygen tank 2 in the Service Module explodes, and the next 87 hours of three men's lives belong to you.

**[► Play it](https://YOURUSERNAME.github.io/apollo13-mission-critical/)** · works on desktop and mobile · sound on

---

## What this is

Not an astronaut game. The ground perspective is the harder, stranger job: solving problems you cannot touch, with numbers on a screen and a 1.4-second speed-of-light delay between you and the people you're keeping alive.

Four resource systems run simultaneously, in real time, on the real physics couplings:

| System | The real number | The catch |
|---|---|---|
| **POWER** | 2,181 ampere-hours in the LM descent batteries | At full draw the ship dies two days before Earth. You decide what goes dark. |
| **CO₂** | 15 mmHg impairs the crew, 30 kills them | The LM scrubber was rated for 2 men × 2 days. It's carrying 3 men × 4. The spare cartridges are the wrong *shape*. |
| **WATER** | 6 oz per man per day — the real ration | The tank doesn't mainly feed the crew. It feeds the **sublimator**: the LM cools its electronics by boiling water into space. Every amp you leave running drinks your water. |
| **TRAJECTORY** | Entry corridor −5.25° to −7.40°, hit from 240,000 miles | The ship drifts shallow continuously — the cooling system itself is a tiny rocket that never shuts off. |

Every crisis fires at its **real GET timestamp**: the explosion at 55:54:53, the free-return burn at 61:29:43, PC+2 at 79:27:38, the hand-flown MCC-5 at 105:18:28, "Farewell, Aquarius" at 141:30, splashdown at 142:54:41. Every decision shows you its costs up front, and after you choose, a historical footnote tells you what the real Mission Control did — and what it cost them.

The CO₂ scrubber fix ("the mailbox") is a five-step build using only items verifiably aboard the spacecraft. Wrong materials waste time while the cabin gauge climbs. The real solution — duct tape, flight-plan cardboard, an LCG stowage bag, a suit hose — is the solution here.

## Engineering notes

- **One file.** Game state, simulation, timeline, rendering, audio synth, save system: `index.html`.
- **Adaptive time compression.** The sim sprints up to ×3000 between milestones and crawls during decisions, so you're never idle more than ~30 seconds. All rates are per *mission*-hour, so compression changes pacing, never outcomes.
- **Procedural audio.** Master alarm (warbled square wave), Quindar beeps (2525 Hz, like the real ones), band-passed white-noise radio static, telemetry ticks — all synthesized at runtime with the Web Audio API. Zero assets.
- **Analog gauges** drawn on canvas per frame: zone arcs, tick marks, glowing needle. CRT scanlines, phosphor glow, and vignette in pure CSS.
- **localStorage saves** — close the tab mid-crisis and the console re-energizes where you left it, including any decision that was on the table.
- A headless test harness (DOM stubs + JavaScriptCore) drove the full mission through the historical playthrough and three failure paths before release.

## Sources

Mission data from NASA's [Apollo 13 mission details](https://www.nasa.gov/missions/apollo/apollo-13-mission-details/) and the Apollo 13 Mission Operations Report: battery capacity, water budget and ration, CO₂ thresholds, cabin temperature, burn times and magnitudes, crew weight loss, the 28.5 lbs of oxygen left in Aquarius at jettison, and the blackout that ran 87 seconds past prediction. The failure ending quotes William Safire's 1969 contingency address *In Event of Moon Disaster* — drafted for Apollo 11, kept ready for every mission after, never read aloud.

Built for [Hack Club Stardance](https://stardance.hackclub.com). MIT licensed — fly it, fork it, break it, fix it.

*"Let's solve the problem, but let's not make it any worse by guessing."* — Gene Kranz
