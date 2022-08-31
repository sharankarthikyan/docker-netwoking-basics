## In this app, we are connecting web-app and mongodb

Steps to communicate between two docker containers:

1. Run mongodb: `docker run mongo` or `docker run -d mongo` or `docker run --name mongodb -d mongo`
2. Now, run the inspect command to see IPAddress of the mongo container: `docker inspect <CONTAINER_ID/NAME>`
3. Inside `NetworkSettings`, you will see a `IPAddress` key, which is the IP address / host the container app is running. (For me, IPAddress of mongodb is `172.17.0.2`)
4. Now, paste this IP address in the mongodb connection URL and build the docker image and run container by the image we have created.
5. Finally, open Postman and send request to the web-server APIs, it will communicates with the mongo server, returns a response to web-server and web-server sends a response to client postman.
