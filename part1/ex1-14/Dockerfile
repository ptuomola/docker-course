FROM ruby:2.6.0
RUN git clone https://github.com/ptuomola/rails-example-project.git
WORKDIR rails-example-project
RUN bundle install
RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install -y nodejs
RUN rails db:migrate
EXPOSE 3000
ENV RAILS_LOG_TO_STDOOUT=true
ENTRYPOINT ["rails", "s"]
