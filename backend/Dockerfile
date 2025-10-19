# Use fixed Python version
FROM python:3.11.9-slim

# Set working directory
WORKDIR /app

# Copy requirements and install
COPY requirements.txt .
RUN pip install --upgrade pip && pip install --no-cache-dir -r requirements.txt

# Copy backend and frontend
COPY backend ./backend
COPY frontend ./frontend

# Set Python path for nested backend
ENV PYTHONPATH=/app

# Environment variables
ENV PORT=8000

# Expose port
EXPOSE 8000

# Run Uvicorn with nested app path
CMD ["uvicorn", "backend.app.main:app", "--host", "0.0.0.0", "--port", "8000"]
