# TODO List
The goal of the project is to create an application with a functionality to create a simple TODO list.

## Tech Stack
* Docker (https://www.docker.com/)
* FastAPI web framework (https://fastapi.tiangolo.com/) 
* HTML + Javascript (for practice)
* SQLite with SQLAlchemy
* frontend served using simple HTTP server written in NodeJS
* Jenkins CI/CD

## Dependencies
### Docker
Install
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```
Add current user to group docker
```
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker 
```
Run the Docker daemon as a non-root user (Rootless mode)
https://docs.docker.com/engine/security/rootless/

## Cheatsheet
Remove unused images
```
docker image prune
```
Stop container
```
docker container stop <container_name>
```
Bash into container
```
docker exec -it <container_name> /bin/bash
```

## Problems
### Cannot access frontend
index.html was not visible from host. Server was hosting on 127.0.0.1 which meant that it was not forwarded outside of container. Solution was to change the address to 0.0.0.0.
https://stackoverflow.com/questions/39525820/docker-port-forwarding-not-working
### CORS
https://fastapi.tiangolo.com/tutorial/cors/
### JQuery POST JSON
1. Set content type to application/json
https://stackoverflow.com/questions/2845459/jquery-how-to-make-post-use-contenttype-application-json
2. Stringify JSON
https://stackoverflow.com/questions/5570747/jquery-posting-json
### Form submit clearing logs
site is not reloaded when onsubmit function returns false
https://stackoverflow.com/questions/25346143/why-does-calling-a-js-function-from-onsubmit-clear-my-form-and-console
### HTTP 422 Unprocessable Entity
Happens when endpoint doesn't return any status code

## Resources
https://docs.docker.com/engine/install/ubuntu/
https://www.digitalocean.com/community/tutorials/how-to-create-a-web-server-in-node-js-with-the-http-module
https://fastapi.tiangolo.com/tutorial/sql-databases/
https://www.twilio.com/blog/2017/09/everything-you-ever-wanted-to-know-about-secure.html-forms.html
https://fastapi.tiangolo.com/tutorial/request-forms/

## Potential TODOs
https://fastapi.tiangolo.com/tutorial/sql-databases/
* secure passwords
* Alembic - migration tool for SQLAlchemy

## Worth to read later
https://fastapi.tiangolo.com/tutorial/dependencies/dependencies-with-yield/
