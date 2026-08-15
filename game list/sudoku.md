# Sudoku

## Summary

The classic number-placement puzzle. You are given a 9 x 9 grid, divided into
nine 3 x 3 boxes, partially filled with digits. Fill in every remaining cell so
that each row, each column, and each 3 x 3 box contains the digits 1 through 9
exactly once. A well-formed puzzle has exactly one solution and needs no
guessing — every digit can be deduced from the ones already placed.

## How to Play

- Click a cell to select it, then type a digit **1–9** to fill it
- The starting clues are fixed and cannot be overwritten

## Objective

Complete the grid without breaking any of the three constraints. Unlike the
arcade games in this collection, Sudoku has a definite end state: the puzzle is
either solved or it is not.

## Rules

1. **Row** — each of the nine rows contains 1–9 with no repeats
2. **Column** — each of the nine columns contains 1–9 with no repeats
3. **Box** — each of the nine 3 x 3 boxes contains 1–9 with no repeats

## Strategy

- **Scanning** — for one digit at a time, cross off the rows, columns, and boxes
  where it already appears; a box with only one remaining candidate cell is a
  free placement.
- **Naked single** — a cell where eight of the nine digits are already excluded
  by its row, column, and box.
- **Hidden single** — a digit that can only go in one cell of a unit, even if
  that cell has several candidates of its own.

## Status

Not yet implemented. `front_end/src/components/sudoku.jsx` is an empty file, but
the route and nav link are already wired up in `front_end/src/App.js`
(`/sudoku`), and `front_end/src/components/styles/sudoku.css` exists. The
component itself still needs to be written — note that importing an empty module
as a React element will fail at runtime until it exports a component.
