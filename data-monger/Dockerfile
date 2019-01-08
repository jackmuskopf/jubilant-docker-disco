# DOCKER FILE FOR DATA-MONGER
FROM ubuntu-py3.6:latest

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# download version of geckodriver for firefox
RUN apt-get install -y firefox
RUN wget https://github.com/mozilla/geckodriver/releases/download/v0.23.0/geckodriver-v0.23.0-linux64.tar.gz \
	--&& tar -xvzf geckodriver-v0.23.0-linux64.tar.gz \
	--&& chmod +x geckodriver \
	--&& mv geckodriver /usr/bin/geckodriver


# Install any needed packages specified in requirements.txt
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# run nltk.download('punkt')
RUN python3.6 /app/run_setup.py

RUN touch ~/.bash_alias \
	--&& echo 'alias python="python3.6"' >> ~/.bash_alias
