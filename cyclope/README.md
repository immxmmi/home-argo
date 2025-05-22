helm repo add cyclops https://cyclops-ui.github.io/helm-charts
helm repo update
helm install cyclops cyclops/cyclops --namespace cyclops --create-namespace


kubectl port-forward svc/cyclops-ui -n cyclops 3000:3000