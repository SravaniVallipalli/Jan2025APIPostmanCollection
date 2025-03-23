# use the official Node.js image as the base image
FROM node:22

# set the working directory in the container(linux)
WORKDIR /app

#install newman globally
RUN npm install -g newman

#install newman html report
RUN npm install -g newman-reporter-html newman-reporter-htmlextra



#copy your postman collection and environemt files to the working directory
COPY DataDrivenAPIsCollection.json .
COPY GoRestEnv.json .
COPY myuser.csv . 

# set the command to run newman and execute your postman collection
CMD ["newman", "run", "DataDrivenAPIsCollection.json", "-e", "GoRestEnv.json", "-d", "myuser.csv", "-r", "cli,json,html,htmlextra"]
