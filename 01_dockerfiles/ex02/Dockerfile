FROM ruby

RUN apt-get update -y && apt-get install -y --no-install-recommends \
    build-essential libpq-dev sqlite3 nodejs yarn git && apt-get update && apt-get upgrade
    
RUN gem install rails bundler
RUN gem install rails
RUN rails new hello-world

ONBUILD COPY hello-world /opt/app

ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000

ONBUILD RUN bundle install

ONBUILD RUN rake db:migrate

ONBUILD RUN rake db:seed

#docker build -t ft-rails:on-build ./ft-rails
#docker build -t do .
#docker run --name ss --rm -p 3000:3000 do
