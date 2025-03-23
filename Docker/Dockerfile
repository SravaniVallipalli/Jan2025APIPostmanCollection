# use the official Node.js image as the base image
FROM node:22

# set the working directory in the container(linux)
WORKDIR /app

#install newman globally
RUN npm install -g newman

#install newman html report
RUN npm install -g newman-reporter-html

#install newman reporter htmlextra
RUN npm install -g newman-reporter-htmlextra

#copy your postman collection and environemt files to the working directory
COPY GoRestAPIWorkflowNAL.json .
COPY GoRestEnv.json . 

# set the command to run newman and execute your postman collection
CMD ["newman", "run", "GoRestAPIWorkflowNAL.json", "-e", "GoRestEnv.json", "-r", "cli,json,html,htmlextra"]
