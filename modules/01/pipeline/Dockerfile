# base image
FROM python:3.13.10-slim

# copy uv into image
COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin

# set working directory
WORKDIR /code

# add virutalenv to path to use installed libs
ENV PATH="/code/.venv/bin:$PATH"

# copy project to image and sync packages
COPY . .
RUN uv sync --locked

ENTRYPOINT ["uv", "run", "python", "ingest_data.py"]