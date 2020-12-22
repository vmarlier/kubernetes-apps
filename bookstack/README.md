Before applying the manifest:
- Create managed database, define the username, password, and the db name.
- Get the endpoints.
- Update the database user permission to "ALL" for the db created.
- Update the configmap variables at the end of the manifest.

Prequisites:
- A "bookstack" namespace

- A traefik ingress controller

- Create the configmap "wbs-bookstack-config-configmap" from the file ./bookstack.env:
$ kubectl create configmap wbs-bookstack-config-configmap -n bookstack --from-file=.env=bookstack.env

- Create the configmap "wbs-bookstack-db-env-configmap" from the file ./db.env:
$ kubectl create configmap wbs-bookstack-db-env-configmap -n bookstack --from-env-file=db.env
