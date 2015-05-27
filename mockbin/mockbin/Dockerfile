# Version 1.0.0
FROM mashape/mockbin

RUN npm config set mockbin:redis redis://redis:6379

EXPOSE 8080

ENTRYPOINT npm start
