# redis

![Version: 19.5.5-bb.1](https://img.shields.io/badge/Version-19.5.5--bb.1-informational?style=flat-square) ![AppVersion: 7.2.5](https://img.shields.io/badge/AppVersion-7.2.5-informational?style=flat-square)

Redis(R) is an open source, advanced key-value store. It is often referred to as a data structure server since keys can contain strings, hashes, lists, sets and sorted sets.

## Upstream References
* <https://bitnami.com>

* <https://github.com/bitnami/charts/tree/main/bitnami/redis>

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
| hostname | string | `"dev.bigbang.mil"` |  |
| istio.enabled | bool | `false` |  |
| istio.hardened.enabled | bool | `false` |  |
| istio.hardened.outboundTrafficPolicyMode | string | `"REGISTRY_ONLY"` |  |
| istio.hardened.customServiceEntries | list | `[]` |  |
| istio.hardened.customAuthorizationPolicies | list | `[]` |  |
| istio.redis.enabled | bool | `false` |  |
| istio.redis.labels | object | `{}` |  |
| istio.redis.annotations | object | `{}` |  |
| istio.redis.gateway.port | int | `15443` |  |
| istio.redis.hosts[0] | string | `"*"` |  |
| monitoring.enabled | bool | `false` |  |
| cleanUpgrade.enabled | bool | `false` |  |
| cleanUpgrade.image | string | `"registry1.dso.mil/ironbank/big-bang/base:2.1.0"` |  |
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
| global.compatibility.openshift.adaptSecurityContext | string | `"auto"` |  |
| kubeVersion | string | `""` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| namespaceOverride | string | `""` |  |
| commonLabels | object | `{}` |  |
| commonAnnotations | object | `{}` |  |
| secretAnnotations | object | `{}` |  |
| clusterDomain | string | `"cluster.local"` |  |
| extraDeploy | list | `[]` |  |
| useHostnames | bool | `true` |  |
| nameResolutionThreshold | int | `5` |  |
| nameResolutionTimeout | int | `5` |  |
| diagnosticMode.enabled | bool | `false` |  |
| diagnosticMode.command[0] | string | `"sleep"` |  |
| diagnosticMode.args[0] | string | `"infinity"` |  |
| image.registry | string | `"registry1.dso.mil"` |  |
| image.repository | string | `"ironbank/bitnami/redis"` |  |
| image.tag | string | `"7.2.5"` |  |
| image.digest | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.pullSecrets | list | `[]` |  |
| image.debug | bool | `false` |  |
| architecture | string | `"replication"` |  |
| auth.enabled | bool | `true` |  |
| auth.sentinel | bool | `true` |  |
| auth.password | string | `""` |  |
| auth.existingSecret | string | `""` |  |
| auth.existingSecretPasswordKey | string | `""` |  |
| auth.usePasswordFiles | bool | `false` |  |
| auth.usePasswordFileFromSecret | bool | `true` |  |
| commonConfiguration | string | `"# Enable AOF https://redis.io/topics/persistence#append-only-file\nappendonly yes\n# Disable RDB persistence, AOF persistence already enabled.\nsave \"\""` |  |
| existingConfigmap | string | `""` |  |
| master.count | int | `1` |  |
| master.configuration | string | `""` |  |
| master.disableCommands[0] | string | `"FLUSHDB"` |  |
| master.disableCommands[1] | string | `"FLUSHALL"` |  |
| master.command | list | `[]` |  |
| master.args | list | `[]` |  |
| master.enableServiceLinks | bool | `true` |  |
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
| master.resourcesPreset | string | `"nano"` |  |
| master.resources.requests.memory | string | `"256Mi"` |  |
| master.resources.requests.cpu | string | `"100m"` |  |
| master.resources.limits.memory | string | `"256Mi"` |  |
| master.resources.limits.cpu | string | `"100m"` |  |
| master.podSecurityContext.enabled | bool | `true` |  |
| master.podSecurityContext.fsGroupChangePolicy | string | `"Always"` |  |
| master.podSecurityContext.sysctls | list | `[]` |  |
| master.podSecurityContext.supplementalGroups | list | `[]` |  |
| master.podSecurityContext.fsGroup | int | `1001` |  |
| master.containerSecurityContext.enabled | bool | `true` |  |
| master.containerSecurityContext.seLinuxOptions | object | `{}` |  |
| master.containerSecurityContext.runAsUser | int | `1001` |  |
| master.containerSecurityContext.runAsGroup | int | `1001` |  |
| master.containerSecurityContext.runAsNonRoot | bool | `true` |  |
| master.containerSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| master.containerSecurityContext.readOnlyRootFilesystem | bool | `true` |  |
| master.containerSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| master.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| master.kind | string | `"StatefulSet"` |  |
| master.schedulerName | string | `""` |  |
| master.updateStrategy.type | string | `"RollingUpdate"` |  |
| master.minReadySeconds | int | `0` |  |
| master.priorityClassName | string | `""` |  |
| master.automountServiceAccountToken | bool | `false` |  |
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
| master.persistence.subPathExpr | string | `""` |  |
| master.persistence.storageClass | string | `""` |  |
| master.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| master.persistence.size | string | `"8Gi"` |  |
| master.persistence.annotations | object | `{}` |  |
| master.persistence.labels | object | `{}` |  |
| master.persistence.selector | object | `{}` |  |
| master.persistence.dataSource | object | `{}` |  |
| master.persistence.existingClaim | string | `""` |  |
| master.persistentVolumeClaimRetentionPolicy.enabled | bool | `false` |  |
| master.persistentVolumeClaimRetentionPolicy.whenScaled | string | `"Retain"` |  |
| master.persistentVolumeClaimRetentionPolicy.whenDeleted | string | `"Retain"` |  |
| master.service.type | string | `"ClusterIP"` |  |
| master.service.portNames.redis | string | `"tcp-redis"` |  |
| master.service.ports.redis | int | `6379` |  |
| master.service.nodePorts.redis | string | `""` |  |
| master.service.externalTrafficPolicy | string | `"Cluster"` |  |
| master.service.extraPorts | list | `[]` |  |
| master.service.internalTrafficPolicy | string | `"Cluster"` |  |
| master.service.clusterIP | string | `""` |  |
| master.service.loadBalancerIP | string | `""` |  |
| master.service.loadBalancerClass | string | `""` |  |
| master.service.loadBalancerSourceRanges | list | `[]` |  |
| master.service.externalIPs | list | `[]` |  |
| master.service.annotations | object | `{}` |  |
| master.service.sessionAffinity | string | `"None"` |  |
| master.service.sessionAffinityConfig | object | `{}` |  |
| master.terminationGracePeriodSeconds | int | `30` |  |
| master.serviceAccount.create | bool | `true` |  |
| master.serviceAccount.name | string | `""` |  |
| master.serviceAccount.automountServiceAccountToken | bool | `false` |  |
| master.serviceAccount.annotations | object | `{}` |  |
| master.pdb.create | bool | `true` |  |
| master.pdb.minAvailable | string | `""` |  |
| master.pdb.maxUnavailable | string | `""` |  |
| replica.kind | string | `"StatefulSet"` |  |
| replica.replicaCount | int | `3` |  |
| replica.configuration | string | `""` |  |
| replica.disableCommands[0] | string | `"FLUSHDB"` |  |
| replica.disableCommands[1] | string | `"FLUSHALL"` |  |
| replica.command | list | `[]` |  |
| replica.args | list | `[]` |  |
| replica.enableServiceLinks | bool | `true` |  |
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
| replica.resourcesPreset | string | `"nano"` |  |
| replica.resources.limits.cpu | string | `"100m"` |  |
| replica.resources.limits.memory | string | `"256Mi"` |  |
| replica.resources.requests.cpu | string | `"100m"` |  |
| replica.resources.requests.memory | string | `"256Mi"` |  |
| replica.podSecurityContext.enabled | bool | `true` |  |
| replica.podSecurityContext.fsGroupChangePolicy | string | `"Always"` |  |
| replica.podSecurityContext.sysctls | list | `[]` |  |
| replica.podSecurityContext.supplementalGroups | list | `[]` |  |
| replica.podSecurityContext.fsGroup | int | `1001` |  |
| replica.containerSecurityContext.enabled | bool | `true` |  |
| replica.containerSecurityContext.seLinuxOptions | object | `{}` |  |
| replica.containerSecurityContext.runAsUser | int | `1001` |  |
| replica.containerSecurityContext.runAsGroup | int | `1001` |  |
| replica.containerSecurityContext.runAsNonRoot | bool | `true` |  |
| replica.containerSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| replica.containerSecurityContext.readOnlyRootFilesystem | bool | `true` |  |
| replica.containerSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| replica.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| replica.schedulerName | string | `""` |  |
| replica.updateStrategy.type | string | `"RollingUpdate"` |  |
| replica.minReadySeconds | int | `0` |  |
| replica.priorityClassName | string | `""` |  |
| replica.podManagementPolicy | string | `""` |  |
| replica.automountServiceAccountToken | bool | `false` |  |
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
| replica.persistence.subPathExpr | string | `""` |  |
| replica.persistence.storageClass | string | `""` |  |
| replica.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| replica.persistence.size | string | `"8Gi"` |  |
| replica.persistence.annotations | object | `{}` |  |
| replica.persistence.labels | object | `{}` |  |
| replica.persistence.selector | object | `{}` |  |
| replica.persistence.dataSource | object | `{}` |  |
| replica.persistence.existingClaim | string | `""` |  |
| replica.persistentVolumeClaimRetentionPolicy.enabled | bool | `false` |  |
| replica.persistentVolumeClaimRetentionPolicy.whenScaled | string | `"Retain"` |  |
| replica.persistentVolumeClaimRetentionPolicy.whenDeleted | string | `"Retain"` |  |
| replica.service.type | string | `"ClusterIP"` |  |
| replica.service.ports.redis | int | `6379` |  |
| replica.service.nodePorts.redis | string | `""` |  |
| replica.service.externalTrafficPolicy | string | `"Cluster"` |  |
| replica.service.internalTrafficPolicy | string | `"Cluster"` |  |
| replica.service.extraPorts | list | `[]` |  |
| replica.service.clusterIP | string | `""` |  |
| replica.service.loadBalancerIP | string | `""` |  |
| replica.service.loadBalancerClass | string | `""` |  |
| replica.service.loadBalancerSourceRanges | list | `[]` |  |
| replica.service.annotations | object | `{}` |  |
| replica.service.sessionAffinity | string | `"None"` |  |
| replica.service.sessionAffinityConfig | object | `{}` |  |
| replica.terminationGracePeriodSeconds | int | `30` |  |
| replica.autoscaling.enabled | bool | `true` |  |
| replica.autoscaling.minReplicas | int | `1` |  |
| replica.autoscaling.maxReplicas | int | `11` |  |
| replica.autoscaling.targetCPU | string | `""` |  |
| replica.autoscaling.targetMemory | string | `""` |  |
| replica.serviceAccount.create | bool | `true` |  |
| replica.serviceAccount.name | string | `""` |  |
| replica.serviceAccount.automountServiceAccountToken | bool | `false` |  |
| replica.serviceAccount.annotations | object | `{}` |  |
| replica.pdb.create | bool | `true` |  |
| replica.pdb.minAvailable | string | `""` |  |
| replica.pdb.maxUnavailable | string | `""` |  |
| sentinel.enabled | bool | `false` |  |
| sentinel.image.registry | string | `"docker.io"` |  |
| sentinel.image.repository | string | `"bitnami/redis-sentinel"` |  |
| sentinel.image.tag | string | `"7.2.5-debian-12-r0"` |  |
| sentinel.image.digest | string | `""` |  |
| sentinel.image.pullPolicy | string | `"IfNotPresent"` |  |
| sentinel.image.pullSecrets | list | `[]` |  |
| sentinel.image.debug | bool | `false` |  |
| sentinel.annotations | object | `{}` |  |
| sentinel.masterSet | string | `"mymaster"` |  |
| sentinel.quorum | int | `2` |  |
| sentinel.getMasterTimeout | int | `90` |  |
| sentinel.automateClusterRecovery | bool | `false` |  |
| sentinel.redisShutdownWaitFailover | bool | `true` |  |
| sentinel.downAfterMilliseconds | int | `60000` |  |
| sentinel.failoverTimeout | int | `180000` |  |
| sentinel.parallelSyncs | int | `1` |  |
| sentinel.configuration | string | `""` |  |
| sentinel.command | list | `[]` |  |
| sentinel.args | list | `[]` |  |
| sentinel.enableServiceLinks | bool | `true` |  |
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
| sentinel.livenessProbe.periodSeconds | int | `10` |  |
| sentinel.livenessProbe.timeoutSeconds | int | `5` |  |
| sentinel.livenessProbe.successThreshold | int | `1` |  |
| sentinel.livenessProbe.failureThreshold | int | `6` |  |
| sentinel.readinessProbe.enabled | bool | `true` |  |
| sentinel.readinessProbe.initialDelaySeconds | int | `20` |  |
| sentinel.readinessProbe.periodSeconds | int | `5` |  |
| sentinel.readinessProbe.timeoutSeconds | int | `1` |  |
| sentinel.readinessProbe.successThreshold | int | `1` |  |
| sentinel.readinessProbe.failureThreshold | int | `6` |  |
| sentinel.customStartupProbe | object | `{}` |  |
| sentinel.customLivenessProbe | object | `{}` |  |
| sentinel.customReadinessProbe | object | `{}` |  |
| sentinel.persistence.enabled | bool | `false` |  |
| sentinel.persistence.storageClass | string | `""` |  |
| sentinel.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| sentinel.persistence.size | string | `"100Mi"` |  |
| sentinel.persistence.annotations | object | `{}` |  |
| sentinel.persistence.labels | object | `{}` |  |
| sentinel.persistence.selector | object | `{}` |  |
| sentinel.persistence.dataSource | object | `{}` |  |
| sentinel.persistence.medium | string | `""` |  |
| sentinel.persistence.sizeLimit | string | `""` |  |
| sentinel.persistentVolumeClaimRetentionPolicy.enabled | bool | `false` |  |
| sentinel.persistentVolumeClaimRetentionPolicy.whenScaled | string | `"Retain"` |  |
| sentinel.persistentVolumeClaimRetentionPolicy.whenDeleted | string | `"Retain"` |  |
| sentinel.resourcesPreset | string | `"nano"` |  |
| sentinel.resources.requests.memory | string | `"256Mi"` |  |
| sentinel.resources.requests.cpu | string | `"100m"` |  |
| sentinel.resources.limits.memory | string | `"256Mi"` |  |
| sentinel.resources.limits.cpu | string | `"100m"` |  |
| sentinel.containerSecurityContext.enabled | bool | `true` |  |
| sentinel.containerSecurityContext.seLinuxOptions | object | `{}` |  |
| sentinel.containerSecurityContext.runAsUser | int | `1001` |  |
| sentinel.containerSecurityContext.runAsGroup | int | `1001` |  |
| sentinel.containerSecurityContext.runAsNonRoot | bool | `true` |  |
| sentinel.containerSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| sentinel.containerSecurityContext.readOnlyRootFilesystem | bool | `true` |  |
| sentinel.containerSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| sentinel.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
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
| sentinel.service.createMaster | bool | `false` |  |
| sentinel.service.loadBalancerIP | string | `""` |  |
| sentinel.service.loadBalancerClass | string | `""` |  |
| sentinel.service.loadBalancerSourceRanges | list | `[]` |  |
| sentinel.service.annotations | object | `{}` |  |
| sentinel.service.sessionAffinity | string | `"None"` |  |
| sentinel.service.sessionAffinityConfig | object | `{}` |  |
| sentinel.service.headless.annotations | object | `{}` |  |
| sentinel.masterService.enabled | bool | `false` |  |
| sentinel.masterService.type | string | `"ClusterIP"` |  |
| sentinel.masterService.ports.redis | int | `6379` |  |
| sentinel.masterService.nodePorts.redis | string | `""` |  |
| sentinel.masterService.externalTrafficPolicy | string | `""` |  |
| sentinel.masterService.extraPorts | list | `[]` |  |
| sentinel.masterService.clusterIP | string | `""` |  |
| sentinel.masterService.loadBalancerIP | string | `""` |  |
| sentinel.masterService.loadBalancerClass | string | `""` |  |
| sentinel.masterService.loadBalancerSourceRanges | list | `[]` |  |
| sentinel.masterService.annotations | object | `{}` |  |
| sentinel.masterService.sessionAffinity | string | `"None"` |  |
| sentinel.masterService.sessionAffinityConfig | object | `{}` |  |
| sentinel.terminationGracePeriodSeconds | int | `30` |  |
| serviceBindings.enabled | bool | `false` |  |
| networkPolicy.enabled | bool | `true` |  |
| networkPolicy.allowExternal | bool | `true` |  |
| networkPolicy.allowExternalEgress | bool | `true` |  |
| networkPolicy.extraIngress | list | `[]` |  |
| networkPolicy.extraEgress | list | `[]` |  |
| networkPolicy.ingressNSMatchLabels | object | `{}` |  |
| networkPolicy.ingressNSPodMatchLabels | object | `{}` |  |
| networkPolicy.metrics.allowExternal | bool | `true` |  |
| networkPolicy.metrics.ingressNSMatchLabels | object | `{}` |  |
| networkPolicy.metrics.ingressNSPodMatchLabels | object | `{}` |  |
| podSecurityPolicy.create | bool | `false` |  |
| podSecurityPolicy.enabled | bool | `false` |  |
| rbac.create | bool | `false` |  |
| rbac.rules | list | `[]` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| serviceAccount.automountServiceAccountToken | bool | `false` |  |
| serviceAccount.annotations | object | `{}` |  |
| pdb | object | `{}` |  |
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
| metrics.image.tag | string | `"v1.61.0"` |  |
| metrics.image.digest | string | `""` |  |
| metrics.image.pullPolicy | string | `"IfNotPresent"` |  |
| metrics.image.pullSecrets | list | `[]` |  |
| metrics.containerPorts.http | int | `9121` |  |
| metrics.startupProbe.enabled | bool | `false` |  |
| metrics.startupProbe.initialDelaySeconds | int | `10` |  |
| metrics.startupProbe.periodSeconds | int | `10` |  |
| metrics.startupProbe.timeoutSeconds | int | `5` |  |
| metrics.startupProbe.successThreshold | int | `1` |  |
| metrics.startupProbe.failureThreshold | int | `5` |  |
| metrics.livenessProbe.enabled | bool | `true` |  |
| metrics.livenessProbe.initialDelaySeconds | int | `10` |  |
| metrics.livenessProbe.periodSeconds | int | `10` |  |
| metrics.livenessProbe.timeoutSeconds | int | `5` |  |
| metrics.livenessProbe.successThreshold | int | `1` |  |
| metrics.livenessProbe.failureThreshold | int | `5` |  |
| metrics.readinessProbe.enabled | bool | `true` |  |
| metrics.readinessProbe.initialDelaySeconds | int | `5` |  |
| metrics.readinessProbe.periodSeconds | int | `10` |  |
| metrics.readinessProbe.timeoutSeconds | int | `1` |  |
| metrics.readinessProbe.successThreshold | int | `1` |  |
| metrics.readinessProbe.failureThreshold | int | `3` |  |
| metrics.customStartupProbe | object | `{}` |  |
| metrics.customLivenessProbe | object | `{}` |  |
| metrics.customReadinessProbe | object | `{}` |  |
| metrics.command | list | `[]` |  |
| metrics.redisTargetHost | string | `"localhost"` |  |
| metrics.extraArgs | object | `{}` |  |
| metrics.extraEnvVars | list | `[]` |  |
| metrics.containerSecurityContext.enabled | bool | `true` |  |
| metrics.containerSecurityContext.seLinuxOptions | object | `{}` |  |
| metrics.containerSecurityContext.runAsUser | int | `1001` |  |
| metrics.containerSecurityContext.runAsGroup | int | `1001` |  |
| metrics.containerSecurityContext.runAsNonRoot | bool | `true` |  |
| metrics.containerSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| metrics.containerSecurityContext.readOnlyRootFilesystem | bool | `true` |  |
| metrics.containerSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| metrics.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| metrics.extraVolumes | list | `[]` |  |
| metrics.extraVolumeMounts | list | `[]` |  |
| metrics.resourcesPreset | string | `"nano"` |  |
| metrics.resources.requests.memory | string | `"256Mi"` |  |
| metrics.resources.requests.cpu | string | `"100m"` |  |
| metrics.resources.limits.memory | string | `"256Mi"` |  |
| metrics.resources.limits.cpu | string | `"100m"` |  |
| metrics.podLabels | object | `{}` |  |
| metrics.podAnnotations."prometheus.io/scrape" | string | `"true"` |  |
| metrics.podAnnotations."prometheus.io/port" | string | `"9121"` |  |
| metrics.service.enabled | bool | `true` |  |
| metrics.service.type | string | `"ClusterIP"` |  |
| metrics.service.ports.http | int | `9121` |  |
| metrics.service.externalTrafficPolicy | string | `"Cluster"` |  |
| metrics.service.extraPorts | list | `[]` |  |
| metrics.service.loadBalancerIP | string | `""` |  |
| metrics.service.loadBalancerClass | string | `""` |  |
| metrics.service.loadBalancerSourceRanges | list | `[]` |  |
| metrics.service.annotations | object | `{}` |  |
| metrics.service.clusterIP | string | `""` |  |
| metrics.serviceMonitor.port | string | `"http-metrics"` |  |
| metrics.serviceMonitor.enabled | bool | `false` |  |
| metrics.serviceMonitor.namespace | string | `""` |  |
| metrics.serviceMonitor.interval | string | `"30s"` |  |
| metrics.serviceMonitor.scrapeTimeout | string | `""` |  |
| metrics.serviceMonitor.relabelings | list | `[]` |  |
| metrics.serviceMonitor.relabellings | list | `[]` |  |
| metrics.serviceMonitor.metricRelabelings | list | `[]` |  |
| metrics.serviceMonitor.honorLabels | bool | `false` |  |
| metrics.serviceMonitor.additionalLabels | object | `{}` |  |
| metrics.serviceMonitor.scheme | string | `""` |  |
| metrics.serviceMonitor.tlsConfig | object | `{}` |  |
| metrics.serviceMonitor.podTargetLabels | list | `[]` |  |
| metrics.serviceMonitor.sampleLimit | bool | `false` |  |
| metrics.serviceMonitor.targetLimit | bool | `false` |  |
| metrics.serviceMonitor.additionalEndpoints | list | `[]` |  |
| metrics.podMonitor.port | string | `"metrics"` |  |
| metrics.podMonitor.enabled | bool | `false` |  |
| metrics.podMonitor.namespace | string | `""` |  |
| metrics.podMonitor.interval | string | `"30s"` |  |
| metrics.podMonitor.scrapeTimeout | string | `""` |  |
| metrics.podMonitor.relabelings | list | `[]` |  |
| metrics.podMonitor.relabellings | list | `[]` |  |
| metrics.podMonitor.metricRelabelings | list | `[]` |  |
| metrics.podMonitor.honorLabels | bool | `false` |  |
| metrics.podMonitor.additionalLabels | object | `{}` |  |
| metrics.podMonitor.podTargetLabels | list | `[]` |  |
| metrics.podMonitor.sampleLimit | bool | `false` |  |
| metrics.podMonitor.targetLimit | bool | `false` |  |
| metrics.podMonitor.additionalEndpoints | list | `[]` |  |
| metrics.prometheusRule.enabled | bool | `false` |  |
| metrics.prometheusRule.namespace | string | `""` |  |
| metrics.prometheusRule.additionalLabels | object | `{}` |  |
| metrics.prometheusRule.rules | list | `[]` |  |
| volumePermissions.enabled | bool | `false` |  |
| volumePermissions.image.registry | string | `"docker.io"` |  |
| volumePermissions.image.repository | string | `"bitnami/os-shell"` |  |
| volumePermissions.image.tag | string | `"12-debian-12-r22"` |  |
| volumePermissions.image.digest | string | `""` |  |
| volumePermissions.image.pullPolicy | string | `"IfNotPresent"` |  |
| volumePermissions.image.pullSecrets | list | `[]` |  |
| volumePermissions.resourcesPreset | string | `"nano"` |  |
| volumePermissions.resources.requests.memory | string | `"256Mi"` |  |
| volumePermissions.resources.requests.cpu | string | `"100m"` |  |
| volumePermissions.resources.limits.memory | string | `"256Mi"` |  |
| volumePermissions.resources.limits.cpu | string | `"100m"` |  |
| volumePermissions.containerSecurityContext.seLinuxOptions | object | `{}` |  |
| volumePermissions.containerSecurityContext.runAsUser | int | `0` |  |
| volumePermissions.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| kubectl.enabled | bool | `false` |  |
| kubectl.image.registry | string | `"docker.io"` |  |
| kubectl.image.repository | string | `"bitnami/kubectl"` |  |
| kubectl.image.tag | string | `"1.30.2-debian-12-r0"` |  |
| kubectl.image.digest | string | `""` |  |
| kubectl.image.pullPolicy | string | `"IfNotPresent"` |  |
| kubectl.image.pullSecrets | list | `[]` |  |
| kubectl.command[0] | string | `"/opt/bitnami/scripts/kubectl-scripts/update-master-label.sh"` |  |
| kubectl.containerSecurityContext.enabled | bool | `true` |  |
| kubectl.containerSecurityContext.seLinuxOptions | object | `{}` |  |
| kubectl.containerSecurityContext.runAsUser | int | `1001` |  |
| kubectl.containerSecurityContext.runAsGroup | int | `1001` |  |
| kubectl.containerSecurityContext.runAsNonRoot | bool | `true` |  |
| kubectl.containerSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| kubectl.containerSecurityContext.readOnlyRootFilesystem | bool | `true` |  |
| kubectl.containerSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| kubectl.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| kubectl.resources.limits.memory | string | `"256Mi"` |  |
| kubectl.resources.limits.cpu | string | `"100m"` |  |
| kubectl.resources.requests.memory | string | `"256Mi"` |  |
| kubectl.resources.requests.cpu | string | `"100m"` |  |
| sysctl.enabled | bool | `false` |  |
| sysctl.image.registry | string | `"docker.io"` |  |
| sysctl.image.repository | string | `"bitnami/os-shell"` |  |
| sysctl.image.tag | string | `"12-debian-12-r22"` |  |
| sysctl.image.digest | string | `""` |  |
| sysctl.image.pullPolicy | string | `"IfNotPresent"` |  |
| sysctl.image.pullSecrets | list | `[]` |  |
| sysctl.command | list | `[]` |  |
| sysctl.mountHostSys | bool | `false` |  |
| sysctl.resourcesPreset | string | `"nano"` |  |
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
