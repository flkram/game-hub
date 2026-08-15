# Flappy Bird

## Summary

A one-button side-scroller. You control a bird that is constantly pulled down by
gravity, and each tap gives it a short upward boost. Pipes scroll in from the
right with a gap in the middle; steer through the gap. Touching a pipe or the
ground ends the run.

## How to Play

- **Space / Arrow Up / X** — flap (a single upward impulse)
- Press any of the same keys after a crash to restart from the beginning

## Objective

Survive as long as possible. You score one point for every pipe pair you clear,
and there is no win condition — the game only ends when you crash, so the score
is the whole point.

## Notes

- Canvas is 360 x 640; the bird is drawn at 34 x 24 and starts at the left
  eighth of the screen, mid-height.
- Gravity is `0.4` per frame and a flap sets vertical velocity to `-6`, so the
  bird arcs rather than moving in straight lines.
- Pipes scroll left at 2 px per frame and a new pair spawns every 1.5 seconds,
  with the vertical position randomized and a fixed gap of one quarter of the
  board height.
- The score increments by 0.5 per pipe (top and bottom counted separately),
  which is why it lands on whole numbers per pipe pair.

## Implementation

Plain canvas game, not a React component:
`front_end/build/docs/flappybird.js` with `flappybird.html` / `flappybird.css`.
It runs on `requestAnimationFrame` for the draw loop and a `setInterval` for
pipe spawning.
