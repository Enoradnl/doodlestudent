FROM node:16-alpine AS build-step

WORKDIR /app

COPY package.json /app
RUN npm install --legacy-peer-deps

COPY . /app
RUN npm run build
RUN npm install serve -g

EXPOSE 3000

CMD serve -s ./dist/tlcfront/

FROM nginx as prod
COPY --from=build-step /app/dist/tlcfront /usr/share/nginx/html
