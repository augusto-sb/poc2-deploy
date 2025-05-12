# Project

this project is a BE/FE app with Keycloak as SSO and MongoDB for storage using Go and Angular

### This small repo clonse the other repos of the project, builds the containers and deploys everything.

* You only need Docker for this!

# Run With:

```bash
bash script.sh
```

# READ
this keycloak imports a realm that has client secrets and users. ONLY FOR TESTING, DO NOT USE IN PRODUCTION;

# Admin keycloak cli

/opt/keycloak/bin/kcadm.sh config credentials --user $KC_BOOTSTRAP_ADMIN_USERNAME --password $KC_BOOTSTRAP_ADMIN_PASSWORD --server http://localhost:8080/auth --realm master
/opt/keycloak/bin/kcadm.sh set-password -r poc --username test --new-password test
/opt/keycloak/bin/kcadm.sh create users -r poc -s username=test -s enabled=true

# Info
https://www.keycloak.org/server/importExport
https://www.keycloak.org/server/all-config
https://www.keycloak.org/server/reverseproxy
https://github.com/little-pinecone/keycloak-in-docker/blob/master/keycloak/realms/realm-export.json

this creates a reverse proxy with Nginx for a unique entrypoint
a keycloak with a realm, public and private clients, and two users common and super with differen roles for testing
and deploys the front and back configuring it