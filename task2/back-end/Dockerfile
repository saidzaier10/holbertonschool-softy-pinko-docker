FROM ubuntu:latest

# Update and install Python3 and pip
RUN apt-get update && apt-get install -y python3 python3-pip

# Install Flask
RUN pip3 install flask

# Set working directory
WORKDIR /app

# Copy the API file
COPY api.py /app

# Expose port 5252
EXPOSE 5252

# Run the Flask application
CMD ["python3", "api.py"]