helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update


<!-- helm install istio-base istio/base -n istio-system --set defaultRevision=default -->

helm install istio-base istio/base -n istio-system --create-namespace

helm install istiod istio/istiod -n istio-system --wait

helm install istio-ingress istio/gateway -n istio-ingress --create-namespace --wait

kubectl create ns bookinfo

