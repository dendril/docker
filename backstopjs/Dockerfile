FROM dockerfile/nodejs
MAINTAINER Facundo Cabrera "cabrerafacundo@gmail.com"

# environment variables
ENV TARGET_DIR /opt/backstopjs

# prevent problems with blocked ssh connections
RUN git config --global url."https://".insteadOf git://

# copy bower configurations
COPY .bowerrc /
COPY .npmrc /
COPY .sample.backstop.json /backstop.json

# Everything should be executed on the root directory
WORKDIR /

# ubuntu packages (mainly dependencies)
RUN apt-get -yqq update
RUN apt-get -yqq install aptitude g++ flex bison gperf ruby perl \
                         libsqlite3-dev libfontconfig1-dev libicu-dev \
                         libfreetype6 libssl-dev libpng-dev libjpeg-dev

# bower
RUN npm install -g bower

# backstopjs
RUN bower install --allow-root backstopjs

# phantomjs
RUN npm install -g phantomjs

# gulp
RUN npm install -g gulp

# casperjs
RUN npm install -g casperjs

# backstopjs dependencies installation
WORKDIR $TARGET_DIR
RUN npm install

# backstopjs dependencies installation (web deps)
WORKDIR $TARGET_DIR/compare
RUN bower install --allow-root

# leave you at useful location
WORKDIR $TARGET_DIR

# expose port for web tool
EXPOSE 3001
