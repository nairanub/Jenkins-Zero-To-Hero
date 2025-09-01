FROM python:3.13-slim

# Install system deps
RUN apt-get update && apt-get install -y python3-setuptools python3-pip python3-wheel

# Install distutils replacement (packaging)
RUN pip install --upgrade pip setuptools wheel packaging

# Set working directory
WORKDIR /app

# Copy requirements
COPY requirements.txt .

# Install Python dependencies
RUN pip install -r requirements.txt

# Copy project files
COPY . .

# Run migrations (if needed in build)
RUN python manage.py migrate
