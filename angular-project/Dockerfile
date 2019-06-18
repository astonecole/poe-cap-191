FROM node AS ngbuild

LABEL MAINTAINER="Vincent Letourneau <vincent@nanoninja.com>"
WORKDIR /home/node/app
COPY . .
RUN npm install \
    && npm run build --prod --output-path=dist

FROM nginx:1.17.0-alpine
COPY --from=ngbuild /home/node/app/dist/angular-project /usr/share/nginx/html
CMD [ "nginx", "-g", "daemon off;" ]
