# Design First Development with Apicurio and Microcks

Below are sequence of commands to kick start the orchestration of respective services to get started with Apicurio & Microcks

$ git clone https://github.com/2much2learn/article-rest-api-design-first-development-with-apicurio.git

Replace `<IP_ADDRESS>` in below files with ip address of your host where the services are orchestrated
- .env.template -> save as .env
- config\keycloak
    - apicurio-realm.json.template -> save as apicurio-realm.json
    - microcks-realm.json.template -> save as microcks-realm.json

$ docker-compose build

$ docker-compose up -d

$ docker-compose ps

-- Verify logs to see if services are started successfully

$ docker-compose logs -f jboss-keycloak
$ docker-compose logs -f apicurio-studio-api
$ docker-compose logs -f apicurio-studio-ui

-- Access urls
Keycloak: 
url - http://<IP_ADDRESS>:9090/auth/admin
credentials - admin/admin

Apicurio Studio:
url - http://<IP_ADDRESS>:9093
credentials - Login to Keycloak and create user with email id and credentials under `apicurio` realm

Microcks Administrator: 
url - http://<IP_ADDRESS>:9900
credentials - admin/admin

-- If there is change in env properties, then recreate the services to apply latest changes
$ docker-compose up -d --force-recreate

$ docker-compose stop

$ docker-compose start

-- Cleanup
$ docker-compose down -v

$ docker system prune --volumes