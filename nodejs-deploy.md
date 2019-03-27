# nodejs deploy on docker

The dockerfile


```dockerfile
# get node
FROM node:10-alpine
# create directory
RUN mkdir -p /src/app
# set as work dir
WORKDIR /src/app
# copy package.json to check updates
COPY package.json .
# run npm -i
RUN npm install
# copy application
COPY . ./
# open port 3000
EXPOSE 3000
# npm run
CMD ["npm", "start"]
```

The just "docker build -t nodeapp .