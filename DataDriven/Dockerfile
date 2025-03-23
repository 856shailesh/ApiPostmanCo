# Use the official Node.js 20 image as the base image
FROM node:20

# Set the working directory in the container
WORKDIR /app


# Install Newman globally
RUN npm install -g newman newman-reporter-html newman-reporter-htmlextra


# Copy your Postman collection and environment files to the working directory
COPY DataDrivenAPI.json .
COPY GoRestEnv.json .
COPY myuser.csv .

# Set the command to run Newman and execute your Postman collection
CMD ["newman", "run", "DataDrivenAPI.json", "-e", "GoRestEnv.json", "-d", "myuser.csv", "-r", "cli,json,html,htmlextra"] 