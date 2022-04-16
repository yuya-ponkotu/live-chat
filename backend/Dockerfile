FROM ruby:2.7.1
ARG WORKDIR
ENV HOME=/${WORKDIR}
RUN apt-get update -qq && apt-get install -y nodejs  postgresql-client yarn
WORKDIR ${HOME}
COPY Gemfile /${HOME}/Gemfile
COPY Gemfile.lock /${HOME}/Gemfile.lock
RUN bundle install

# Add a script to be executed every time the container starts.
COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]

# Configure the main process to run when running the image
CMD ["rails", "server", "-b", "0.0.0.0"]