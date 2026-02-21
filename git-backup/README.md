# Git Backup for OpenClaw

**Prerequisite: uv**

Creates a timeline of all files changes in `.openclaw` on git. Each change will be automatically committed into a repo of your choice, providing visibility into the inner working of your openclaw instance.

## Setup
```shell
# We need the latest rsync
brew install rsync

uv sync
```

## Run
```shell
sudo uv run python ./watcher.py /home/otheruser/somedir /path/to/local/repo
```
