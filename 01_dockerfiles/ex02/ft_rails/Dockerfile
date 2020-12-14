FROM ruby

RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install && rails db:migrate && rails db:seed

ONBUILD COPY . /opt/app
ONBUILD WORKDIR /opt/app

# How to build it?
# docker build -t ft-rails:on-build .