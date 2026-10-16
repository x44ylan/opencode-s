# opencode-s

List, inspect, resume, rename, and delete local OpenCode sessions with the `oc` CLI.

## Install

Requires Node.js 24 or later and OpenCode on your `PATH`.

```sh
npm install -g opencode-s
```

## Usage

```sh
oc help
oc new
oc list
oc resume
oc resume "Fix login"
oc view ses_abc123
oc rename ses_abc123 "Login fix"
oc projects
oc delete
oc delete ses_abc123 ses_def456
```

Session arguments accept IDs, titles, or unique prefixes. Ambiguous matches open
a picker. Without an argument, `oc resume` uses sessions in the current directory.

In pickers, type to filter, use arrow keys to move, and press `Enter` to select.
Press `Ctrl+C` to cancel. In the deletion picker, `Space` toggles selections.

## Cleanup and deletion

```sh
oc cleanup
oc cleanup --vacuum
```

> [!WARNING]
> Deletion asks for confirmation and also removes child sessions. There is no undo.
> Cleanup immediately removes stale session-diff files without confirmation or a
> dry run. `--vacuum` also compacts the database. Back up important data first;
> avoid vacuuming an active database.

## Fish completions

```sh
mkdir -p ~/.config/fish/completions
oc completion fish > ~/.config/fish/completions/oc.fish
```

Open a new Fish shell to load the completions.
