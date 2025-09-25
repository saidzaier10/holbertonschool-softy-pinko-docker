# Use the latest Ubuntu as the base image
FROM ubuntu:latest

# Update the package list
RUN apt-get update

# Upgrade currently installed packages
RUN apt-get upgrade -y

# Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# Remove the EXTERNALLY-MANAGED file to allow pip installations
RUN rm -f /usr/lib/python*/EXTERNALLY-MANAGED

# Install Flask using pip3
RUN pip3 install flask

# Set the working directory to /app
WORKDIR /app

# Copy the Python file to the Docker image
COPY ./api.py /app/api.py

# Set the default command to run the Flask app
CMD ["python3", "api.py"]