# select the base image we would like to use for our app
FROM python:3.9-slim-buster

# instructs Docker to create and use "/app" as the default location for all commands
WORKDIR /app

# copy the requirements.txt file into our image
COPY requirements.txt requirements.txt

# execute the command to install our requirements (from our default location)
RUN pip install -r requirements.txt

# we now have an image based on Python 3.9 and Flask.
# next, we'll copy all files in the current directory on to the image
COPY app.py app.py
COPY Dockerfile Dockerfile

# run this command when our image is executed inside a container.
# ---host0.0.0.0 makes the app externally visible (outside the container)
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]