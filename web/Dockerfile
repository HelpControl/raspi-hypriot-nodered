FROM hypriot/rpi-node:7

# Node-RED
RUN npm cache clean && \
    npm install -g --unsage-perm node-red

RUN mkdir /root/.node-red && \
    mkdir /root/.node-red/flow && \
    cp /usr/local/lib/node_modules/node-red/settings.js /root/.node-red/
#   sed -i -e "s/\/\/userDir.*$/userDir: '\/root\/.node-red\/flow\/',/" /root/.node-red/settings.js

VOLUME /root/.node-red

EXPOSE 1880

WORKDIR /root

# sensortag for Node-RED
RUN apt-get update && \
    apt-get install -y bluetooth && \
    npm install node-red-node-sensortag

# Azure for Node-Red
RUN npm install node-red-contrib-azure-blob-storage
RUN npm install node-red-contrib-azure-iot-hub

# command
COPY startup-script /opt/startup-script
RUN chmod +x /opt/startup-script

CMD ["/opt/startup-script"]
