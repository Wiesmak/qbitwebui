# qbitwebui

qbitwebui helm chart

## Installing the Chart

To install the chart with the release name `my-release`:

```bash
helm install my-release . -f values.yaml
```

## Configuration

The following table lists the configurable parameters of the qbitwebui chart and their default values.

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| `replicaCount` | int | `1` | Number of pods to run |
| `image.repository` | string | `"ghcr.io/maciejonos/qbitwebui"` | Container image repository |
| `image.pullPolicy` | string | `"IfNotPresent"` | Container image pull policy |
| `image.tag` | string | `"2.34.0"` | Container image tag |
| `imagePullSecrets` | list | `[]` | Secrets for pulling private images |
| `env` | list | `[PORT:"3000", ...]` | Environment variables passed to the pod (e.g., `PORT`, `DISABLE_AUTH`, `ALLOW_SELF_SIGNED_CERTS`, `DOWNLOADS_PATH`) |
| `existingSecret` | string | `"encryption-key"` | Name of an existing secret containing sensitive configuration/keys |
| `service.web.type` | string | `"ClusterIP"` | Kubernetes service type |
| `service.web.port` | int | `80` | Kubernetes service port |
| `service.web.targetPort` | int | `3000` | Port the container is listening on |
| `ingress.enabled` | bool | `true` | Enable Ingress resource |
| `ingress.className` | string | `""` | Ingress/Route class name |
| `ingress.annotations` | object | `{}` | Additional annotations for the Ingress/Route |
| `ingress.host` | string | `"qbitwebui.example"` | Hostname for the Ingress/Route |
| `resources` | object | `{}` | CPU/Memory resource requests and limits |
| `livenessProbe` | object | `{...}` | Configuration for Liveness probe |
| `readinessProbe` | object | `{...}` | Configuration for Readiness probe |
| `persistence.data.enabled` | bool | `true` | Enable persistence for application data |
| `persistence.data.storageClass` | string | `""` | Storage class for application data PVC |
| `persistence.data.accessMode` | string | `"ReadWriteOnce"` | Access mode for application data PVC |
| `persistence.data.size` | string | `"1Gi"` | Storage size requested for application data |
| `persistence.downloads.enabled` | bool | `true` | Enable persistence for downloads directory |
| `persistence.downloads.existingClaim` | string | `""` | Skip dynamic provisioning and use an existing PVC for downloads |
