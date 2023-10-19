FROM node:16-alpine
COPY . .
RUN npm install
RUN npm build --prod
CMD ["npm","serve","--prod","--host 0.0.0.0"]
