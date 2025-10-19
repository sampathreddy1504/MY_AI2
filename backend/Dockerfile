# Use fixed Python version 3.11.9
FROM python:3.11.9-slim

# Set working directory
WORKDIR /app

# Copy dependencies first to leverage Docker cache
COPY requirements.txt .

# Install dependencies
RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# Copy backend and frontend folders
COPY backend ./backend
COPY frontend ./frontend

# Set Python path to backend folder
ENV PYTHONPATH=/app/backend

# Expose port Render will use
EXPOSE 8000

# Start the app using uvicorn
CMD ["uvicorn", "backend.app.main:app", "--host", "0.0.0.0", "--port", "8000"]
