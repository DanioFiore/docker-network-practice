# The FE setup is in reach but it depends to node, so here we make a Dockerfail based on it. Node is used to make sure that the browser understand our React code.
FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3001

# see in package.json the start script
CMD ["npm", "start"]

# To make sure the React container run, we have to add the interactive command -it

# Pay attention to this problem: If we have a network with DB, BE, FE there is a problem, because the browser didn't know our containers name. To make sure that the FE can communicate with the BE container, we have to not put the FE in the network, and the BE will be in the network and also exposed to a port, in this case 95:95 and the FE 3001:3001. In this case we make sure that the endpoint are accessible from the browser