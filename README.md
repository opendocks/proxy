## Docker Proxy Network

The is based on  [jwilder/docker-gen](https://github.com/jwilder/docker-gen). All credits goes to the MAN :)

### How to use for project
- Clone this repo using command 
```bash
    git clone git@github.com:smurtazakazmi/dock.p.git
```

- Create docker network using command
```bash
    docker network create nginx-proxy
```

- You need to specify VIRTUAL_HOST as environment for apache service, if you are using [Docker Site](https://github.com/smurtazakazmi/dock.s) with this project, you just need to update .env file for APACHE_VIRTUAL_HOST variable.

- Enjoy :)
