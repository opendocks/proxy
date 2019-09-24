## OpenDock Proxy

The is based on  [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy). All credits goes to the MAN :)

This will setup service for auto handling of reverse proxy, this also uses [jrcs/letsencrypt-nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion) to automate SSL certificates.

### How to use for project
- Clone this [opendock/o-proxy](https://github.com/opendock/o-proxy) repository using command 
```bash
    git clone git@github.com:opendock/o-proxy.git
```
- Create `certs` sub directory

- Create `vhost.d` sub directory

- Create docker network using command

- Create docker network using command
```bash
    docker network create net1-nginx-proxy
```

- You need to specify VIRTUAL_HOST & VIRTUAL_PORT as environment for apache service to handle reverse proxy. 

- You need to specify LETSENCRYPT_HOST & LETSENCRYPT_EMAIL as environment for apache service, to handle SSL certificates.

    - BONUS, If you are using [opendock/o-template](https://github.com/opendock/o-template) with this project, you just need to update .env file for APACHE_VIRTUAL_HOST & APACHE_HTTP_PORT variable and provide in apache service asbelow.
    
        ```yaml
        environment:
              VIRTUAL_HOST: ${APACHE_VIRTUAL_HOST}
              VIRTUAL_PORT: ${APACHE_HTTP_PORT}
              LETSENCRYPT_HOST: ${APACHE_VIRTUAL_HOST}
              LETSENCRYPT_EMAIL: example@email.com
        ```
      
- Run service
```bash
    docker-compose up
```

- Enjoy :)


