# k8s-template

This will looking for `arfanrfn/auth` image

running dev: ``skaffold dev``

running without skaffold: ``kubectl apply -f infra/k8s``


## Ingress-nginx
use https://kubernetes.github.io/ingress-nginx/ for ingress setup. If the ingress-nginx doesn't exist. Follow the documentation to install it.

update host file on linux/MacOS
````
sudo vi /etc/hosts
// add <Minikube ip> ingress domain name
// example: 192.168.49.2 ticketing.dev
````
to https bypas use chrome browser and type `thisisunsafe`, then it should work

### fix error on ingress
remove admission from ValidatingWebhookConfiguration to fix *failed calling webhoook*
````
kubectl delete -A ValidatingWebhookConfiguration ingress-nginx-admission
````

