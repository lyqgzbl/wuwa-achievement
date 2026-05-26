# wuwa-achievement

Offline Wuthering Waves achievement tracker generator.

This repository reads user-provided SQLite database files and generates a static
HTML achievement checklist page. It does not include Pak extraction, key
acquisition, process injection, runtime hooks, local game path discovery, or game
automation.

## Required Inputs

Prepare these files yourself before running the generator:

- Achievement config database: `db_achievement.db`
- Simplified Chinese text databases: one or more `lang_multi_text*.db`

The generator only reads the paths passed through CLI arguments.

## Generate HTML

Run from the repository root:

```bash
python -m Tools \
  --config-db /path/to/db_achievement.db \
  --multitext-db /path/to/lang_multi_text.db \
  --multitext-db /path/to/lang_multi_text_1sthalf.db \
  --out docs/achievement_tracker_zh.html
```

The generated page is a self-contained static HTML file:

```text
docs/achievement_tracker_zh.html
```

## Arguments

- `--config-db`: path to `db_achievement.db`
- `--multitext-db`: path to `lang_multi_text*.db`; can be passed multiple times
- `--out`: output HTML path; defaults to `out/achievement_tracker_zh.html`
- `--root`: output root; defaults to the current directory

## Public Deployment

The GitHub workflow for this repository should deploy only static files from
`docs/`. It should not run extraction, key acquisition, runtime automation, or DB
generation jobs.
