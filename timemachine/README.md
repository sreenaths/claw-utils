# TimeMachine

**Prerequisite: uv, rsync**

TimeMachine is a tool designed to create a timeline of all file changes in the `~/.openclaw` directory on git. Each change is automatically committed into a repository of your choice, providing visibility into the inner workings of your OpenClaw instance.

## Setup

```shell
# Install the latest version of `rsync`
brew install rsync

# Sync your environment using `uv`
uv sync
```

## Usage
To run TimeMachine, use the following command:

```shell
sudo uv run python ./watcher.py /home/agent-user/.openclaw /path/to/local/repo
```

Replace `/home/agent-user/.openclaw` with the path to the `.openclaw` directory you want to monitor, and `/path/to/local/repo` with the path to your local repository where changes will be committed.

> **Note:** The `sudo` command is required to read from another user's space.
