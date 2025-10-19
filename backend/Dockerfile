# Use specific Python version 3.11.9 slim
FROM python:3.11.9-slim

# Set working directory
WORKDIR /app

# Copy requirements and install
COPY requirements.txt .
RUN pip install --upgrade pip && pip install --no-cache-dir -r requirements.txt

# Copy backend folder
COPY backend ./backend

# Optional: copy frontend if needed
COPY frontend ./frontend

# Optional: copy .env if you have one
# COPY .env .env

# Set environment variable for Render
ENV PORT=8000

# Expose port
EXPOSE 8000

# Set PYTHONPATH so Python can find backend.app
ENV PYTHONPATH=/app

# Run Uvicorn server (pointing to nested main.py)
CMD ["uvicorn", "backend.app.main:app", "--host", "0.0.0.0", "--port", "8000"]
