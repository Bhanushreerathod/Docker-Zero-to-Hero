FROM ubuntu
WORKDIR /app

# Copy requirements.txt and devops directory to /app in the container
COPY requirements.txt /app
COPY devops /app


# Update apt-get and install Python 3 and pip
RUN apt-get update && \
    apt-get install -y python3 python3-pip

# Install Python packages from requirements.txt
RUN pip install -r requirements.txt -v

# Change directory to /app/devops (assuming this is necessary for your application)
WORKDIR /app/devops

# Set the entry point and default command to run the Django server
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]

