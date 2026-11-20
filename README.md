# Frame Macro

Geode mod for **Geometry Dash 2.2081** (Geode v5). Records your inputs, replays them tick-for-tick, and shows a
live **frame counter** plus a **click-gap histogram**: how many inputs came 1, 2, 3, 4, 5-6, 7-8, 9-12, 13-16 or
17+ frames after the previous one.

## Get the .geode (nothing to install)

GitHub builds it for you in the cloud, about 5 to 15 minutes:

1. On github.com: **New repository** (any name, public or private), then **uploading an existing file**.
2. Unzip this project and drag everything inside the `frame-macro` folder into the page, including the
   `.github` folder. Click **Commit changes**.
3. Open the repo's **Actions** tab and wait for the **Build** run to finish (the Windows job is the one most
   people need).
4. Open the finished run, scroll to **Artifacts**, download `frame-macro-Windows` (or macOS / Android64 /
   Android32), and unzip it to get `yourname.frame-macro.geode`.
5. In GD: Geode > Mods > *Install from file*, or drop the file in `geode/mods`. Restart the game.

If you use git and the GitHub CLI instead: `git init -b main && git add -A && git commit -m init`, then
`gh repo create frame-macro --public --source=. --push`, then `gh run watch` and `gh run download`.

If a job fails, open it and copy the red lines from the *Run CMake and build* step.

The build uses the Geode SDK version in `mod.json` (`"geode": "5.11.2"`), the last one for GD 2.2081. Leave
it alone; newer SDKs (v6) target 2.2091. Change `id` and `developer` in `mod.json` before sharing the mod.
To build on your own PC instead: install the Geode CLI, check out tag `v5.11.2` in your SDK folder, run
`geode sdk install-binaries`, then `geode build`.

## Use

- **Pause menu:** *Rec* restarts from the start and records. *Play* restarts and replays the saved macro for
  this level. *Stop* ends and saves a recording.
- **Keys** (change them in the mod's settings): F6 record, F7 replay, F8 stop.
- Finishing the level while recording saves automatically. One macro per level, in the mod's save folder
  under `macros/`. Stop / finish overwrites that level's previous macro. Quitting mid-recording discards it.
- While replaying, your own clicks are ignored. If the run dies, the replay restarts from the beginning.

Macro files are plain text (`framemacro 1`, then `frame button down isPlayer1` per line), so other tools can
generate them.

## Notes

- A "frame" is one physics tick at the default 240 TPS. An input on frame N is applied right before tick N.
  The overlay shows `Frame: N` (and `N / last-input-frame` while replaying).
- Practice mode: a respawn rewinds the recording to the checkpoint's frame. A button held across a checkpoint
  can desync. For exact macros, record in normal mode.
- Inputs are injected once per tick, like other bots. There are no input/frame fixes, so very tight
  sections can drift.
- Safe mode (default on) marks completions during a replay as test-mode so they are not saved or submitted.
  Don't submit botted runs anywhere.
- Gap counting: any two inputs by default; the *presses only* setting counts press-to-press.

## Test the logic

    g++ -std=c++20 -I src tests/test_macro.cpp -o test_macro && ./test_macro
