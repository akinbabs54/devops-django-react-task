#pull the official base image
FROM python:3.8.3-alpine

# setup environment variable
ENV DockerHOME=/home/app/webapp

#set WORk directory
RUN mkdir -p $DockerHOME

#setup the work directory
WORKDIR $DockerHOME

#set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Install dependencies
RUN pip install --upgrade pip

# Copy everything else
COPY . $DockerHOME

#install all dependencies
RUN pip install -r requirements.txt

#port on Django app runs
EXPOSE 8000

#Run the commands to start server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
