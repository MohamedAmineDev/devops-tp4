FROM node
WORKDIR /src
COPY /src /src
COPY package.json package.json
RUN npm install
CMD ["ng","serve"]
EXPOSE 3000
