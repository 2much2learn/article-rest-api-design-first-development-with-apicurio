# Design First Development with Apicurio and Microcks

Below are sequence of commands to kick start the orchestration of respective services to get started with Apicurio & Microcks

$ git clone 

Replace `<IP_ADDRESS>` in below files with ip address of your host where the services are orchestrated
- .env.template -> save as .env
- config\keycloak
    - apicurio-realm.json.template -> save as apicurio-realm.json
    - microcks-realm.json.template -> save as microcks-realm.json

$ docker-compose build

$ docker-compose up -d

$ docker-compose ps

$ docker-compose logs -f <container_id>

-- If there is change in env properties, then recreate the services to apply latest changes
$ docker-compose up -d --force-recreate

-- Cleanup
$ docker-compose down -v

$ docker system prune --volumes

-- Access urls
Keycloak: 
url - http://<IP_ADDRESS>:9090/auth/admin
credentials - admin/admin

Apicurio Studio:
url - http://<IP_ADDRESS>:9093/
credentials - Login to Keycloak and create user with email id and credentials under `apicurio` realm

Microcks Administrator: 
url - http://<IP_ADDRESS>:9900/
credentials - admin/admin