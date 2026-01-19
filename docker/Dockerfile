FROM python:3.11-slim

WORKDIR /app

# System dependencies needed by pip packages
RUN apt-get update && apt-get install -y \
    build-essential \
    gcc \
    libffi-dev \
    && rm -rf /var/lib/apt/lists/*

# 1️⃣ Copy requirements first
COPY app/requirements.txt .

# Show pip + Python versions (debug)
RUN python --version && pip --version

# Install Python dependencies (verbose)
RUN pip install -vvv --no-cache-dir -r requirements.txt

# 3️⃣ Copy application code
COPY app/app.py .

EXPOSE 5000

CMD ["python", "app.py"]
