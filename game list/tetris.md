# Tetris

## Summary

The classic falling-block puzzle. Tetrominoes drop one at a time into a 10-wide
playfield; you slide and rotate each one on the way down and lock it into place
at the bottom. Fill a horizontal row completely and it clears, dropping
everything above it down a line. Let the stack reach the top and the game ends.

## How to Play

- **Left / Right Arrow** — move the falling piece sideways
- **Up Arrow** — rotate the piece 90°
- **Down Arrow** — soft drop (move down one row immediately)

Moves that would push a piece into a wall or an existing block are rejected
rather than clipped, so a rotation next to the wall may simply not happen.

## Objective

Clear as many lines as you can before the stack reaches the top of the
playfield. As with the other arcade games here, there is no final level — it runs
until you top out.

## Notes

- The playfield is 22 rows by 10 columns, drawn on a 32 px grid. The top two
  rows sit above the visible area and act as spawn space.
- All seven standard tetrominoes are implemented: **I, J, L, O, S, T, Z**.
- Pieces come from a shuffled bag of all seven rather than independent random
  draws, so you never go a long stretch without the piece you need.
- Rotation is a matrix transpose plus a row reverse — a generic 90° turn that
  works for every shape without a per-piece lookup table.
- Pieces spawn centered horizontally; the I-piece starts one row higher than the
  rest because of its flatter matrix.

## Implementation

`front_end/src/components/tetris.jsx` — a React component rendering to a canvas
via `useRef`, with the playfield and current piece in `useState` and the drop
loop driven by `requestAnimationFrame`.
