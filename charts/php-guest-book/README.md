# php-guest-book

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 5.0.0](https://img.shields.io/badge/AppVersion-5.0.0-informational?style=flat-square)

A Helm chart for Kubernetes that deploys the php guest book

## Installing the Chart

Before you can install the chart you will need to add the `sossickd` repo to [Helm](https://helm.sh/).

```shell
helm repo add sossickd https://sossickd.github.io/helm-charts/
```

After you've installed the repo you can install the chart.

```shell
helm upgrade --install --namespace default --values ./my-values.yaml my-release sossickd/php-guest-book
```

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | redis | 15.4.* |

## Configuration

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| affinity | object | `{}` | Affinity for pod assignment. |
| autoscaling.enabled | bool | `false` | If true, create a HPA for the deployment. |
| autoscaling.maxReplicas | int | `100` | Maximum number of pod replicas. |
| autoscaling.minReplicas | int | `1` | Minimum number of pod replicas. |
| autoscaling.targetCPUUtilizationPercentage | int | `80` | Target CPU utilisation for the pod. |
| autoscaling.targetMemoryUtilizationPercentage | int | `80` | Target memory utilisation for the pod. |
| fullnameOverride | string | `""` | Override the fullname of the chart. |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy. |
| image.repository | string | `"gcr.io/google-samples/gb-frontend"` | Image repository. |
| image.tag | string | `"v5"` | Image tag. |
| imagePullSecrets | list | `[]` | Image pull secrets. |
| ingress.annotations | object | `{}` | Ingress annotations. |
| ingress.enabled | bool | `false` | If true, create an ingress object. |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.ingressClassName | string | `""` | Ingress class to use. |
| ingress.tls | list | `[]` | Ingress TLS configuration |
| nameOverride | string | `""` | Override the name of the chart. |
| nodeSelector | object | `{}` | Node labels for pod assignment. |
| podAnnotations | object | `{}` | Annotations to add to the pod. |
| podSecurityContext | object | `{}` | Security context for the pod. |
| redis.auth.enabled | bool | `false` | If `false`, disables redis auth, this is a requiremenrt for the php-guest-book. |
| redis.enabled | bool | `true` | If `true`, deploys redis, this is a requiremenrt for the php-guest-book. |
| redis.master.persistence.enabled | bool | `false` | If `true` enable persistence storage for the redis master. |
| redis.replica.persistence.enabled | bool | `false` | If `true` enable persistence storage for the redis replica. |
| redis.replica.replicaCount | int | `2` | Reddis replica, replica count. |
| replicaCount | int | `1` | Replica count. |
| resources | object | `{}` | Resource requests and limits. |
| securityContext | object | `{}` | Security context for the confluence container. |
| service.port | int | `80` | Service port. |
| service.type | string | `"ClusterIP"` | Service type. |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account. |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created. |
| serviceAccount.name | string | `"frontend"` |  |
| tolerations | list | `[]` | Tolerations for pod assignment. |
