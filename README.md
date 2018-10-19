# Rails for CI Docker Image
build from [official image](https://github.com/docker-library/ruby)

## Features
A few packages are installed:

- mysql-client
- postgresql-client
- sqlite3
- nodejs
- yarn (via npm)
- phantomjs (via npm)
- imagemagick
- mecab
- libmecab-dev
- mecab-ipadic-utf8
- unzip

and npm packages are installed:

## Usage
```
docker run -d parobus/rails-ci:latest
```

## Updating

This image is based off the [https://github.com/docker-library/ruby](base ruby image)
when that has the lastest ruby you can upgrade the CI stack. Copy over the most recent
folder to your target version, e.g. `cp -r 2.5.0 2.5.3` and edit the base Ruby image
in the `Dockerfile`, then:

1 - `docker build <target>/Dockerfile`
2 - `docker tag <resulting image> parobus/rails-ci:<target>`
3 - `docker push parabus/rails-ci:<target>`

Note you will need to be logged in as some with DockerHub priviledges.
