# DOCKER FILE FOR DATA-MONGER
FROM python:3.7-stretch

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --trusted-host pypi.python.org -r requirements.txt

RUN python -m spacy download en_core_web_sm

CMD ["python", "test/aws.py"]