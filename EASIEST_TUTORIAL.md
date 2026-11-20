# Frame Macro — Easiest Tutorial (3 Steps)

## Step 1: Fix Your GitHub Repo (2 minutes)

Your repo has the `build.yml` file in the WRONG place. GitHub needs it at `.github/workflows/build.yml`.

**The fix:**

1. Go to your repo: `https://github.com/sviatsv-max/asdasdasd`
2. Click on the file `build.yml` (it's at the root right now)
3. Click the **pencil icon** ✏️ (Edit) in the top-right corner
4. At the top where it says the file path `asdasdasd / build.yml`, click the folder icon or the path area
5. Click **"Move to a new path"** or **"Rename"**
6. Type: `.github/workflows/build.yml`
7. Click **Commit changes** (green button at the bottom)

**Done!** GitHub will automatically start building within 1-2 minutes.

---

## Step 2: Download Your Mod (wait 5-10 minutes)

1. Go to the **Actions** tab at the top of your repo
2. You should see a build running — wait for the **Windows** job to show a green checkmark ✓
3. Click on the build run name
4. Scroll down to **Artifacts** at the bottom of the page
5. Download `asdasdasd-win64` (or whatever it's called)
6. Unzip it — you'll get a `.geode` file

---

## Step 3: Install in Geometry Dash

1. Make sure you have **Geode** installed (download from `geode-sdk.org`)
2. Launch Geometry Dash through Geode
3. Click the **Geode gear icon** on the main menu
4. Go to **Mods** → **Install from files**
5. Select your `.geode` file
6. Done! The mod is installed

---

## Using the Mod

| What | How |
|------|-----|
| **Record** | Press **F6** or pause → click **Rec** |
| **Replay** | Press **F7** or pause → click **Play** |
| **Stop** | Press **F8** or pause → click **Stop** |

That's it!
