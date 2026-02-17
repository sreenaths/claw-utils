# Claw Utils 🦞

Making OpenClaw easier 😌

These utils are to be run as admin user, OpenClaw must be run under standard user.

## 1. [LLM Proxy](./llm-proxy/)
## 2. [Git Backup](./git-backup/)
## 3. Hosting

Steps to host an embedding model using ollama to be shared between all openclaw instances.

### Install

```shell
brew install ollama
```

### Start in background

```shell
brew services start ollama
```

### Pull and host model

```shell
ollama pull embeddinggemma
```

### Testing

Once setup the following command should work.

```shell
curl http://localhost:11434/api/embeddings -d '{
  "model": "embeddinggemma",
  "prompt": "Hello world"
}'
```
