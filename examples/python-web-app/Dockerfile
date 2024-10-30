FROM ubuntu:latest

WORKDIR /app

ENV PIP_BREAK_SYSTEM_PACKAGES=1

COPY requirements.txt /app
COPY devops /app

RUN apt-get update && \
    apt-get install python3 python3-pip && \
    pip install -r requirements.txt && \
    cd devops

ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
