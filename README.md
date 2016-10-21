# dockerized-mean
Project regarding the dockerized a MEAN stack project.


Require
node
docker

Go to the directory that has your Dockerfile and run the following command to build the Docker image. The -t flag lets you tag your image so it's easier to find later using the docker images command:
```
$ docker build -t <your username>/node-web-app .
```
run
```
$ docker run -p 49160:8080 -d <your username>/node-web-app
```
To test your app, get the port of your app that Docker mapped:
```
$ docker ps

# Example
ID            IMAGE                                COMMAND    ...   PORTS
ecce33b30ebf  <your username>/node-web-app:latest  npm start  ...   49160->8080
```


Now you can call your app using curl (install if needed via: sudo apt-get install curl):

```
$ curl -i localhost:49160

HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: text/html; charset=utf-8
Content-Length: 12
Date: Sun, 02 Jun 2013 03:53:22 GMT
Connection: keep-alive

Hello world
```

Based on this tutorial:

https://nodejs.org/en/docs/guides/nodejs-docker-webapp/
