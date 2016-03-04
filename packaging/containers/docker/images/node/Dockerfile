FROM ubuntu:14.04

RUN  apt-get update && apt-get install -y git curl && rm -rf /var/lib/apt/lists/*
RUN  curl -sL https://deb.nodesource.com/setup | sudo bash - && rm -rf /var/lib/apt/lists/*
RUN  apt-get update && apt-get install -y nodejs && rm -rf /var/lib/apt/lists/*
RUN  curl -L https://npmjs.org/install.sh | sh && rm -rf /var/lib/apt/lists/*
RUN  npm install -g bower
RUN  npm install -g sails

RUN git clone https://github.com/elsix/angular-jointjs-graph-demo.git app
RUN cd /app && npm install
RUN cd /app && bower install --allow-root

RUN echo 'module.exports.host = "0.0.0.0";' > /app/config/application.js
COPY connections.js /app/config/connections.js
COPY production.js /app/config/envs/production.js
