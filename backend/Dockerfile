# # # Use an official Python runtime as a parent image
# # FROM python:3.10-slim

# # # Set environment variables to prevent Python from writing pyc files to disk and to prevent buffering
# # ENV PYTHONUNBUFFERED=1
# # ENV POETRY_VERSION=1.1.13

# # # Set the working directory in the container
# # WORKDIR /app

# # # Copy the requirements file into the container
# # COPY pyproject.toml poetry.lock ./

# # # Install Poetry
# # RUN apt-get update && apt-get install -y curl \
# #     && curl -sSL https://install.python-poetry.org | python3 - \
# #     && ln -s /root/.local/bin/poetry /usr/local/bin/poetry

# # # Install dependencies using Poetry
# # RUN poetry install --no-root --no-interaction --no-ansi

# # # Copy the rest of the application code
# # COPY . .

# # # Run the FastAPI server
# # CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
# # Use an official Python runtime as a parent image
# FROM python:3.8-slim

# # Set the working directory in the container
# WORKDIR /app

# # Install Poetry
# RUN pip install poetry

# # Copy the pyproject.toml and poetry.lock files to the container
# COPY pyproject.toml poetry.lock ./

# # Install dependencies
# RUN poetry install --no-root --no-interaction --no-ansi

# # Copy the rest of the application code to the container
# COPY . .

# # Expose the port the app runs on
# EXPOSE 8000

# # Run the FastAPI application
# CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
# Use an official Python 3.10 runtime as a parent image
FROM python:3.10-slim

# Set the working directory in the container
WORKDIR /app

# Install Poetry
RUN pip install poetry

# Copy the pyproject.toml and poetry.lock files to the container
COPY pyproject.toml poetry.lock ./

# Install dependencies
RUN poetry install --no-root --no-interaction --no-ansi

# Copy the rest of the application code to the container
COPY . .

# Expose the port the app runs on
EXPOSE 8000

# Run the FastAPI application
CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
