FROM python:3.10-slim

# Set work directory
WORKDIR /app

# Copy requirements first (for better layer caching)
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# Expose port is only for the reader's information, 
# still need to map it when running the container
# e.g., docker run -p 8000:8000 welcome-flaskapp
EXPOSE 8000

# Command to run the application
CMD ["python","app.py"]