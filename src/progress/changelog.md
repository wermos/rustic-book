# Changelog

## ? ??, 2021 - Rustic Alpha 3.0.0 (work in progress)

- New features:
  - Killer Heuristic
  - History Heuristic
- Changes:
  - Switch versioning scheme to SemVer. Versions are going to be in the
    form "a.b.c" from now on, with the following meaning:
    - Increment **a**: A new strength-gaining feature was added.
    - Increment **b**: A bug was fixed that gained strength.
    - Increment **c**: A feature was added or a bug was fixed that did not
      gain stregnth. It is not necessary to test this version for a rating
      change.
- Misc:
  - A build script was added, so all versions of Rustic for a particular
    operating system can be compiled at once, without having to manually
    set compilation flags. Of course, the basic "cargo build --release"
    will also still work, but the resulting version of the engine will not
    be optimized for the specific hardware.

## March 17, 2021 - Rustic Alpha 2

- New Features:
  - Transposition table for search and perft.
  - Ordering on transposition table move.
  - Set TT size through --hash option or UCI parameter.
- Improvement:
  - Move check extension higher up in the search routine, to prevent
    quiescence search while in check.
- Changes:
  - seldepth: report max ply reached during the search, instead of
    selective depth at last completed iteration.
  - Count all nodes visited, instead of only nodes which generated moves.
  - Change random number generator from SmallRng to ChaChaRng for
    reproducible behavior between platforms/OS's/architectures/versions.
- Cleanup
  - Change Root PV handling to remove redundant code.
  - Miscellaneous small renames, refactors, and cleanups.
  - Add rand_chacha and remove SmallRng number generators.
  - Update Rand library to 0.8.3.

## March 15, 2021 - Rustic Alpha 1.1

This is a bugfix release. Alpha 1 lost all of its games on time forfeit
when playing in MoveTime mode (for example, when playing seconds/move).

Bugfixes:
- Do not exceed alotted time in MoveTime mode.

## January 24, 2021 - Rustic Alpha 1

This is the initial release.
Below are the features included in this version.
[CCRL Blitz rating: +/- 1677 Elo](https://www.computerchess.org.uk/ccrl/404/cgi/engine_details.cgi?print=Details&each_game=1&eng=Rustic%20Alpha%201%2064-bit#Rustic_Alpha_1_64-bit)

- Engine:
  - Bitboard board representation
  - Magic bitboard move generator
  - UCI-protocol
- Search
  - Alpha/Beta search
  - Quiescence search
  - MVV-LVA move ordering
  - Check extension
- Evaluation
  - Material counting
  - Piece-Square Tables