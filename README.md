# movies-quarkus-devops

Helm chart for the [movies-quarkus](https://github.com/rh-bcordeir/movies-quarkus) application.

ArgoCD (OpenShift GitOps) syncs this repo onto the cluster. The Tekton pipeline in the application repo bumps `chart/values.yaml` (`image.tag`) on each successful build, which triggers a sync.

## Layout

```
chart/
  Chart.yaml
  values.yaml
  templates/
    deployment.yaml
    service.yaml
    route.yaml
    _helpers.tpl
```

## Manual install (for verification)

```sh
helm template movies-quarkus chart/ | oc apply -f -
```
