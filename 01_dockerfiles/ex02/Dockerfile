FROM ruby

RUN apt-get update -y && apt-get install -y \
    build-essential libpq-dev sqlite3 nodejs 

ONBUILD COPY hello-world /opt/app

ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000

ONBUILD RUN bundle install

ONBUILD RUN rake db:migrate

ONBUILD RUN rake db:seed

#rails new hello-world