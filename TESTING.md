# Test record

The game was cloned from the public GitHub repo into a fresh folder. The clone contains `index.html` and `README.md`. The JavaScript passes `node --check`.

The interaction checks below ran against the game's actual JavaScript with simulated canvas and pointer events. They check game logic and HUD updates, but they are not a substitute for opening the game in a browser.

| Check | Action | Expected result | Result |
|---|---|---|---|
| Start | Click **Start round** | Intro closes; HUD shows 3 targets, 0/5 shots, gravity down | Pass |
| Invalid pull | Pull the bird fewer than 10 pixels and release | Shot count and gravity stay unchanged | Pass |
| Controls and new rule | Drag from the sling back about 78 pixels and release | Bird launches; shot count increases once; gravity turns down → left | Pass |
| Win ending | Make two shallow down-right launches, allowing gravity to move the targets | Win message appears when all targets leave play | Pass in simulation |
| Lose ending | Use five launches without clearing all targets | Loss message appears at 5/5 | Pass |
| Restart | Press **R** after an ending | Targets return to 3, shots to 0/5, gravity down, ready overlay appears | Pass |

## Fix found during testing

The first physics settings made shots too slow to reach the tower, and shots bounced away from supports. The launch speed and gravity were tuned, and strong impacts now break a support and continue through it. The loss and restart flow, invalid short pull, gravity advance, and a win sequence passed the simulated interaction checks after the fix.

## Still needs a person

GitHub Pages is not enabled, so the repo URL is not currently a playable web page. Download the repo and open `index.html` in a browser to do the visual play-through. A classmate should then try it without coaching; write down where they get stuck and decide whether another usability fix is needed. No classmate feedback is claimed here.

