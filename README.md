# redis

![Version: 16.9.2-bb.0](https://img.shields.io/badge/Version-16.9.2--bb.0-informational?style=flat-square) ![AppVersion: 6.2.6](https://img.shields.io/badge/AppVersion-6.2.6-informational?style=flat-square)

Redis(TM) is an open source, advanced key-value store. It is often referred to as a data structure server since keys can contain strings, hashes, lists, sets and sorted sets.

## Upstream References
* <https://github.com/bitnami/charts/tree/master/bitnami/redis>

* <https://github.com/bitnami/bitnami-docker-redis>

## Learn More
* [Application Overview](docs/overview.md)
* [Other Documentation](docs/)

## Pre-Requisites

* Kubernetes Cluster deployed
* Kubernetes config installed in `~/.kube/config`
* Helm installed

Install Helm

https://helm.sh/docs/intro/install/

## Deployment

* Clone down the repository
* cd into directory
```bash
helm install redis chart/
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| hostname | string | `"bigbang.dev"` |  |
| istio.enabled | bool | `false` |  |
| istio.redis.enabled | bool | `false` |  |
| istio.redis.labels | object | `{}` |  |
| istio.redis.annotations | object | `{}` |  |
| istio.redis.gateway.port | int | `15443` |  |
| istio.redis.hosts[0] | string | `"*"` |  |
| monitoring.enabled | bool | `false` |  |
| cleanUpgrade.enabled | bool | `false` |  |
| cleanUpgrade.image | string | `"registry1.dso.mil/ironbank/big-bang/base:1.2.0"` |  |
| cleanUpgrade.resources.requests.memory | string | `"256Mi"` |  |
| cleanUpgrade.resources.requests.cpu | string | `"100m"` |  |
| cleanUpgrade.resources.limits.memory | string | `"256Mi"` |  |
| cleanUpgrade.resources.limits.cpu | string | `"100m"` |  |
| networkPolicies.enabled | bool | `true` |  |
| networkPolicies.controlPlaneCidr | string | `"0.0.0.0/0"` |  |
| global.imageRegistry | string | `""` |  |
| global.imagePullSecrets[0] | string | `"private-registry"` |  |
| global.storageClass | string | `""` |  |
| global.redis.password | string | `""` |  |
| kubeVersion | string | `""` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| commonLabels | object | `{}` |  |
| commonAnnotations | object | `{}` |  |
| secretAnnotations | object | `{}` |  |
| clusterDomain | string | `"cluster.local"` |  |
| extraDeploy | list | `[]` |  |
| diagnosticMode.enabled | bool | `false` |  |
| diagnosticMode.command[0] | string | `"sleep"` |  |
| diagnosticMode.args[0] | string | `"infinity"` |  |
| image.registry | string | `"registry1.dso.mil"` |  |
| image.repository | string | `"ironbank/bitnami/redis"` |  |
| image.tag | string | `"6.2.6"` |  |
| image.pullPolicy | string | `"Always"` |  |
| image.debug | bool | `false` |  |
| architecture | string | `"replication"` |  |
| auth.enabled | bool | `true` |  |
| auth.sentinel | bool | `true` |  |
| auth.password | string | `""` |  |
| auth.existingSecret | string | `""` |  |
| auth.existingSecretPasswordKey | string | `""` |  |
| auth.usePasswordFiles | bool | `false` |  |
| commonConfiguration | string | `"# Enable AOF https://redis.io/topics/persistence#append-only-file\nappendonly yes\n# Disable RDB persistence, AOF persistence already enabled.\nsave \"\""` |  |
| existingConfigmap | string | `""` |  |
| master.configuration | string | `""` |  |
| master.disableCommands[0] | string | `"FLUSHDB"` |  |
| master.disableCommands[1] | string | `"FLUSHALL"` |  |
| master.command | list | `[]` |  |
| master.args | list | `[]` |  |
| master.preExecCmds | list | `[]` |  |
| master.extraFlags | list | `[]` |  |
| master.extraEnvVars | list | `[]` |  |
| master.extraEnvVarsCM | string | `""` |  |
| master.extraEnvVarsSecret | string | `""` |  |
| master.containerPorts.redis | int | `6379` |  |
| master.startupProbe.enabled | bool | `false` |  |
| master.startupProbe.initialDelaySeconds | int | `20` |  |
| master.startupProbe.periodSeconds | int | `5` |  |
| master.startupProbe.timeoutSeconds | int | `5` |  |
| master.startupProbe.successThreshold | int | `1` |  |
| master.startupProbe.failureThreshold | int | `5` |  |
| master.livenessProbe.enabled | bool | `true` |  |
| master.livenessProbe.initialDelaySeconds | int | `20` |  |
| master.livenessProbe.periodSeconds | int | `5` |  |
| master.livenessProbe.timeoutSeconds | int | `5` |  |
| master.livenessProbe.successThreshold | int | `1` |  |
| master.livenessProbe.failureThreshold | int | `5` |  |
| master.readinessProbe.enabled | bool | `true` |  |
| master.readinessProbe.initialDelaySeconds | int | `20` |  |
| master.readinessProbe.periodSeconds | int | `5` |  |
| master.readinessProbe.timeoutSeconds | int | `1` |  |
| master.readinessProbe.successThreshold | int | `1` |  |
| master.readinessProbe.failureThreshold | int | `5` |  |
| master.customStartupProbe | object | `{}` |  |
| master.customLivenessProbe | object | `{}` |  |
| master.customReadinessProbe | object | `{}` |  |
| master.resources.requests.memory | string | `"256Mi"` |  |
| master.resources.requests.cpu | string | `"100m"` |  |
| master.resources.limits.memory | string | `"256Mi"` |  |
| master.resources.limits.cpu | string | `"100m"` |  |
| master.podSecurityContext.enabled | bool | `true` |  |
| master.podSecurityContext.fsGroup | int | `1001` |  |
| master.containerSecurityContext.enabled | bool | `true` |  |
| master.containerSecurityContext.runAsUser | int | `1001` |  |
| master.kind | string | `"StatefulSet"` |  |
| master.schedulerName | string | `""` |  |
| master.updateStrategy.type | string | `"RollingUpdate"` |  |
| master.updateStrategy.rollingUpdate | object | `{}` |  |
| master.priorityClassName | string | `""` |  |
| master.hostAliases | list | `[]` |  |
| master.podLabels | object | `{}` |  |
| master.podAnnotations | object | `{}` |  |
| master.shareProcessNamespace | bool | `false` |  |
| master.podAffinityPreset | string | `""` |  |
| master.podAntiAffinityPreset | string | `"soft"` |  |
| master.nodeAffinityPreset.type | string | `""` |  |
| master.nodeAffinityPreset.key | string | `""` |  |
| master.nodeAffinityPreset.values | list | `[]` |  |
| master.affinity | object | `{}` |  |
| master.nodeSelector | object | `{}` |  |
| master.tolerations | list | `[]` |  |
| master.topologySpreadConstraints | list | `[]` |  |
| master.dnsPolicy | string | `""` |  |
| master.dnsConfig | object | `{}` |  |
| master.lifecycleHooks | object | `{}` |  |
| master.extraVolumes | list | `[]` |  |
| master.extraVolumeMounts | list | `[]` |  |
| master.sidecars | list | `[]` |  |
| master.initContainers | list | `[]` |  |
| master.persistence.enabled | bool | `true` |  |
| master.persistence.medium | string | `""` |  |
| master.persistence.sizeLimit | string | `""` |  |
| master.persistence.path | string | `"/data"` |  |
| master.persistence.subPath | string | `""` |  |
| master.persistence.storageClass | string | `""` |  |
| master.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| master.persistence.size | string | `"8Gi"` |  |
| master.persistence.annotations | object | `{}` |  |
| master.persistence.selector | object | `{}` |  |
| master.persistence.dataSource | object | `{}` |  |
| master.persistence.existingClaim | string | `""` |  |
| master.service.type | string | `"ClusterIP"` |  |
| master.service.ports.redis | int | `6379` |  |
| master.service.nodePorts.redis | string | `""` |  |
| master.service.externalTrafficPolicy | string | `"Cluster"` |  |
| master.service.internalTrafficPolicy | string | `"Cluster"` |  |
| master.service.extraPorts | list | `[]` |  |
| master.service.clusterIP | string | `""` |  |
| master.service.loadBalancerIP | string | `""` |  |
| master.service.loadBalancerSourceRanges | list | `[]` |  |
| master.service.annotations | object | `{}` |  |
| master.terminationGracePeriodSeconds | int | `30` |  |
| replica.replicaCount | int | `3` |  |
| replica.configuration | string | `""` |  |
| replica.disableCommands[0] | string | `"FLUSHDB"` |  |
| replica.disableCommands[1] | string | `"FLUSHALL"` |  |
| replica.command | list | `[]` |  |
| replica.args | list | `[]` |  |
| replica.preExecCmds | list | `[]` |  |
| replica.extraFlags | list | `[]` |  |
| replica.extraEnvVars | list | `[]` |  |
| replica.extraEnvVarsCM | string | `""` |  |
| replica.extraEnvVarsSecret | string | `""` |  |
| replica.externalMaster.enabled | bool | `false` |  |
| replica.externalMaster.host | string | `""` |  |
| replica.externalMaster.port | int | `6379` |  |
| replica.containerPorts.redis | int | `6379` |  |
| replica.startupProbe.enabled | bool | `true` |  |
| replica.startupProbe.initialDelaySeconds | int | `10` |  |
| replica.startupProbe.periodSeconds | int | `10` |  |
| replica.startupProbe.timeoutSeconds | int | `5` |  |
| replica.startupProbe.successThreshold | int | `1` |  |
| replica.startupProbe.failureThreshold | int | `22` |  |
| replica.livenessProbe.enabled | bool | `true` |  |
| replica.livenessProbe.initialDelaySeconds | int | `20` |  |
| replica.livenessProbe.periodSeconds | int | `5` |  |
| replica.livenessProbe.timeoutSeconds | int | `5` |  |
| replica.livenessProbe.successThreshold | int | `1` |  |
| replica.livenessProbe.failureThreshold | int | `5` |  |
| replica.readinessProbe.enabled | bool | `true` |  |
| replica.readinessProbe.initialDelaySeconds | int | `20` |  |
| replica.readinessProbe.periodSeconds | int | `5` |  |
| replica.readinessProbe.timeoutSeconds | int | `1` |  |
| replica.readinessProbe.successThreshold | int | `1` |  |
| replica.readinessProbe.failureThreshold | int | `5` |  |
| replica.customStartupProbe | object | `{}` |  |
| replica.customLivenessProbe | object | `{}` |  |
| replica.customReadinessProbe | object | `{}` |  |
| replica.resources.limits.cpu | string | `"100m"` |  |
| replica.resources.limits.memory | string | `"256Mi"` |  |
| replica.resources.requests.cpu | string | `"100m"` |  |
| replica.resources.requests.memory | string | `"256Mi"` |  |
| replica.podSecurityContext.enabled | bool | `true` |  |
| replica.podSecurityContext.fsGroup | int | `1001` |  |
| replica.containerSecurityContext.enabled | bool | `true` |  |
| replica.containerSecurityContext.runAsUser | int | `1001` |  |
| replica.schedulerName | string | `""` |  |
| replica.updateStrategy.type | string | `"RollingUpdate"` |  |
| replica.updateStrategy.rollingUpdate | object | `{}` |  |
| replica.priorityClassName | string | `""` |  |
| replica.podManagementPolicy | string | `""` |  |
| replica.hostAliases | list | `[]` |  |
| replica.podLabels | object | `{}` |  |
| replica.podAnnotations | object | `{}` |  |
| replica.shareProcessNamespace | bool | `false` |  |
| replica.podAffinityPreset | string | `""` |  |
| replica.podAntiAffinityPreset | string | `"soft"` |  |
| replica.nodeAffinityPreset.type | string | `""` |  |
| replica.nodeAffinityPreset.key | string | `""` |  |
| replica.nodeAffinityPreset.values | list | `[]` |  |
| replica.affinity | object | `{}` |  |
| replica.nodeSelector | object | `{}` |  |
| replica.tolerations | list | `[]` |  |
| replica.topologySpreadConstraints | list | `[]` |  |
| replica.dnsPolicy | string | `""` |  |
| replica.dnsConfig | object | `{}` |  |
| replica.lifecycleHooks | object | `{}` |  |
| replica.extraVolumes | list | `[]` |  |
| replica.extraVolumeMounts | list | `[]` |  |
| replica.sidecars | list | `[]` |  |
| replica.initContainers | list | `[]` |  |
| replica.persistence.enabled | bool | `true` |  |
| replica.persistence.medium | string | `""` |  |
| replica.persistence.sizeLimit | string | `""` |  |
| replica.persistence.path | string | `"/data"` |  |
| replica.persistence.subPath | string | `""` |  |
| replica.persistence.storageClass | string | `""` |  |
| replica.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| replica.persistence.size | string | `"8Gi"` |  |
| replica.persistence.annotations | object | `{}` |  |
| replica.persistence.selector | object | `{}` |  |
| replica.persistence.dataSource | object | `{}` |  |
| replica.service.type | string | `"ClusterIP"` |  |
| replica.service.ports.redis | int | `6379` |  |
| replica.service.nodePorts.redis | string | `""` |  |
| replica.service.externalTrafficPolicy | string | `"Cluster"` |  |
| replica.service.internalTrafficPolicy | string | `"Cluster"` |  |
| replica.service.extraPorts | list | `[]` |  |
| replica.service.clusterIP | string | `""` |  |
| replica.service.loadBalancerIP | string | `""` |  |
| replica.service.loadBalancerSourceRanges | list | `[]` |  |
| replica.service.annotations | object | `{}` |  |
| replica.terminationGracePeriodSeconds | int | `30` |  |
| replica.autoscaling.enabled | bool | `false` |  |
| replica.autoscaling.minReplicas | int | `1` |  |
| replica.autoscaling.maxReplicas | int | `11` |  |
| replica.autoscaling.targetCPU | string | `""` |  |
| replica.autoscaling.targetMemory | string | `""` |  |
| sentinel.enabled | bool | `false` |  |
| sentinel.image.registry | string | `"docker.io"` |  |
| sentinel.image.repository | string | `"bitnami/redis-sentinel"` |  |
| sentinel.image.tag | string | `"6.2.7-debian-10-r0"` |  |
| sentinel.image.pullPolicy | string | `"IfNotPresent"` |  |
| sentinel.image.pullSecrets | list | `[]` |  |
| sentinel.image.debug | bool | `false` |  |
| sentinel.masterSet | string | `"mymaster"` |  |
| sentinel.quorum | int | `2` |  |
| sentinel.getMasterTimeout | int | `220` |  |
| sentinel.automateClusterRecovery | bool | `false` |  |
| sentinel.downAfterMilliseconds | int | `60000` |  |
| sentinel.failoverTimeout | int | `18000` |  |
| sentinel.parallelSyncs | int | `1` |  |
| sentinel.configuration | string | `""` |  |
| sentinel.command | list | `[]` |  |
| sentinel.args | list | `[]` |  |
| sentinel.preExecCmds | list | `[]` |  |
| sentinel.extraEnvVars | list | `[]` |  |
| sentinel.extraEnvVarsCM | string | `""` |  |
| sentinel.extraEnvVarsSecret | string | `""` |  |
| sentinel.externalMaster.enabled | bool | `false` |  |
| sentinel.externalMaster.host | string | `""` |  |
| sentinel.externalMaster.port | int | `6379` |  |
| sentinel.containerPorts.sentinel | int | `26379` |  |
| sentinel.startupProbe.enabled | bool | `true` |  |
| sentinel.startupProbe.initialDelaySeconds | int | `10` |  |
| sentinel.startupProbe.periodSeconds | int | `10` |  |
| sentinel.startupProbe.timeoutSeconds | int | `5` |  |
| sentinel.startupProbe.successThreshold | int | `1` |  |
| sentinel.startupProbe.failureThreshold | int | `22` |  |
| sentinel.livenessProbe.enabled | bool | `true` |  |
| sentinel.livenessProbe.initialDelaySeconds | int | `20` |  |
| sentinel.livenessProbe.periodSeconds | int | `5` |  |
| sentinel.livenessProbe.timeoutSeconds | int | `5` |  |
| sentinel.livenessProbe.successThreshold | int | `1` |  |
| sentinel.livenessProbe.failureThreshold | int | `5` |  |
| sentinel.readinessProbe.enabled | bool | `true` |  |
| sentinel.readinessProbe.initialDelaySeconds | int | `20` |  |
| sentinel.readinessProbe.periodSeconds | int | `5` |  |
| sentinel.readinessProbe.timeoutSeconds | int | `1` |  |
| sentinel.readinessProbe.successThreshold | int | `1` |  |
| sentinel.readinessProbe.failureThreshold | int | `5` |  |
| sentinel.customStartupProbe | object | `{}` |  |
| sentinel.customLivenessProbe | object | `{}` |  |
| sentinel.customReadinessProbe | object | `{}` |  |
| sentinel.persistence.enabled | bool | `false` |  |
| sentinel.persistence.storageClass | string | `""` |  |
| sentinel.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| sentinel.persistence.size | string | `"100Mi"` |  |
| sentinel.persistence.annotations | object | `{}` |  |
| sentinel.persistence.selector | object | `{}` |  |
| sentinel.persistence.dataSource | object | `{}` |  |
| sentinel.resources.requests.memory | string | `"256Mi"` |  |
| sentinel.resources.requests.cpu | string | `"100m"` |  |
| sentinel.resources.limits.memory | string | `"256Mi"` |  |
| sentinel.resources.limits.cpu | string | `"100m"` |  |
| sentinel.containerSecurityContext.enabled | bool | `true` |  |
| sentinel.containerSecurityContext.runAsUser | int | `1001` |  |
| sentinel.lifecycleHooks | object | `{}` |  |
| sentinel.extraVolumes | list | `[]` |  |
| sentinel.extraVolumeMounts | list | `[]` |  |
| sentinel.service.type | string | `"ClusterIP"` |  |
| sentinel.service.ports.redis | int | `6379` |  |
| sentinel.service.ports.sentinel | int | `26379` |  |
| sentinel.service.nodePorts.redis | string | `""` |  |
| sentinel.service.nodePorts.sentinel | string | `""` |  |
| sentinel.service.externalTrafficPolicy | string | `"Cluster"` |  |
| sentinel.service.extraPorts | list | `[]` |  |
| sentinel.service.clusterIP | string | `""` |  |
| sentinel.service.loadBalancerIP | string | `""` |  |
| sentinel.service.loadBalancerSourceRanges | list | `[]` |  |
| sentinel.service.annotations | object | `{}` |  |
| sentinel.terminationGracePeriodSeconds | int | `30` |  |
| networkPolicy.enabled | bool | `false` |  |
| networkPolicy.allowExternal | bool | `true` |  |
| networkPolicy.extraIngress | list | `[]` |  |
| networkPolicy.extraEgress | list | `[]` |  |
| networkPolicy.ingressNSMatchLabels | object | `{}` |  |
| networkPolicy.ingressNSPodMatchLabels | object | `{}` |  |
| podSecurityPolicy.create | bool | `false` |  |
| podSecurityPolicy.enabled | bool | `false` |  |
| rbac.create | bool | `false` |  |
| rbac.rules | list | `[]` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| serviceAccount.automountServiceAccountToken | bool | `true` |  |
| serviceAccount.annotations | object | `{}` |  |
| pdb.create | bool | `false` |  |
| pdb.minAvailable | int | `1` |  |
| pdb.maxUnavailable | string | `""` |  |
| tls.enabled | bool | `false` |  |
| tls.authClients | bool | `true` |  |
| tls.autoGenerated | bool | `false` |  |
| tls.existingSecret | string | `""` |  |
| tls.certificatesSecret | string | `""` |  |
| tls.certFilename | string | `""` |  |
| tls.certKeyFilename | string | `""` |  |
| tls.certCAFilename | string | `""` |  |
| tls.dhParamsFilename | string | `""` |  |
| metrics.enabled | bool | `false` |  |
| metrics.image.registry | string | `"registry1.dso.mil"` |  |
| metrics.image.repository | string | `"ironbank/bitnami/analytics/redis-exporter"` |  |
| metrics.image.tag | string | `"1.35.0"` |  |
| metrics.image.pullPolicy | string | `"Always"` |  |
| metrics.image.pullSecrets | list | `[]` |  |
| metrics.command | list | `[]` |  |
| metrics.redisTargetHost | string | `"localhost"` |  |
| metrics.extraArgs | object | `{}` |  |
| metrics.extraEnvVars | list | `[]` |  |
| metrics.containerSecurityContext.enabled | bool | `true` |  |
| metrics.containerSecurityContext.runAsUser | int | `1001` |  |
| metrics.extraVolumes | list | `[]` |  |
| metrics.extraVolumeMounts | list | `[]` |  |
| metrics.resources.requests.memory | string | `"256Mi"` |  |
| metrics.resources.requests.cpu | string | `"100m"` |  |
| metrics.resources.limits.memory | string | `"256Mi"` |  |
| metrics.resources.limits.cpu | string | `"100m"` |  |
| metrics.podLabels | object | `{}` |  |
| metrics.podAnnotations."prometheus.io/scrape" | string | `"true"` |  |
| metrics.podAnnotations."prometheus.io/port" | string | `"9121"` |  |
| metrics.service.type | string | `"ClusterIP"` |  |
| metrics.service.port | int | `9121` |  |
| metrics.service.externalTrafficPolicy | string | `"Cluster"` |  |
| metrics.service.extraPorts | list | `[]` |  |
| metrics.service.loadBalancerIP | string | `""` |  |
| metrics.service.loadBalancerSourceRanges | list | `[]` |  |
| metrics.service.annotations | object | `{}` |  |
| metrics.sentinel.enabled | bool | `false` |  |
| metrics.sentinel.image.registry | string | `"docker.io"` |  |
| metrics.sentinel.image.repository | string | `"bitnami/redis-sentinel-exporter"` |  |
| metrics.sentinel.image.tag | string | `"1.7.1-debian-10-r122"` |  |
| metrics.sentinel.image.pullPolicy | string | `"IfNotPresent"` |  |
| metrics.sentinel.image.pullSecrets | list | `[]` |  |
| metrics.sentinel.extraArgs | object | `{}` |  |
| metrics.sentinel.containerSecurityContext.enabled | bool | `true` |  |
| metrics.sentinel.containerSecurityContext.runAsUser | int | `1001` |  |
| metrics.sentinel.resources.requests.memory | string | `"256Mi"` |  |
| metrics.sentinel.resources.requests.cpu | string | `"100m"` |  |
| metrics.sentinel.resources.limits.memory | string | `"256Mi"` |  |
| metrics.sentinel.resources.limits.cpu | string | `"100m"` |  |
| metrics.sentinel.service.type | string | `"ClusterIP"` |  |
| metrics.sentinel.service.port | int | `9355` |  |
| metrics.sentinel.service.externalTrafficPolicy | string | `"Cluster"` |  |
| metrics.sentinel.service.loadBalancerIP | string | `""` |  |
| metrics.sentinel.service.loadBalancerSourceRanges | list | `[]` |  |
| metrics.sentinel.service.annotations | object | `{}` |  |
| metrics.serviceMonitor.enabled | bool | `false` |  |
| metrics.serviceMonitor.namespace | string | `"monitoring"` |  |
| metrics.serviceMonitor.selector.prometheus | string | `"kube-prometheus"` |  |
| metrics.serviceMonitor.namespace | string | `""` |  |
| metrics.serviceMonitor.interval | string | `"30s"` |  |
| metrics.serviceMonitor.scrapeTimeout | string | `""` |  |
| metrics.serviceMonitor.relabellings | list | `[]` |  |
| metrics.serviceMonitor.metricRelabelings | list | `[]` |  |
| metrics.serviceMonitor.honorLabels | bool | `false` |  |
| metrics.serviceMonitor.additionalLabels | object | `{}` |  |
| metrics.prometheusRule.enabled | bool | `false` |  |
| metrics.prometheusRule.namespace | string | `""` |  |
| metrics.prometheusRule.additionalLabels | object | `{}` |  |
| metrics.prometheusRule.rules[0].alert | string | `"RedisDown"` |  |
| metrics.prometheusRule.rules[0].expr | string | `"redis_up{service=\"{{ template \"common.names.fullname\" . }}-metrics\"} == 0"` |  |
| metrics.prometheusRule.rules[0].for | string | `"2m"` |  |
| metrics.prometheusRule.rules[0].labels.severity | string | `"error"` |  |
| metrics.prometheusRule.rules[0].annotations.summary | string | `"Redis(TM) instance {{ \"{{ $labels.instance }}\" }} down"` |  |
| metrics.prometheusRule.rules[0].annotations.description | string | `"Redis(TM) instance {{ \"{{ $labels.instance }}\" }} is down"` |  |
| metrics.prometheusRule.rules[1].alert | string | `"RedisMemoryHigh"` |  |
| metrics.prometheusRule.rules[1].expr | string | `"redis_memory_used_bytes{service=\"{{ template \"common.names.fullname\" . }}-metrics\"} * 100 / redis_memory_max_bytes{service=\"{{ template \"common.names.fullname\" . }}-metrics\"} > 90\n"` |  |
| metrics.prometheusRule.rules[1].for | string | `"2m"` |  |
| metrics.prometheusRule.rules[1].labels.severity | string | `"error"` |  |
| metrics.prometheusRule.rules[1].annotations.summary | string | `"Redis(TM) instance {{ \"{{ $labels.instance }}\" }} is using too much memory"` |  |
| metrics.prometheusRule.rules[1].annotations.description | string | `"Redis(TM) instance {{ \"{{ $labels.instance }}\" }} is using {{ \"{{ $value }}\" }}% of its available memory.\n"` |  |
| metrics.prometheusRule.rules[2].alert | string | `"RedisKeyEviction"` |  |
| metrics.prometheusRule.rules[2].expr | string | `"increase(redis_evicted_keys_total{service=\"{{ template \"common.names.fullname\" . }}-metrics\"}[5m]) > 0\n"` |  |
| metrics.prometheusRule.rules[2].for | string | `"1s"` |  |
| metrics.prometheusRule.rules[2].labels.severity | string | `"error"` |  |
| metrics.prometheusRule.rules[2].annotations.summary | string | `"Redis(TM) instance {{ \"{{ $labels.instance }}\" }} has evicted keys"` |  |
| metrics.prometheusRule.rules[2].annotations.description | string | `"Redis(TM) instance {{ \"{{ $labels.instance }}\" }} has evicted {{ \"{{ $value }}\" }} keys in the last 5 minutes.\n"` |  |
| volumePermissions.enabled | bool | `false` |  |
| volumePermissions.image.registry | string | `"docker.io"` |  |
| volumePermissions.image.repository | string | `"bitnami/bitnami-shell"` |  |
| volumePermissions.image.tag | string | `"10-debian-10-r408"` |  |
| volumePermissions.image.pullPolicy | string | `"IfNotPresent"` |  |
| volumePermissions.image.pullSecrets | list | `[]` |  |
| volumePermissions.resources.requests.memory | string | `"256Mi"` |  |
| volumePermissions.resources.requests.cpu | string | `"100m"` |  |
| volumePermissions.resources.limits.memory | string | `"256Mi"` |  |
| volumePermissions.resources.limits.cpu | string | `"100m"` |  |
| volumePermissions.containerSecurityContext.runAsUser | int | `0` |  |
| sysctl.enabled | bool | `false` |  |
| sysctl.image.registry | string | `"docker.io"` |  |
| sysctl.image.repository | string | `"bitnami/bitnami-shell"` |  |
| sysctl.image.tag | string | `"10-debian-10-r408"` |  |
| sysctl.image.pullPolicy | string | `"IfNotPresent"` |  |
| sysctl.image.pullSecrets | list | `[]` |  |
| sysctl.command | list | `[]` |  |
| sysctl.mountHostSys | bool | `false` |  |
| sysctl.resources.requests.memory | string | `"256Mi"` |  |
| sysctl.resources.requests.cpu | string | `"100m"` |  |
| sysctl.resources.limits.memory | string | `"256Mi"` |  |
| sysctl.resources.limits.cpu | string | `"100m"` |  |
| useExternalDNS.enabled | bool | `false` |  |
| useExternalDNS.suffix | string | `""` |  |
| useExternalDNS.annotationKey | string | `"external-dns.alpha.kubernetes.io/"` |  |
| useExternalDNS.additionalAnnotations | object | `{}` |  |

## Contributing

Please see the [contributing guide](./CONTRIBUTING.md) if you are interested in contributing.
