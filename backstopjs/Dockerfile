FROM dockerfile/nodejs
MAINTAINER Facundo Cabrera "cabrerafacundo@gmail.com"

# environment variables
ENV TARGET_DIR /opt/backstopjs

# prevent problems with blocked ssh connections
RUN git config --global url."https://".insteadOf git://

# copy bower configurations
COPY .bowerrc /
COPY .npmrc /

# Everything should be executed on the root directory
WORKDIR /

# package installation
RUN apt-get -yqq update
RUN apt-get -yqq install aptitude

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

# Complete backstopjs install
WORKDIR $TARGET_DIR/backstopjs
RUN npm install
