# oathkeeper-maester

![Version: 0.21.7](https://img.shields.io/badge/Version-0.21.7-informational?style=flat-square) ![AppVersion: v0.1.4](https://img.shields.io/badge/AppVersion-v0.1.4-informational?style=flat-square)

A Helm chart for deploying ORY Oathkeeper Rule Controller in Kubernetes

**Homepage:** <https://www.ory.sh/>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| ORY Team | office@ory.sh | https://www.ory.sh/ |

## Source Code

* <https://github.com/ory/oathkeeper>
* <https://github.com/ory/k8s>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Configure node affinity |
| deployment.annotations | object | `{}` | Configure annotations. |
| deployment.automountServiceAccountToken | bool | `true` |  |
| deployment.envs | object | `{}` | Configure environment variables. |
| deployment.nodeSelector | object | `{}` | Node labels for pod assignment. |
| deployment.resources | object | `{}` |  |
| deployment.securityContext.allowPrivilegeEscalation | bool | `false` |  |
| deployment.securityContext.capabilities.drop[0] | string | `"ALL"` |  |
| deployment.securityContext.privileged | bool | `false` |  |
| deployment.securityContext.readOnlyRootFilesystem | bool | `true` |  |
| deployment.securityContext.runAsNonRoot | bool | `true` |  |
| deployment.securityContext.runAsUser | int | `1000` |  |
| deployment.tolerations | list | `[]` | Configure node tolerations. |
| global | object | `{"ory":{"oathkeeper":{"maester":{"mode":"controller"}}}}` | Mode for oathkeeper controller -- Two possible modes are: controller or sidecar |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy |
| image.repository | string | `"oryd/oathkeeper-maester"` | ORY Oathkeeper Rule Controller image |
| image.tag | string | `"v0.1.6"` | ORY Oathkeeper Rule Controller version |
| pdb | object | `{"enabled":false,"spec":{"minAvailable":1}}` | PodDistributionBudget configuration |
| replicaCount | int | `1` | Number of controller replicas in deployment mode |
| rulesConfigmapNamespace | string | `""` |  |
| rulesFileName | string | `""` |  |
| singleNamespaceMode | bool | `false` | Single namespace mode. If enabled the controller will watch for resources only from namespace it is deployed in, ignoring others |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)