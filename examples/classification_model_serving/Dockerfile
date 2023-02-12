# Use an official Python runtime as a parent image
FROM python:3.6-slim

# Copy the requirements file into the image
COPY ./requirements.txt /app/requirements.txt

# Set the working directory to /app
WORKDIR /app

# Install any needed packages specified in requirements.txt
RUN pip install -r requirements.txt

# copy every content from the local file to the image
COPY . /app

# Configure the container to run in an executed manner
ENTRYPOINT [ "python" ]

CMD ["server.py"]