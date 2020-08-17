# generator-knative-kustomize-skaffold
Generator for Knative Resources based on Kustomize and Skaffold

If your app depends on a MySQL database, then you must first create a database server instance.

You have two options for this, either using Helm or the Kustomize configuration provided in the `local-services` profile.

Using Kustomize run:

```bash
kubectl create secret generic mysql \
  --from-literal=mysql-root-password=$(echo $RANDOM) \
  --from-literal=mysql-password=$(echo $RANDOM)
skaffold run -p local-services
```

Using Helm v3 run:

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
skaffold run -p local-services-helm
```

Then, to execute the application run:

```bash
skaffold run -p local
```
