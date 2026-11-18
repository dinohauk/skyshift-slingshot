# Skyshift Slingshot

A one screen slingshot puzzle inspired by Angry Birds, built from original simple shapes.

## Run

Open `skyshift-slingshot.html` in a current browser. It has no external assets or libraries.

## Rules

- Start a round with **Start round**. Drag the red bird backward from the sling and release to launch it. Dragging farther gives the shot more speed; a short pull under 10 pixels does not use a shot.
- Each launch rotates gravity clockwise by 90 degrees: down, left, up, right, then down again. Gravity affects the bird, targets, and loose debris until each leaves the screen or slows down. The tower blocks stay in place until an impact breaks them.
- Knock all three green targets out of the play area or hit them hard enough to remove them. Blocks can be damaged by impacts and break into debris.
- You have five launches. Clearing all targets wins immediately; using all five without clearing them loses.
- Press **R** at any time to reset the round. After a win or loss, choose **Play again**.

## Controls and feedback

Pointer or mouse drag/release launches. The HUD shows surviving targets, launches used, and current gravity direction. The launch sling stretches to show the pull direction.

## Example strategy

When gravity points left, both the bird and targets drift left during the shot. After a block breaks, its debris also drifts left. A later launch rotates gravity up, changing the next flight and where targets move.

## Five checks to perform

1. Start round: click Start round; the overlay closes and one bird appears at the sling.
2. Controls: pull back and release; the shot count increases once and the bird moves forward.
3. Special rule: launch a second time; gravity direction advances one step clockwise in the HUD.
4. Ending: knock down all three targets for a win, or spend five launches for a loss.
5. Restart: click Play again or press R; targets, shots, gravity, and blocks return to their initial state.

## Presentation notes

- Creative choice: gravity rotates after each launch, so each shot changes its own flight path and the direction targets and broken debris move.
- Code to explain: `gravity=(gravity+1)%4` advances through the four gravity vectors after a launch; the physics step applies the selected vector to the bird, targets, and debris.
- Improvement made during review: the target counter now updates immediately when a target is knocked out or leaves the play area.
- Have a classmate try a fresh copy and note where they hesitate; this guide does not claim a classmate test has happened.


