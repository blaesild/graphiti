FROM python:3.11-slim

WORKDIR /app

# Install curl and uv
RUN apt-get update && apt-get install -y curl && \
    curl -LsSf https://astral.sh/uv/install.sh | sh && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Add uv to PATH
ENV PATH="/root/.local/bin:${PATH}"

# Copy requirements file
COPY pyproject.toml .

# Install dependencies
RUN uv sync

# Copy application files
COPY graphiti_mcp_server.py .
COPY .env .

# Set environment variables
ENV PYTHONUNBUFFERED=1

# Create a simplified entrypoint script
RUN echo '#!/bin/sh\nexec "$@"' > /entrypoint.sh && chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
CMD ["uv", "run", "graphiti_mcp_server.py", "--transport", "sse"]
