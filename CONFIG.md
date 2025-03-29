# si

![Version: 4.3.0-0](https://img.shields.io/badge/Version-4.3.0--0-informational?style=flat-square) ![AppVersion: 4.3.0](https://img.shields.io/badge/AppVersion-4.3.0-informational?style=flat-square)

A Helm chart for the deployment of WSO2 Streaming Integrator

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| aws.region | string | `""` | AWS region |
| aws.secretManager.secretIdentifiers.internalKeystorePassword.secretKey | string | `""` | Secret key for internal keystore password |
| aws.secretManager.secretIdentifiers.internalKeystorePassword.secretName | string | `""` | Secret name for internal keystore password |
| aws.secretManager.secretProviderClass | string | `""` | AWS Secret Manager secret provider class name |
| aws.serviceAccountName | string | `""` | AWS IAM service account name |
| aws.storage.cAppAccessPoint | string | `""` | EFS file system access point ID for mounting the CApps |
| aws.storage.capacity | string | `""` | Persistent volume storage capacity |
| aws.storage.directoryPerms | string | `"0777"` | Directory permissions for access point root directory creation |
| aws.storage.fileSystemId | string | `""` | EFS file system ID |
| aws.storage.provisioner | string | `"efs.csi.aws.com"` | Storage provisioner |
| aws.storage.storageClass | string | `""` | Persistent volume storage class name |
| azure.keyVault.activeDirectory.servicePrincipal | object | `{"appId":"","clientSecret":""}` | Service Principal created for transacting with the target Azure Key Vault For advanced details refer to official documentation (https://github.com/Azure/secrets-store-csi-driver-provider-azure/blob/master/docs/service-principal-mode.md) |
| azure.keyVault.activeDirectory.servicePrincipal.appId | string | `""` | Azure AD application name for fetching secrets via CSI secret store driver |
| azure.keyVault.activeDirectory.servicePrincipal.clientSecret | string | `""` | Client secret of Azure AD application client |
| azure.keyVault.activeDirectory.tenantId | string | `""` | Azure Active Directory tenant ID of the target Key Vault |
| azure.keyVault.name | string | `""` | Name of the target Azure Key Vault instance |
| azure.keyVault.resourceManager.resourceGroup | string | `""` | Name of the Azure Resource Group to which the target Azure Key Vault belongs |
| azure.keyVault.resourceManager.subscriptionId | string | `""` | Subscription ID of the target Azure Key Vault |
| azure.keyVault.secretIdentifiers.internalKeystorePassword | string | `""` |  |
| azure.keyVault.secretProviderClass | string | `""` |  |
| azure.serviceAccount | string | `""` |  |
| azure.storage.capacity | string | `""` | Persistent volume capacity |
| azure.storage.fileShare | string | `""` | Azure fileshare name |
| azure.storage.secretName | string | `""` | Azure file secret name |
| azure.storage.storageClass | string | `""` | Persistent volume storage class |
| gcp.secretManager.secretIdentifiers.internalKeystorePassword | string | `""` | Secret name for internal keystore password. Expected format is `projects/<PROJECT_ID>/secrets/<SECRET_NAME>/versions/<VERSION>` |
| gcp.secretManager.secretProviderClass | string | `""` | GCP Secret Manager secret provider class name |
| gcp.secretManager.serviceAccountKeySecret | string | `""` | K8s secret name which contains the JSON keyfile for the service account used to access the GCP Secret Manager |
| gcp.storage.capacity | string | `""` | Persistent volume storage capacity |
| gcp.storage.network | string | `""` | Network of the FileStore |
| gcp.storage.storageClass | string | `""` | Persistent volume storage class name |
| gcp.storage.tier | string | `""` |  |
| gcp.storage.volumeAttributes.ip | string | `""` | Pre-provisioned Filestore instance IP |
| gcp.storage.volumeAttributes.volume | string | `""` | Pre-provisioned Filestore instance share name |
| gcp.storage.volumeHandle | string | `""` | Volume handle of the GCP Filestore instance. Format `modeInstance/<zone>/<filestore-instance-name>/<filestore-share-name>` |
| provider | string | `""` | -------------------------------------------------------------------------------------- |
| wso2.config.admin.password | string | `""` | Super admin password |
| wso2.config.admin.username | string | `""` | Super admin username |
| wso2.config.databridge.thrift.sslPort | int | `7711` |  |
| wso2.config.databridge.thrift.tcpPort | int | `7611` |  |
| wso2.config.keyStore.primary.alias | string | `"wso2carbon"` | Primary keystore alias |
| wso2.config.keyStore.primary.fileName | string | `"wso2carbon.jks"` | Primary keystore file name |
| wso2.config.keyStore.primary.keyPassword | string | `""` | Primary keystore key password |
| wso2.config.keyStore.primary.password | string | `""` | Primary keystore password |
| wso2.config.keyStore.secureVault.alias | string | `"wso2carbon"` | Secure vault alias |
| wso2.config.keyStore.secureVault.fileName | string | `"securevault.jks"` | Secure vault file name |
| wso2.config.keyStore.secureVault.keyPassword | string | `""` | Secure vault key password |
| wso2.config.keyStore.secureVault.password | string | `""` | Secure vault password |
| wso2.config.secureVault.enabled | bool | `false` | Enable/Disable secure vault |
| wso2.config.transport.http.default | int | `9090` |  |
| wso2.config.transport.http.msf4jHttps | int | `9443` |  |
| wso2.config.trustStore.primary.fileName | string | `"client-truststore.jks"` | Primary truststore file name |
| wso2.config.trustStore.primary.password | string | `""` | Primary truststore password |
| wso2.deployment.BuildVersion | string | `"4.3.0"` | Build version of the Streaming Integrator |
| wso2.deployment.JKSSecretName | string | `""` | K8s secret name which contains JKS files |
| wso2.deployment.envs | list | `nil` | Environment variables for the Streaming integrator deployment |
| wso2.deployment.hostname | string | `"si.wso2.com"` | Hostname of the Streaming Integrator deployment |
| wso2.deployment.image.containerRegistry | string | `"docker.io"` | Container registry (When running on a local Kubernetes cluster using local image, make this empty) |
| wso2.deployment.image.digest | string | `""` | Container image digest |
| wso2.deployment.image.pullPolicy | string | `"IfNotPresent"` | Container image pull policy. Refer (https://kubernetes.io/docs/concepts/containers/images/#updating-images) |
| wso2.deployment.image.repository | string | `"wso2/wso2si"` | Container image repository name |
| wso2.deployment.image.tag | string | `"4.3.0-ubuntu"` | Container image tag |
| wso2.deployment.imagePullSecrets | string | `""` | imagePullSecrets for private docker registry |
| wso2.deployment.mountSiddhiApps | bool | `false` |  |
| wso2.deployment.probes.livenessProbe.initialDelaySeconds | int | `60` |  |
| wso2.deployment.probes.livenessProbe.periodSeconds | int | `10` |  |
| wso2.deployment.probes.readinessProbe.initialDelaySeconds | int | `60` |  |
| wso2.deployment.probes.readinessProbe.periodSeconds | int | `10` |  |
| wso2.deployment.replicas | int | `1` | Number of deployment replicas |
| wso2.deployment.resources.jvm.memory.xms | string | `"512m"` | The minimum amount of memory that should be allocated for the JVM |
| wso2.deployment.resources.jvm.memory.xmx | string | `"1024m"` | The maximum amount of memory that should be allocated for the JVM |
| wso2.deployment.resources.limits.cpu | string | `"1000m"` | The maximum amount of CPU that should be allocated for a Pod |
| wso2.deployment.resources.limits.memory | string | `"1Gi"` | The maximum amount of memory that should be allocated for a Pod |
| wso2.deployment.resources.requests.cpu | string | `"500m"` | The minimum amount of CPU that should be allocated for a Pod |
| wso2.deployment.resources.requests.memory | string | `"512Mi"` | The minimum amount of memory that should be allocated for a Pod |
| wso2.deployment.securityContext.apparmor | bool | `true` | Enable/Disable AppArmor (https://kubernetes.io/docs/tutorials/security/apparmor/) |
| wso2.deployment.securityContext.runAsUser | string | `""` | The UID to run the entrypoint of the container process |
| wso2.deployment.securityContext.seccompProfile | bool | `true` | Enable/Disable seccomp profile (https://kubernetes.io/docs/tutorials/security/seccomp/) |
| wso2.deployment.strategy.rollingUpdate.maxSurge | int | `1` | The maximum number of pods that can be scheduled above the desired number of pods. |
| wso2.deployment.strategy.rollingUpdate.maxUnavailable | int | `0` | The maximum number of pods that can be unavailable during the update. |
| wso2.ingress.annotations | list | `nil` | Ingress annotations |
| wso2.ingress.backendProtocol | string | `"AUTO_HTTP"` | Controls how the Ingress communicates with backend services |
| wso2.ingress.enabled | bool | `true` | Enable Ingress for SI |
| wso2.ingress.ingressClassName | string | `"nginx"` | Ingress class name |
| wso2.ingress.ratelimit.burstLimit | string | `""` | Ingress ratelimit burst limit |
| wso2.ingress.ratelimit.enabled | bool | `false` | Ingress rate limit |
| wso2.ingress.ratelimit.zoneName | string | `""` | Ingress ratelimit zone name |
| wso2.ingress.sslRedirect | string | `"false"` | Controls how the  redirection of HTTPS if TLS is enabled for that ingress. |
| wso2.ingress.tlsSecret | string | `""` | K8s TLS secret for configured hostname |
| wso2.subscription.password | string | `""` | WSO2 subscription password |
| wso2.subscription.username | string | `""` | WSO2 subscription username |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
