FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Environment variable to allow pip to break system packages
ENV PIP_BREAK_SYSTEM_PACKAGES=1

# Copy the requirements file and devops directory
COPY requirements.txt /app
COPY devops /app

# Install Python and pip, then install the requirements
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip install -r requirements.txt && \
    cd devops

# Ensure manage.py is executable
RUN chmod +x manage.py

# Set the entry point and command
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
