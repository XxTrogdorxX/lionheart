# Lionheart Lifting

A strength-training tracker that plans your next workout for you. Built as a single-page web app for iPhone (Home Screen app), and a sister brand to Lionheart Leather.

**Live app:** https://xxtrogdorxx.github.io/lionheart
**Status:** beta. Features are added one step at a time.

## What it does

**Train**
- Log weight, reps and reps in reserve (RIR) for every set, with ramp-up sets and supersets.
- Each exercise shows a short, encouraging line explaining why you got today's weight and reps. Tap it for the numbers behind the choice.
- Timed holds (like planks) and cardio (run, walk, hike, bike, row, swim, stairs) are tracked alongside lifts. Cardio logs distance or floors plus minutes, and shows pace or speed.

**Progression**
- Choose how weights change, for the whole plan or per exercise:
  - **Auto-adjust** (default): next week's weight comes from how your sets went.
  - **Linear**: add one step each week you hit all your reps.
  - **Double progression**: work within a rep range, then add weight.
  - **Percent of 1RM**: weights set from a max you enter.
  - **Fixed weight**: stays until you change it.
- Missed weeks, plateaus and tough weeks are handled automatically.

**Advanced plans**
- Deload weeks, 1-rep-max test weeks and rep waves, set on a simple week grid.
- Max tests offer to update your training weights afterward.

**Getting started**
- Build a plan from scratch (Basic or Advanced), pick a pre-built plan, reuse a past plan, or restore from a backup.
- A library of about 150 exercises, plus your own custom exercises.

**History**
- Records and progress graphs for every movement, a summary after each workout, and a list of past plans you can reuse.

**Your data**
- Works offline and saves on your phone first. Sign in with email and password to sync to your account.
- Export a backup file or a spreadsheet-friendly CSV of your workout log at any time.

## Using it on iPhone

1. Open the live app link in Safari.
2. Tap Share, then **Add to Home Screen**.
3. Open it from the Home Screen like any other app.

Before you update the app or switch phones, save a backup from **Profile → Settings → Backup**.

## How it's built

- One file, `index.html`: plain HTML, CSS and JavaScript with no framework and no build step.
- Hosted on GitHub Pages.
- Data is stored locally first, then synced to Supabase (email and password accounts, one saved state per user, with automatic snapshots).

### Files in this repo

| File | Purpose |
|---|---|
| `index.html` | The whole app |
| `supabase-setup.sql` | Creates the tables, security rules and snapshot trigger in Supabase |
| `.github/workflows/keepalive.yml` | Pings Supabase twice a week so the free project stays active |

### Setting up your own copy

1. Create a free [Supabase](https://supabase.com) project and run `supabase-setup.sql` in the SQL editor.
2. Put your project URL and public (anon) key into the `SB` setting near the top of the script in `index.html`. Never use the service key.
3. Turn on GitHub Pages for the repo (Settings → Pages, deploy from the main branch).
4. For the keep-alive workflow, add your Supabase URL and anon key as repository secrets, and re-enable the workflow if GitHub pauses it after a long quiet period.

### Updating the app

1. Save a backup in the app first.
2. Upload the new `index.html` (Add file → Upload files) and commit.
3. Reopen the app and check that **Settings → Backup** shows the new version number.

## Roadmap

Next, real-world feedback from individual lifters. After that, in rough order: program sharing, trainer and client pairing, and a marketplace for plans.

## Privacy

Your training data belongs to you. Never commit personal backup files to this repository, because it is public.
