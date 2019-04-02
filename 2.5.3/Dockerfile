FROM ruby:2.5.3

ENV LC_ALL=C.UTF-8

RUN \
  curl -sL https://deb.nodesource.com/setup_8.x | bash - && \
  curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
  echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
  curl -sS https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add - && \
  echo "deb http://apt.postgresql.org/pub/repos/apt/ stretch-pgdg main" |  tee /etc/apt/sources.list.d/pgdg.list && \
  curl -sS https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - && \
  echo "deb http://dl.google.com/linux/chrome/deb/ stable main" | tee /etc/apt/sources.list.d/chrome.list && \
  apt-get update && \
  apt-get install -y --no-install-recommends \
      mysql-client \
      postgresql-client-10 \
      sqlite3 \
      nodejs \
      yarn \
      imagemagick \
      mecab libmecab-dev mecab-ipadic-utf8 \
      libxss1 libappindicator1 libindicator7 \
      fonts-liberation libappindicator3-1 libasound2 \
      libatk-bridge2.0-0 libatspi2.0-0 libgtk-3-0 \
      libnspr4 libnss3 libxtst6 xdg-utils \
      google-chrome-stable \
      libgconf-2-4 xvfb unzip && \
  wget -N https://chromedriver.storage.googleapis.com/73.0.3683.68/chromedriver_linux64.zip && \
  unzip chromedriver_linux64.zip && \
  chmod +x chromedriver && \
  mv -f chromedriver /usr/local/share/chromedriver && \
  ln -s /usr/local/share/chromedriver /usr/local/bin/chromedriver && \
  ln -s /usr/local/share/chromedriver /usr/bin/chromedriver && \
  rm -rf /var/lib/apt/lists/*  /tmp/*
