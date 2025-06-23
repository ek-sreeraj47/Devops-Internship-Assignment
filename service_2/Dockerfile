FROM python:3.11-slim

WORKDIR /app

# Install dependencies and uv
RUN apt-get update && apt-get install -y curl unzip && rm -rf /var/lib/apt/lists/*
RUN curl -Ls https://astral.sh/uv/install.sh | bash

# Add uv to PATH
ENV PATH="/root/.local/bin:${PATH}"

# Copy code
COPY . .

# Setup virtual environment and install Flask
RUN uv venv .venv
RUN uv pip install flask

EXPOSE 8002
CMD ["./.venv/bin/python3", "app.py"]

