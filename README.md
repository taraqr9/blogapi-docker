# Blogapi Docker
This project is a core system of Blogapi Web.

### Docker Services
- nginx
- app
- database

If you do not have docker installed please install `docker` and `docker-compose` first.

## Requirements
- Docker
- Docker Compose


## Installation
Clone the project from github and go to the project and run these commands.

```shell
chmod +x ./blogapi
```

After, run this command and go to sleep.

```shell
./blogapi ready
```
To show all the running process, run the command below

```shell
docker-compose ps
```
To stop all the services, run the command

```shell
docker-compose down
```
