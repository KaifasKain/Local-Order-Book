FROM ruby:2.6.5-alpine

RUN apk add --no-cache --update build-base openssl openssl-dev

RUN echo 'gem: --no-document' > ~/.gemrc
RUN gem install bundler --without development test

ENV APP_HOME /app/
COPY Gemfile Gemfile.lock $APP_HOME
WORKDIR $APP_HOME
RUN bundle install
COPY . $APP_HOME
