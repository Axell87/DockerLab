# GetImage 16
FROM node:13.12.0-alpine
# SetUp work DIR
WORKDIR /app
#Add ENV settings
ENV PATH /app/node_modules/.bin:$PATH
# install all app dependencies
COPY package.json .
COPY package-lock.json .
#RUN npm install
RUN npm install
RUN npm install react-scripts@3.4.1 -g

# add all data to container
COPY . .
# start app
CMD ["npm", "start"]

