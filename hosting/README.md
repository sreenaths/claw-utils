# Hosting an Embedding Model

Follow these steps to host an embedding model locally using Ollama, enabling it to be shared seamlessly across all OpenClaw instances.

## Setup

### Installation

```shell
brew install ollama
```

### Start Ollama

Start the Ollama service in the foreground.

```shell
ollama serve
```

> Use a new tab for the remaining commands.

### Download and Host the Model

```shell
ollama pull embeddinggemma
```

## Testing the Setup

After completing the setup, you can test the embedding model with the following command:

```shell
curl http://localhost:11434/api/embeddings -d '{
  "model": "embeddinggemma",
  "prompt": "Hello world"
}'
```
