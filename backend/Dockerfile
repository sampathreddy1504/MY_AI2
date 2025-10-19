# Use specific Python version
FROM python:3.11.9-slim

# Set working directory
WORKDIR /app

# Copy requirements and install
COPY requirements.txt .
RUN pip install --upgrade pip && pip install --no-cache-dir -r requirements.txt

# Copy backend and frontend
COPY backend ./backend
COPY frontend ./frontend

# Set Python path to backend folder
ENV PYTHONPATH=/app/backend

# Expose port (Render expects a port to bind)
EXPOSE 8000

# Run the backend app with uvicorn
CMD ["uvicorn", "backend.app.main:app", "--host", "0.0.0.0", "--port", "8000"]
