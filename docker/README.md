## Docker Overview

To use `docker run`:

1. First, build the Docker image. Navigate to the root of the repository and execute this command:

```bash
docker build -t ollama-obisidian-indexer -f docker/Dockerfile .
```

2. Now, you can run the Docker container using `docker run` command. Run the following command from the parent directory:

```bash
docker run \
  --name ollama-obsidian-indexer \
  -v "$(pwd)/INDEX_STORAGE:/app/.storage" \
  -v "$(pwd)/huggingface_cache:/root/.cache/huggingface/" \
  -v "$(pwd)/.env:/app/.env" \
  -e TZ=America/Chicago \
  ollama-obisidian-indexer python index.py
```

Note you will need to create a `.env` file.