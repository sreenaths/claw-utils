# TimeMachine

**Prerequisite: uv, rsync**

TimeMachine is a tool designed to create a timeline of all the file changes in the `~/.openclaw` directory using git. Each change is automatically committed and pushed into a repository of your choice, providing visibility into the inner workings of your OpenClaw agent.

## Setup

```shell
# Install the latest version of `rsync`
brew install rsync

# Grant admin group read/traverse ACL access for rsync
sudo chmod -R +a "group:admin allow read,execute,file_inherit,directory_inherit" /path/to/.openclaw
```

## Usage
Run the TimeMachine watcher script to start monitoring and syncing changes.

```shell
uv run python ./watcher.py /path/to/.openclaw /path/to/local/repo mybot_v1
```

The script requires three positional arguments:
1. **Source Directory**: The path to the `.openclaw` directory that you want to monitor for changes.
2. **Target Repository**: The path to your local Git repository where the changes will be committed and pushed.
3. **Target Directory**: The name or path of a subdirectory within the repository where the files will be added. This can include details like your agent's name or deployment version, making it easier to organize multiple agent instances within a single repository.

> Note that the target directory will be overwritten.
