# Gebruik een image met Node.js als basis
FROM node:18

ADD . /app

# Set de werkmap binnen de container
WORKDIR /app

# ARG-instructie om de environmentvariabele te ontvangen
ARG BACKEND_URL

# Stel de environmentvariabele in voor de Vue.js-applicatie
ENV BACKEND_URL=$BACKEND_URL

# Installeer de afhankelijkheden
RUN npm install

# Expose de poort waarop de applicatie draait (optioneel, afhankelijk van je configuratie)
EXPOSE 8080

# Commando om live reloading te ondersteunen
CMD ["npm", "run", "serve"]
