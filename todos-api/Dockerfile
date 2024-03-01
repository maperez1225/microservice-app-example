FROM node:18.17.0-alpine
RUN mkdir -p /home/node/app/node_modules
RUN chown -R node:node /home/node/app
WORKDIR /home/node/app
COPY --chown=node:node package*.json .
USER node
RUN npm install
COPY --chown=node:node *.js .
EXPOSE 8082
ENV JWT_SECRET=PRFT
ENV TODO_API_PORT=8082
CMD ["npm", "start"]