# kimbodo-posit-base-resources
Base resources to create a K8s environment by kimbodo with posit tools

| name | type | default | description |
| :---: | :---: | :---: | :--- |
| `.global.namespaces.rstudioConnect` | *string* | `rstudio-connect` | The namespace to create rstudio-connect objects provided by this Helm Chart and `rstudio/rstudio-connect` Helm Chart |
| `.global.namespaces.rstudioWorkbench` | *string* | `rstudio-workbench` | The namespace to create rstudio-workbench objects provided by this Helm Chart and `rstudio/rstudio-workbench` Helm Chart  |
| `.global.namespaces.rstudioPackageManager` | *string* | `rstudio-package-manager` | The namespace to create rstudio-package-manager objects provided by this Helm Chart and `rstudio/rstudio-pm` Helm Chart |
| `.global.namespaces.postgresql` | *string* | `postgresql` | The namespace for PostgreSQL resources |
| `.global.namespaces.nfsServerProvisioner` | *string* | `nfs-server-provisioner` | The namespace for NFS Server Provisioner |
| `.global.wbLicense` | *string (base64)* | `""` | RStudio Workbench license key in base64 format |
| `.global.ctLicense` | *string (base64)* | `""` | RStudio Connect license key in base64 format |
| `.global.clusterIssuer.enabled` | *bool* | `true` | Whether to create the `ClusterIssuer` object |
| `.global.clusterIssuer.name` | *string* | `letsencrypt-prod` | Metadata name of the Let's Encrypt ClusterIssuer |
| `.global.clusterIssuer.email` | *string* | `""` | Email required by Let's Encrypt |
| `.global.clusterIssuer.server` | *string* | `https://acme-v02.api.letsencrypt.org/directory` | Let's Encrypt server URL |
| `.global.clusterIssuer.accountKeySecret` | *string* | `letsencrypt-prod-account-key` | Secret name containing the account key for Let's Encrypt |
| `.global.postgresql.auth.username` | *string* | `""` | Username to be created for PostgreSQL |
| `.global.postgresql.auth.password` | *string* | `""` | Password for the PostgreSQL user |
| `.global.postgresql.auth.database` | *string* | `""` | Database to be created on first execution |
| `.global.cloudProvider` | *string* | `GCP` | The cloud provider to deploy to (`AWS`, `GCP`, or `AZURE`) |
| `.global.httpsResolver.enabled` | *bool* | `true` | Whether to generate a TLS key/cert using a resolver |
| `.global.httpsResolver.api` | *string* | `LETSENCRYPT` | API to use for generating TLS certificates (`LETSENCRYPT` or `BUYPASS`) |
| `.rstudio-connect.fullnameOverride` | *string* | `rstudio-connect` | Custom name override for RStudio Connect release |
| `.rstudio-connect.hpa.minReplicas` | *int* | `1` | Minimum number of pods for RStudio Connect autoscaling |
| `.rstudio-connect.hpa.maxReplicas` | *int* | `5` | Maximum number of pods for RStudio Connect autoscaling |
| `.rstudio-workbench.fullnameOverride` | *string* | `rstudio-workbench` | Custom name override for RStudio Workbench release |
| `.rstudio-workbench.hpa.minReplicas` | *int* | `1` | Minimum number of pods for RStudio Workbench autoscaling |
| `.rstudio-workbench.hpa.maxReplicas` | *int* | `5` | Maximum number of pods for RStudio Workbench autoscaling |
| `.rstudio-pm.fullnameOverride` | *string* | `rstudio-package-manager` | Custom name override for RStudio Package Manager release |
| `.rstudio-pm.hpa.minReplicas` | *int* | `1` | Minimum number of pods for RStudio Package Manager autoscaling |
| `.rstudio-pm.hpa.maxReplicas` | *int* | `5` | Maximum number of pods for RStudio Package Manager autoscaling |
| `.global.rbac.users` | *list* | `[]` | List of users with access roles for this cluster |
| `.global.rbac.users[].name` | *string* | `""` | The user email or ID. For GCP, must be the Google Account used to access the cluster |
| `.global.rbac.users[].role` | *string* | `""` | The role assigned to the user. Valid options: `viewer`, `editor`, `admin` |