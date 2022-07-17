FROM ruby:2.7.0

RUN apt-get update && \
    apt-get install -y wget build-essential default-mysql-client default-libmysqlclient-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

COPY ruby/public /webapp/public
WORKDIR /webapp/ruby
COPY ruby/Gemfile* /webapp/ruby
RUN bundle install --jobs 300
ENV LANG=C.UTF-8
