FROM python:3.12-alpine

WORKDIR /app

RUN adduser -D user
USER user

ENV PYTHONUNBUFFERED=1

RUN apk add --no-cache git \
    && git clone https://github.com/brumik/ollama-obsidian-indexer.git .

RUN apk add --no-cache --virtual .build-deps gcc musl-dev \
    && pip install --no-cache-dir -r requirements.txt \
    && apk del .build-deps

CMD ["python", "index.py"]
