# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the Games

Open any HTML file directly in a browser — no build step, server, or dependencies required:

```bash
open shooter.html
open tictactoe.html
```

## Project Structure

Each game is a **single self-contained HTML file** with inline CSS and JavaScript. This is the deliberate architecture of the project — do not split files into separate JS/CSS assets.

## Code Conventions

### shooter.html
- **800×600 canvas**, centered on a dark page, all rendering via `ctx.fillRect` pixel-art pixel maps (no external images)
- **Game loop**: `requestAnimationFrame` with delta-time capped at 50ms
- **State machine**: `MENU → PLAYING → LEVEL_COMPLETE → PLAYING → GAME_OVER`
- **Sprites**: defined as 2D color arrays, rendered by `drawSprite(pixelMap, cx, cy, scale, flipX, angle)`
- **Collision**: circle-circle via `Math.hypot`
- **Persistence**: hi-score stored in `localStorage` under key `topdown_hiscore`
- Input: arrow keys / WASD move, mouse aims, left click shoots, keys `1`/`2`/`3` switch guns

### tictactoe.html
- Pure DOM manipulation, no canvas
- Session-only score tracking (no localStorage)

## Git & GitHub

- Remote: `https://github.com/404atl/ClaudeCodeTest`
- Always commit with descriptive messages and push after every meaningful change
- Stage specific files by name — never `git add -A`
