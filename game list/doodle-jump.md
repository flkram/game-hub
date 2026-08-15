# Doodle Jump

## Summary

A vertical endless climber. The doodler bounces automatically off every platform
it lands on, so the only thing you control is horizontal movement. Line yourself
up with the next platform above, and the screen scrolls down to follow you as you
climb. Miss, fall off the bottom of the screen, and the run is over.

## How to Play

- **Left Arrow / A** — move left
- **Right Arrow / D** — move right
- **Space** — restart after a game over

The doodler wraps around the screen edges: exit on the right and you reappear on
the left, which is often the fastest route to a platform.

## Objective

Climb as high as you can. Your score is the height reached, and it only counts
when you beat your previous maximum, so hovering around the same platforms does
not inflate it. Like Flappy Bird, there is no ending — only a personal best.

## Notes

- Canvas is 360 x 576, the doodler is 46 x 46 and starts near the bottom.
- Gravity is `0.4` per frame; landing on a platform resets vertical velocity to
  `-8` for the bounce.
- Once the doodler rises past the top quarter of the screen, the platforms slide
  down instead of the doodler moving up — that scrolling is what creates the
  illusion of endless height.
- Platforms that go off the bottom are recycled to the top with a new random x
  position, so the world is generated continuously rather than pre-built.

## Implementation

`front_end/src/components/doodlejump.jsx`, a React component wrapping a canvas
loop, with assets and styling in `front_end/src/components/styles/`. A standalone
non-React copy also lives at `front_end/build/docs/doodlejump.js`.
