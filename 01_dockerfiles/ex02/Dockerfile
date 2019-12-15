FROM ruby
RUN apt -y update && apt -y upgrade \
	&& apt -y install nodejs
RUN gem install rails && gem update bundler
ONBUILD COPY ./myapp /opt/app
WORKDIR /opt/app
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed
