# Senet

[Versione italiana](README.md)

[![Version](https://img.shields.io/badge/version-1.1-blue)](#versions)
[![License: AGPL v3](https://img.shields.io/badge/license-AGPL--3.0-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![GitHub Pages](https://img.shields.io/badge/demo-GitHub%20Pages-222?logo=github)](#publishing-on-github-pages)
[![HTML5](https://img.shields.io/badge/HTML5-single%20file-E34F26?logo=html5&logoColor=white)](index.html)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES2020-F7DF1E?logo=javascript&logoColor=black)](index.html)
[![Three.js](https://img.shields.io/badge/Three.js-r128-000?logo=threedotjs&logoColor=white)](https://threejs.org/)
[![Language](https://img.shields.io/badge/language-Italian%20%7C%20English-green)](#)

A browser-based version of Senet, the ancient Egyptian board game. It consists of a single HTML page, with no build process or installation required. It shares its architecture with the [Royal Game of Ur](https://github.com/): a game engine separate from the user interface, 3D dice, animations, synthesized audio, historical background, and illustrated rules.

[Play it here](https://tagtthespellcaster.github.io/Senet/)

## Features

- **Two separate rule sets**, kept distinct because the sources do not fully agree:
  - *CEMEA*: four casting sticks, seven pieces per player;
  - *Kendall and Bell*: six-sided die marked with an X, five pieces per player, and pieces leaving square 30 at the beginning of a turn.
- **Pieces per player**: 5 or 7, independently of the selected rule set.
- **Opponent**: computer or two players sharing the same screen.
- **Game board**: blue faience with glyphs representing the special squares (ankh, water, III, Eye of Horus, solar disk), plus an afterlife tray for each player.
- **3D casting sticks and die** (Three.js). A 2D version is used when WebGL or Three.js is unavailable.
- **Step-by-step animations**, including position swaps during attacks and returns to square 15 after landing on the unlucky square. Animations are disabled when the operating system's reduced-motion setting is enabled.
- **Synthesized audio** using Web Audio: sound effects (enabled by default) and an Egyptian-inspired soundtrack (disabled by default), featuring a double harmonic scale, harp, flute, darbuka, and sistrum. The settings are saved in the browser.
- **Illustrated rules**: an animated tutorial for each rule set (19 and 20 moves).
- **History**: a cinematic-style title sequence based on the Wikipedia entry for "Senet".
- **Italian and English**: an IT/EN language selector in the header. The selected language is saved in the browser; if no preference is stored, the browser's language is used. The language can also be changed during a game, in the illustrated rules, and in the historical section (entries already recorded in the game log remain in their original language).
- Automatic light and dark themes, with a layout adapted to small screens.

## Rules at a Glance

The path consists of 30 squares arranged in three rows of 10, followed in a serpentine pattern. Players move exactly the number of squares indicated by their roll. With a roll of 1, 4, or 6 (casting sticks), or 1, 4, or 5 (die), they roll again; with 2 or 3, their turn ends. Landing on an opponent's piece swaps their positions. Two adjacent pieces form a block that cannot be attacked but can be jumped over; three adjacent pieces form an impassable block. Squares 15, 26, 28, 29, and 30 protect pieces; square 27 sends a piece back to square 15. Pieces leave the board from square 28 with a roll of 3, square 29 with a roll of 2, and square 30 with a roll of 1. The first player to get all their pieces off the board wins.

For the full details, see the "Rules, Interpretations and Sources" panel in the game.

## Interpretations and Limitations

The original rules are unknown, and the available sources leave some points unresolved. The following interpretations have been adopted:

- **Skipping the unlucky square**: the instruction "with a roll of 1, you can skip the unlucky square" is interpreted as moving directly from square 26 to square 28.
- **Unlucky square when square 15 is occupied**: if the piece on square 27 belongs to the same player, it moves to the first available square; if it belongs to the opponent, it remains on square 27 and the player is blocked until they roll a 4.
- **Leaving the board with a 4**: a blocked piece leaves the board and counts as a piece safely removed, as specified by the CEMEA rules.
- **Backward movement** (zero-point roll): only onto unoccupied squares. Pieces on squares 28–30 can leave their square only with the exact required roll.
- **Not implemented**: the ancient rule according to which both players completed the game.
- The date "5th–4th millennium BC", given in the source text in connection with the use of the game by pharaohs, is not included in the historical section because it has not been verified.

The game engine has been tested through complete game simulations (8 combinations of rules, number of pieces, and player types) and 33 scenarios covering attacks, blocks, special squares, and pieces leaving the board.

## Getting Started

Open `index.html` in a modern browser. The page loads Three.js r128 (`cdnjs.cloudflare.com`) and Google Fonts from CDNs, if available. If they cannot be reached, 2D dice and system fonts are used instead.

## Publishing on GitHub Pages

1. Copy `index.html` to the root of the repository.
2. In *Settings → Pages*, select the branch (for example, `main`) and the `/ (root)` folder.
3. The page will be available at `https://<username>.github.io/<repository>/`.

## Versions

| Version | Changes |
|---|---|
| 1.1 | Italian and English interface with language selector. |
| 1.0 | Complete game with CEMEA and Kendall and Bell rules, animations, audio, historical background, and illustrated rules. |

## Sources

- "Senet", Wikipedia, which includes the rules of the CEMEA research group on the game (the *CEMEA* rule set).
- Rules by Timothy Kendall and R.C. Bell, in the UniNerd adaptation (PDF) (the *Kendall and Bell* rule set).

## License

Copyright © 2026 Alessandro Valli.

This program is free software: you can redistribute it and modify it under the terms of the GNU Affero General Public License, version 3 or later. If you provide a modified version as a network service, you must make its source code available to users. The program is distributed without any warranty. Full text: [LICENSE](LICENSE) and <https://www.gnu.org/licenses/agpl-3.0.html>.

Three.js is distributed under the MIT License.
