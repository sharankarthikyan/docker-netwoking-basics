## In this app, we are connecting web-app and mongodb

Elegant Container to Container communication:

1. Create a network: `docker network create <NETWORK_NAME>`. Example: `docker network create app-network`

2. Run mongo image using network tag: `docker run -d --rm --name mongodb --network app-network mongo`. Make sure to remember this container name `mongodb`, because we replace this container name in place of mongodb connection ip address area.

3. Run this app's image: `docker run -d --rm --name web-app --network app-network -p 3000:3000 doc-net-01`
