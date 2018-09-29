# Version: 0.1.0
FROM node:alpine
MAINTAINER Brock Research 

RUN npm install -g gitbook-cli@2.3.2 && gitbook fetch 3.2.3

RUN mkdir -p /var/books

CMD ["/bin/sh"]