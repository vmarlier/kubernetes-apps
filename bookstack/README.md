# [Bookstack](https://github.com/BookStackApp/BookStack)
This manifest is written to work with the managed k8s of the scaleway cloud.

Before applying the manifest:
- Create managed database, define the username, password, and the db name.
- Get the endpoints.
- Update the database user permission to "ALL" for the db created.
- Update the configmap variables at the end of the manifest.

Prequisites:
- A "bookstack" namespace
- A traefik ingress controller
- Create the configmap "config-configmap" from the file ./env:
$ kubectl create configmap config-configmap -n bookstack --from-file=.env=bookstack.env
- Create the configmap "bookstack-configmap" from the file ./db-config:
$ kubectl create configmap bookstack-configmap -n bookstack --from-env-file=db.env
