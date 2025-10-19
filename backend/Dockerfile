# Use official Python 3.11 slim image
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy dependency list first (better layer caching)
COPY requirements.txt .

# Upgrade pip and install dependencies
RUN pip install --upgrade pip \
    && pip install --no-cache-dir -r requirements.txt

# Copy the rest of the app code
COPY . .

# NOTE: Don't copy .env — Render injects environment variables automatically
# COPY .env /app/.env  ← removed

# Expose FastAPI port (Render usually maps this automatically)
EXPOSE 5000

# Start the FastAPI app
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "5000"]
