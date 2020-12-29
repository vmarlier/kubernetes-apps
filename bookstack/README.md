Before applying the manifest:
- Create managed database, define the username, password, and the db name.
- Get the endpoints.
- Update the database user permission to "ALL" for the db created.
- Update the configmap variables at the end of the manifest.

Prequisites:
- A "bookstack" namespace

- A traefik ingress controller

- Update the configmap in ./bookstack.yml if you want to update the .env file

- Create the configmap "wbs-bookstack-db-env-secret" from the file ./db.env:
$ kubectl create secret generic bookstack-db-env-secret -n bookstack --from-env-file=db.env
