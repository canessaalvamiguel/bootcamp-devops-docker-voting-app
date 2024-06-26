# Voting app
Welcome to the DevOps bootcamp from Codigo Facilito!

In this module, our objective was to develop a Docker Compose file capable of orchestrating the various services within the voting application. To accomplish this, each service is accompanied by a Dockerfile, facilitating the construction of its respective container. The Docker Compose then seamlessly runs these containers, providing a comprehensive environment for the voting app to operate.

# Voting-app-devops
![](architecture.excalidraw.png)
La aplicación comprende varios componentes esenciales: 
- Una aplicación web front-end en Python [python:3.11], 
- Un backend .NET [dotnet/sdk:7.0] [dotnet/runtime:7.0]
- Un servidor Redis para votos [redis:alpine], 
- Una base de datos PostgreSQL [postgres:15-alpine] respaldada por un volumen Docker, 
- y Una aplicación web Node.js [Node 18] que muestra los resultados de la votación en tiempo real.

#Run using docker-Compose

```shell
docker-compose up --build
```

# Please notice
Something to notice regarding nginxproxy:
```diff
- The services (vote and result) need to be mapped to port 80 by default. 
```
I was unable to reach result service when it was mapper to 4000 port, I changed it to 80
and it worked. Check the commit:  "Only expose endpoint by the proxy"