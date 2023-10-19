FROM node:16-alpine
COPY . .
RUN npm install
RUN ng build --prod
CMD ["ng","serve","--prod","--host 0.0.0.0"]
