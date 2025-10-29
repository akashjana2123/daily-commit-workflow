# 🤖 Daily Contribution Keeper

This project is not a typical application, but rather a configuration that utilizes **GitHub Actions** to perform a **daily, automated commit** to this repository.

The primary purpose is to maintain a consistent commit history, which can be useful for keeping a repository "active" or simply for ensuring a daily contribution to a profile's activity graph.

---

## ✨ Features

* **Daily Schedule:** The workflow is set to run automatically every day at a specific time (`04:15 UTC`).
* **Log File Update:** It appends a timestamped entry to a file named `daily-log.txt`.
* **Dedicated Commit:** The workflow performs a `git commit` and `git push` with a dedicated bot user (`github-actions[bot]`).
* **Manual Trigger:** Includes a `workflow_dispatch` trigger, allowing the workflow to be run manually from the GitHub Actions tab.

---

## ⚙️ How It Works (The Workflow)

The automation is defined in the file **`.github/workflows/blank.yaml`**.

### 1. The Trigger (`on:`)

The workflow runs based on a cron schedule:

```yaml
on:
  schedule:
    - cron: '15 4 * * *' # Runs daily at 04:15 AM UTC
  workflow_dispatch: # Allows manual triggering
