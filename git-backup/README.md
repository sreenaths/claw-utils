# Git Backup for OpenClaw

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
