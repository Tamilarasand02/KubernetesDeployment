# First stage: Build dependencies
FROM python:3.10.8-slim@sha256:49749648f4426b31b20fca55ad854caa55ff59dc604f2f76b57d814e0a47c181 as builder

# Update package list and install required packages
RUN apt-get -qq update \
    && apt-get install -y --no-install-recommends \
        wget g++ \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /recommendationservice

# Copy the requirements file and install dependencies
COPY requirements.txt ./
RUN pip install -r requirements.txt

# Copy the rest of the application files
COPY . .

# Expose the application port
EXPOSE 8085

# Command to run the application
CMD ["python", "recommendation_server.py"]
