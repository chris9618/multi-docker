FROM node:alpine

WORKDIR '/app'

COPY ./package.json ./

RUN npm install 

COPY . . 

RUN npm run build 


COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

COPY --from=1 /app/build /usr/share/nginx/html

