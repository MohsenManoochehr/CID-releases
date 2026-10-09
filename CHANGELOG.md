# Changelog

All notable changes to CID. Download installers from the [releases page](https://github.com/MohsenManoochehr/CID-releases/releases).

## [1.2.0] - 2026-10-09

### Now on Linux

- CID is available for **Linux** as a `.deb` package for Debian, Ubuntu and derivatives (64-bit Intel/AMD). Install it with `sudo apt install ./cid_1.2.0_amd64.deb`. Workflows that run on your computer use Bash.

### New look

- Redesigned the whole app, with **light and dark themes**. Pick Light, Dark or System in Settings; the window's title bar follows along.
- **Ctrl+K search** jumps to any page or project, starts a new workflow, or switches the theme.
- The Overview now shows a 14-day activity chart and your success rate.

### Workflows

- Workflows open in a **full-page editor** instead of a small pop-up.
- Each step is a **multi-line code editor** with syntax highlighting, so long commands are readable.
- **Drag steps to reorder** them, and duplicate a step with one click.
- **Choose the shell** for workflows that run on this computer: Command Prompt, PowerShell or Git Bash. PowerShell and Bash steps stop at the first error.
- Give any step its own **working folder**, so you no longer need `cd` at the start of commands.
- "Server" is now **Runs on**, with "This computer" as an option of its own.
- Schedules show in plain English ("At 04:00 AM") and come with presets.
- **Duplicate** a workflow, or **Save & run** straight from the editor.
- CID warns you before you leave the editor with unsaved changes.

### Runs

- Run details open in a **side panel from anywhere**, with live, colour-coded logs, exit codes and how long each step took.
- **Run again** from the run panel.
- Filter runs by workflow, status and **date range**, with pages for long histories. Lists update live while runs happen.
- CID tells you when a run finishes: in the app, and with a desktop notification when CID is in the background.

### Other

- CID checks this page for new versions and tells you when an update is available. See **Settings → About CID**.
- Clearer confirmations everywhere. Deleting a project now asks you to type its name.

Existing workflows keep working as before: Command Prompt is still the default shell, and single-line commands run exactly as typed.

## [1.1.0] - 2026-10-09

### New

- **Run workflows on this computer.** Pick "No server (run on this computer)" on a workflow and its steps run locally in the project's repository folder, using the system shell. No SSH server needed. Project variables and secrets are passed in as environment variables.
- **Artifacts.** CID keeps the files your runs produce in its own data folder (`%APPDATA%\cid\artifacts\<project>\<workflow>\run-<n>`).
  - Add artifact paths to a workflow (one per line, `*` allowed in file names) and CID copies them in after a successful run. On a server workflow they're downloaded over SFTP.
  - Local steps can also write straight to `%CID_ARTIFACTS_DIR%`.
  - The run panel lists a run's artifacts with an "Open folder" button, and Settings shows where the artifacts folder is.

### Improved

- Cancelling a run stops the whole process tree for local steps, and cancelled runs are marked "cancelled" instead of "failed".

## [1.0.0] - 2026-09-14

First version of CID: CI/CD that runs on your own computer.

- **Projects and workflows.** Group workflows by project; each workflow is an ordered list of named steps.
- **Triggers.** Run a workflow by hand, on every push to a branch, or on a cron schedule.
- **SSH deploys.** Generate or import SSH keys, add servers, and test the connection. CID syncs your repository to the server over SFTP (optionally only the files that changed) and runs the steps there. No agent to install.
- **Proxy support.** Route SSH connections through a SOCKS5 proxy.
- **Environment.** Per-project variables and encrypted secrets, exported to every step.
- **Run history.** Branch, commit, duration and status for every run, with live step-by-step logs and cancel.

[1.2.0]: https://github.com/MohsenManoochehr/CID-releases/releases/tag/v1.2.0
[1.1.0]: https://github.com/MohsenManoochehr/CID-releases/releases/tag/v1.1.0
[1.0.0]: https://github.com/MohsenManoochehr/CID-releases/releases/tag/v1.0.0
