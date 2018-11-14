# kubedeploy

* simple python script that processes a jinja2 template of a kubernetes yaml file
* Advantage over helm is that the user's rbac restrictions are honored
* This is just a proof of concept, we need to decide if we go this way or use helm

Usage: 

```
./kubedeploy -f infrastructure/traefik.yaml \
  -p TRAEFIK_DASHBOARD_DOMAIN=rancher.mydomain.com TRAEFIK_DATA_DIR=/data/traefik \
  | kubectl apply -f -

./kubedeploy -f infrastructure/rancher-server-ingress.yaml \
  -p RANCHER_SERVER_DOMAIN=rancher.mydomain.com \
  | kubectl apply -f -

```

# Other stuff

* possible volume provisioners
  * https://kubernetes.io/blog/2018/04/13/local-persistent-volumes-beta/
  * https://github.com/MaZderMind/hostpath-provisioner
  * https://github.com/torchbox/k8s-hostpath-provisioner
  * https://github.com/monostream/k8s-localflex-provisioner



