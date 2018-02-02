FROM python:3.6

# install google chrome
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
RUN sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
RUN apt-get -y update
RUN apt-get install -y google-chrome-stable

# install chromedriver
RUN apt-get install -yqq unzip
RUN wget -O /tmp/chromedriver.zip http://chromedriver.storage.googleapis.com/`curl -sS chromedriver.storage.googleapis.com/LATEST_RELEASE`/chromedriver_linux64.zip
RUN unzip /tmp/chromedriver.zip chromedriver -d /usr/local/bin/

# install xvfb
RUN apt-get install -yqq xvfb

# install firefox driver
RUN wget -O /tmp/geckodriver.tar.gz https://github.com/mozilla/geckodriver/releases/download/v0.19.1/geckodriver-v0.19.1-linux64.tar.gz
RUN tar -xvzf /tmp/geckodriver.tar.gz -C /usr/local/bin/
RUN ls /usr/local/bin/

#install Firefox
RUN apt-get install -y firefox

# set display port to avoid crash
ENV DISPLAY=:99
ENV DBUS_SESSION_BUS_ADDRESS=/dev/null
