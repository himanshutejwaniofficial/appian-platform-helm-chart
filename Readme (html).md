::: typora-export-content
::: {#write}
# Appian Platform (CS) Helm Chart

A Helm chart for deploying the Appian platform on Kubernetes. This Helm
chart is supplied by Appian Customer Success via the Appian App Market.

This chart deploys a custom resource of type `appian` that is managed by
the [Appian
Operator](https://docs.appian.com/suite/help/latest/k8s/what-is-appian-operator.html).

## Introduction

This chart facilitates the deployment of Appian sites through templated
support for common options while baking-in best practice configurations.

## Prerequisites

-   [Deployment
    prerequisites](https://docs.appian.com/suite/help/latest/k8s/install-appian-on-k8s.html#prerequisites)

-   [Appian
    operator](https://docs.appian.com/suite/help/latest/k8s/install-appian-on-k8s.html#1-install-the-appian-operator)

The Config Generator tool from [Appian Kubernetes
Utilities](https://community.appian.com/b/appmarket/posts/appian-kubernetes-utilities),
available from the Appian App Market, can help you prepare these
prerequisites.

## Usage

### Review templated custom resource specification

Want to see what custom resource specification your values file would
produce? You can preview your Appian custom resource manifest by
preparing your values file and running the following:

``` {.md-fences .md-end-block .ty-contain-cm .modeLoaded spellcheck="false" lang="console"}
helm template -f values.yaml appian-platform-cs-$CHART_VERSION.tgz > appian-site.yaml
```
:::
:::

::: {style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 23px;"}
:::

::: {.CodeMirror-gutters style="display: none; height: 23px;"}
:::

> Note: You need to substitute the placeholder `CHART_VERSION` with the
> version of chart you are using. A YAML file that specifies the values
> for the parameters must be provided (e.g. `values.yaml`).

Or if you have already deployed the chart to your Helm repository:

``` {.md-fences .md-end-block .ty-contain-cm .modeLoaded spellcheck="false" lang="console"}
xxxxxxxxxx
```

::: CodeMirror-measure
:::

::: {style="position: relative; z-index: 1;"}
:::

::: {.CodeMirror-code role="presentation"}
::: {.CodeMirror-activeline style="position: relative;"}
::: {.CodeMirror-activeline-background .CodeMirror-linebackground}
:::

::: {.CodeMirror-gutter-background .CodeMirror-activeline-gutter style="left: 0px; width: 0px;"}
:::

``` {.CodeMirror-line role="presentation"}
helm template -f values.yaml oci://$REGISTRY_NAME/$REPOSITORY_NAME/appian-platform-cs --version $CHART_VERSION > appian-site.yaml
```
:::
:::

::: {style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 46px;"}
:::

::: {.CodeMirror-gutters style="display: none; height: 46px;"}
:::

> Note: You need to substitute the placeholders `REGISTRY_NAME` and
> `REPOSITORY_NAME` with a reference to your Helm chart registry and
> repository. A YAML file that specifies the values for the parameters
> must be provided (e.g. `values.yaml`).

### Deploying or restarting the Appian site (Installing the chart)

To install the chart with the release name `$SITE_NAME`:

``` {.md-fences .md-end-block .ty-contain-cm .modeLoaded spellcheck="false" lang="console"}
xxxxxxxxxx
```

::: CodeMirror-measure
:::

::: {style="position: relative; z-index: 1;"}
:::

::: {.CodeMirror-code role="presentation"}
::: {.CodeMirror-activeline style="position: relative;"}
::: {.CodeMirror-activeline-background .CodeMirror-linebackground}
:::

::: {.CodeMirror-gutter-background .CodeMirror-activeline-gutter style="left: 0px; width: 0px;"}
:::

``` {.CodeMirror-line role="presentation"}
helm install $SITE_NAME --namespace appian -f values.yaml --wait oci://$REGISTRY_NAME/$REPOSITORY_NAME/appian-platform-cs --version $CHART_VERSION
```
:::
:::

::: {style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 46px;"}
:::

::: {.CodeMirror-gutters style="display: none; height: 46px;"}
:::

> Note: You need to substitute the placeholders `REGISTRY_NAME` and
> `REPOSITORY_NAME` with a reference to your Helm chart registry and
> repository. A YAML file that specifies the values for the parameters
> must be provided (e.g. `values.yaml`) while installing the chart.

### Stopping the Appian site (Deleting the chart)

To stop the Appian site with the release name `$SITE_NAME`:

``` {.md-fences .md-end-block .ty-contain-cm .modeLoaded spellcheck="false" lang="console"}
xxxxxxxxxx
```

::: CodeMirror-measure
:::

::: {style="position: relative; z-index: 1;"}
:::

::: {.CodeMirror-code role="presentation"}
::: {.CodeMirror-activeline style="position: relative;"}
::: {.CodeMirror-activeline-background .CodeMirror-linebackground}
:::

::: {.CodeMirror-gutter-background .CodeMirror-activeline-gutter style="left: 0px; width: 0px;"}
:::

``` {.CodeMirror-line role="presentation"}
helm uninstall $SITE_NAME --namespace appian
```
:::
:::

::: {style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 23px;"}
:::

::: {.CodeMirror-gutters style="display: none; height: 23px;"}
:::

This will not delete the Persistent Volume Claims nor the associated
RDBMS and as such leaves the site\'s data in place ready for when the
site is next started again.

### Upgrading or hotfixing the Appian site

To upgrade the Appian site to a new major version, or to hoftix the site
with newer container images for the same major version:

1.  [Stop the Appian
    site](\#stopping-the-appian-site-deleting-the-chart) (Ensure the
    site stops cleanly with all checkpoints completed).

2.  Update the value of `url` in your values file to reference your new
    target version

3.  [Start the Appian
    site](\#deploying-or-restarting-the-appian-site-installing-the-chart)

Ensure you check the [operator release
notes](https://docs.appian.com/suite/help/latest/k8s/release-notes.html)
and [platform release
notes](https://docs.appian.com/suite/help/latest/Appian_Release_Notes.html)
before upgrading an Appian site and provision the relevant container
images and Operator Helm chart in your container registry.

### Upgrading this Helm chart

To upgrade to a later version of this Helm chart, ensure you check the
[Release Notes](#release-notes) for any changes. Before upgrading, use
the `helm template` command to compare the output generated by the new
version of the chart with your existing configuration.

## Example values files

This section provides some sample values files illustrating certain
configuration options.

> Note: These few examples are not exhaustive and do not represent all
> possible configurations.

### Example 1 - Non-HA, MariaDB, AWS Load Balancer

Spec overview:

-   Non-HA

-   class \"small\"

-   MariaDB primary data source

-   AWS Load Balancer ingress, with SSL configured via an AWS
    certificate

-   Container registry authenticated via images.pullSecrets

``` {.md-fences .md-end-block .ty-contain-cm .modeLoaded spellcheck="false" lang="yaml" style="break-inside: unset;"}
xxxxxxxxxx
```

::: CodeMirror-measure
:::

::: {style="position: relative; z-index: 1;"}
:::

::: {.CodeMirror-code role="presentation" style=""}
::: {.CodeMirror-activeline style="position: relative;"}
::: {.CodeMirror-activeline-background .CodeMirror-linebackground}
:::

::: {.CodeMirror-gutter-background .CodeMirror-activeline-gutter style="left: 0px; width: 0px;"}
:::

``` {.CodeMirror-line role="presentation"}
siteName: company-proj-dev
```
:::

``` {.CodeMirror-line role="presentation"}
version: "24.3.100.0"
```

``` {.CodeMirror-line role="presentation"}
url: https://proj-dev.company.com
```

``` {.CodeMirror-line role="presentation"}
staticUrl: https://proj-dev.company-static.com
```

``` {.CodeMirror-line role="presentation"}
dynamicUrl: https://proj-dev.company-dynamic.com
```

``` {.CodeMirror-line role="presentation"}
class: small
```

``` {.CodeMirror-line role="presentation"}
# Non-HA
```

``` {.CodeMirror-line role="presentation"}
highAvailability: false
```

``` {.CodeMirror-line role="presentation"}
passwordsPropertiesSecretName: "passwords-properties"
```

``` {.CodeMirror-line role="presentation"}
license:
```

``` {.CodeMirror-line role="presentation"}
  k3SecretName: "k3lic"
```

``` {.CodeMirror-line role="presentation"}
  k4SecretName: "k4lic"
```

``` {.CodeMirror-line role="presentation"}
  appianConfigMapName: "appian-lic"
```

``` {.CodeMirror-line role="presentation"}
storage:
```

``` {.CodeMirror-line role="presentation"}
  rwoStorageClassName: "my-ebs-sc"
```

``` {.CodeMirror-line role="presentation"}
  sharedLogsPvc: "appian-shared-logs-pvc"
```

``` {.CodeMirror-line role="presentation"}
images:
```

``` {.CodeMirror-line role="presentation"}
  pullSecrets:
```

``` {.CodeMirror-line role="presentation"}
    - regcred
```

``` {.CodeMirror-line role="presentation"}
  appian:
```

``` {.CodeMirror-line role="presentation"}
    repository: "my.container.registry.com/appian"
```

``` {.CodeMirror-line role="presentation"}
  minimal:
```

``` {.CodeMirror-line role="presentation"}
    repository: alpine
```

``` {.CodeMirror-line role="presentation"}
    tag: "3.18.0"
```

``` {.CodeMirror-line role="presentation"}
smtp:
```

``` {.CodeMirror-line role="presentation"}
  senderAddress: "my_from_address@my_domain.com"
```

``` {.CodeMirror-line role="presentation"}
  senderDomain: "my_domain.com"
```

``` {.CodeMirror-line role="presentation"}
  host: "my.smtp.server.smtp.com"
```

``` {.CodeMirror-line role="presentation"}
  auth: true
```

``` {.CodeMirror-line role="presentation"}
  user: "my_user_name"
```

``` {.CodeMirror-line role="presentation"}
  protocol: "smtp"
```

``` {.CodeMirror-line role="presentation"}
  starttlsEnabled: false
```

``` {.CodeMirror-line role="presentation"}
  starttlsRequired: false
```

``` {.CodeMirror-line role="presentation"}
dataSources:
```

``` {.CodeMirror-line role="presentation"}
  # MariaDB primary data source
```

``` {.CodeMirror-line role="presentation"}
  primary:
```

``` {.CodeMirror-line role="presentation"}
    name: jdbc/AppianPrimary
```

``` {.CodeMirror-line role="presentation"}
    dbType: mariadb
```

``` {.CodeMirror-line role="presentation"}
    dbServerAndPort: my.database.server.com:3306
```

``` {.CodeMirror-line role="presentation"}
    schemaName: "appian_primary"
```

``` {.CodeMirror-line role="presentation"}
    usernameSecretKeyRef:
```

``` {.CodeMirror-line role="presentation"}
      name: "appian-primary-ds"
```

``` {.CodeMirror-line role="presentation"}
      key: "username"
```

``` {.CodeMirror-line role="presentation"}
    passwordSecretKeyRef:
```

``` {.CodeMirror-line role="presentation"}
      name: "appian-primary-ds"
```

``` {.CodeMirror-line role="presentation"}
      key: "password"
```

``` {.CodeMirror-line role="presentation"}
ingressTemplate:
```

``` {.CodeMirror-line role="presentation"}
  # AWS Load Balancer ingress
```

``` {.CodeMirror-line role="presentation"}
  name: alb
```

``` {.CodeMirror-line role="presentation"}
  # SSL configured via an AWS certificate
```

``` {.CodeMirror-line role="presentation"}
  certificateReference: "my-cert-arn"
```
:::

::: {style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 1175px;"}
:::

::: {.CodeMirror-gutters style="display: none; height: 1175px;"}
:::

### Example 2 - HA, MySQL, NGINX

Spec overview:

-   HA

-   class \"medium\"

-   MySQL primary and one business data source

-   NGINX ingress, with SSL configured via TLS field

-   Node selector targeting dedicated Appian node group

-   Kafka storage size (set by class template) overridden

-   Data Service class upscaled to \"large\"

-   Self-managed monitoring metrics API enabled

``` {.md-fences .md-end-block .ty-contain-cm .modeLoaded spellcheck="false" lang="yaml" style="break-inside: unset;"}
xxxxxxxxxx
```

::: CodeMirror-measure
:::

::: {style="position: relative; z-index: 1;"}
:::

::: {.CodeMirror-code role="presentation" style=""}
::: {.CodeMirror-activeline style="position: relative;"}
::: {.CodeMirror-activeline-background .CodeMirror-linebackground}
:::

::: {.CodeMirror-gutter-background .CodeMirror-activeline-gutter style="left: 0px; width: 0px;"}
:::

``` {.CodeMirror-line role="presentation"}
siteName: company-proj-dev
```
:::

``` {.CodeMirror-line role="presentation"}
version: "24.3.100.0"
```

``` {.CodeMirror-line role="presentation"}
url: https://proj-dev.company.com
```

``` {.CodeMirror-line role="presentation"}
staticUrl: https://proj-dev.company-static.com
```

``` {.CodeMirror-line role="presentation"}
dynamicUrl: https://proj-dev.company-dynamic.com
```

``` {.CodeMirror-line role="presentation"}
class: medium
```

``` {.CodeMirror-line role="presentation"}
# HA
```

``` {.CodeMirror-line role="presentation"}
highAvailability: true
```

``` {.CodeMirror-line role="presentation"}
passwordsPropertiesSecretName: "passwords-properties"
```

``` {.CodeMirror-line role="presentation"}
# Self-Managed Monitoring Metrics API
```

``` {.CodeMirror-line role="presentation"}
metricsAuthToken: "bW9uaXRvcmluZw=="
```

``` {.CodeMirror-line role="presentation"}
# Node selector targeting dedicated Appian node group
```

``` {.CodeMirror-line role="presentation"}
nodeSelector:
```

``` {.CodeMirror-line role="presentation"}
  my-node-group-label-key: my-node-group-label-value
```

``` {.CodeMirror-line role="presentation"}
license:
```

``` {.CodeMirror-line role="presentation"}
  k3SecretName: "k3lic"
```

``` {.CodeMirror-line role="presentation"}
  k4SecretName: "k4lic"
```

``` {.CodeMirror-line role="presentation"}
  appianConfigMapName: "appian-lic"
```

``` {.CodeMirror-line role="presentation"}
storage:
```

``` {.CodeMirror-line role="presentation"}
  rwoStorageClassName: "my-rwo-sc"
```

``` {.CodeMirror-line role="presentation"}
  sharedLogsPvc: "appian-shared-logs-pvc"
```

``` {.CodeMirror-line role="presentation"}
  haSharedDataPvc: "appian-shared-data-pvc"
```

``` {.CodeMirror-line role="presentation"}
images:
```

``` {.CodeMirror-line role="presentation"}
  appian:
```

``` {.CodeMirror-line role="presentation"}
    repository: "my.container.registry.com/appian"
```

``` {.CodeMirror-line role="presentation"}
  minimal:
```

``` {.CodeMirror-line role="presentation"}
    repository: alpine
```

``` {.CodeMirror-line role="presentation"}
    tag: "3.18.0"
```

``` {.CodeMirror-line role="presentation"}
smtp:
```

``` {.CodeMirror-line role="presentation"}
  senderAddress: "my_from_address@my_domain.com"
```

``` {.CodeMirror-line role="presentation"}
  senderDomain: "my_domain.com"
```

``` {.CodeMirror-line role="presentation"}
  host: "my.smtp.server.smtp.com"
```

``` {.CodeMirror-line role="presentation"}
  auth: true
```

``` {.CodeMirror-line role="presentation"}
  user: "my_user_name"
```

``` {.CodeMirror-line role="presentation"}
  protocol: "smtp"
```

``` {.CodeMirror-line role="presentation"}
  starttlsEnabled: false
```

``` {.CodeMirror-line role="presentation"}
  starttlsRequired: false
```

``` {.CodeMirror-line role="presentation"}
dataSources:
```

``` {.CodeMirror-line role="presentation"}
  # MySQL primary
```

``` {.CodeMirror-line role="presentation"}
  primary:
```

``` {.CodeMirror-line role="presentation"}
    name: jdbc/AppianPrimary
```

``` {.CodeMirror-line role="presentation"}
    dbType: mysql
```

``` {.CodeMirror-line role="presentation"}
    dbServerAndPort: my.database.server.com:3306
```

``` {.CodeMirror-line role="presentation"}
    schemaName: "appian_primary"
```

``` {.CodeMirror-line role="presentation"}
    usernameSecretKeyRef:
```

``` {.CodeMirror-line role="presentation"}
      name: "appian-primary-ds"
```

``` {.CodeMirror-line role="presentation"}
      key: "username"
```

``` {.CodeMirror-line role="presentation"}
    passwordSecretKeyRef:
```

``` {.CodeMirror-line role="presentation"}
      name: "password-secret-appian-primary-ds"
```

``` {.CodeMirror-line role="presentation"}
      key: "password"
```

``` {.CodeMirror-line role="presentation"}
  # one business data source
```

``` {.CodeMirror-line role="presentation"}
  business:
```

``` {.CodeMirror-line role="presentation"}
    - name: jdbc/Appian
```

``` {.CodeMirror-line role="presentation"}
      dbType: mysql
```

``` {.CodeMirror-line role="presentation"}
      dbServerAndPort: my.database.server.com:3306
```

``` {.CodeMirror-line role="presentation"}
      schemaName: "appian"
```

``` {.CodeMirror-line role="presentation"}
      usernameSecretKeyRef:
```

``` {.CodeMirror-line role="presentation"}
    name: "appian-business-ds"
```

``` {.CodeMirror-line role="presentation"}
        key: "username"
```

``` {.CodeMirror-line role="presentation"}
      passwordSecretKeyRef:
```

``` {.CodeMirror-line role="presentation"}
        name: "appian-business-ds"
```

``` {.CodeMirror-line role="presentation"}
        key: "password"
```

``` {.CodeMirror-line role="presentation"}
ingressTemplate:
```

``` {.CodeMirror-line role="presentation"}
  # NGINX ingress
```

``` {.CodeMirror-line role="presentation"}
  name: nginx
```

``` {.CodeMirror-line role="presentation"}
  # SSL configured via TLS field
```

``` {.CodeMirror-line role="presentation"}
  tls:
```

``` {.CodeMirror-line role="presentation"}
    - hosts:
```

``` {.CodeMirror-line role="presentation"}
        - proj-dev.company.com
```

``` {.CodeMirror-line role="presentation"}
        - proj-dev.company-static.com
```

``` {.CodeMirror-line role="presentation"}
        - proj-dev.company-dynamic.com
```

``` {.CodeMirror-line role="presentation"}
      secretName: appian-ingress-tls-secret
```

``` {.CodeMirror-line role="presentation"}
# Kafka storage size (set by class template) overridden
```

``` {.CodeMirror-line role="presentation"}
kafka:
```

``` {.CodeMirror-line role="presentation"}
  storageSize: "60Gi"
```

``` {.CodeMirror-line role="presentation"}
dataServer:
```

``` {.CodeMirror-line role="presentation"}
  class: "large"
```
:::

::: {style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 1775px;"}
:::

::: {.CodeMirror-gutters style="display: none; height: 1775px;"}
:::

## Limitations

A number of fields in the Custom Resource are immutable. These must not
be modified for a running site, so any Helm upgrades to the chart must
avoid changing these values. To be able to change these immutable
fields, the Appian site needs to be stopped (by [deleting the
chart](#stopping-the-appian-site-deleting-the-chart)) and restarted (by
[installing the
chart](#deploying-or-restarting-the-appian-site-installing-the-chart)
with updated values).

As `version` is one of these immutable fields, Appian hotfixes and major
version upgrades cannot be applied using `helm upgrade` and require the
site to be stopped and restarted as above.

## T-Shirt Sizing

This Helm chart uses a `class` parameter to apply default values for a
range of size- and scaling-related parameters, which can then be
fine-tuned using [component-level
overrides](#per-component-overrides-and-additional-parameters). An
appropriate t-shirt size should be chosen as a starting configuration.
Performance testing should be used to determine whether to change class
or, alternatively, to override certain parameters set by class
templates.

> For example, a site with higher process throughput may require larger
> Kafka storage and additional resources for just the execution
> engines - which can be achieved by overriding just those parameters,
> while all other relevant parameters are left as set by the chosen
> class.

The table below provides very rough guidelines for each class, including
the expected resources required to run each size.

<figure class="table-figure">
<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Class</span></th>
<th><span>Purpose</span></th>
<th><span>Resources Required (Non-HA)</span></th>
<th><span>Resources Required (HA)</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>x-small</code></td>
<td><span>Development or Single Application</span></td>
<td><span>8 CPU / 64 GB RAM</span><br />
<span>115 GB RWO</span><br />
<span>100 GB RWX (Logs)</span></td>
<td><span>CPU / RAM x3</span><br />
<span>186 GB RWO</span><br />
<span>200 GB RWX (Logs) / 100 GB RWX (Data)</span></td>
</tr>
<tr class="even">
<td><code>small</code></td>
<td><span>Development or Single Application</span></td>
<td><span>16 CPU / 128 GB RAM</span><br />
<span>115 GB RWO</span><br />
<span>100 GB RWX (Logs)</span></td>
<td><span>CPU / RAM x3</span><br />
<span>186 GB RWO</span><br />
<span>200 GB RWX (Logs) / 100 GB RWX (Data)</span></td>
</tr>
<tr class="odd">
<td><code>medium</code></td>
<td><span>Departmental adoption</span></td>
<td><span>24 CPU / 192 GB RAM</span><br />
<span>150 GB RWO</span><br />
<span>150 GB RWX (Logs)</span></td>
<td><span>CPU / RAM x3</span><br />
<span>291 GB RWO</span><br />
<span>300 GB RWX (Logs) / 200 GB RWX (Data)</span></td>
</tr>
<tr class="even">
<td><code>large</code></td>
<td><span>Enterprise adoption</span></td>
<td><span>48 CPU / 384 GB RAM</span><br />
<span>210 GB RWO</span><br />
<span>200 GB (Logs)</span></td>
<td><span>CPU / RAM x3</span><br />
<span>342 GB RWO</span><br />
<span>400 GB RWX (Logs) / 300 GB RWX (Data)</span></td>
</tr>
<tr class="odd">
<td><code>x-large</code></td>
<td><span>Enterprise adoption</span></td>
<td><span>64 CPU / 512 GB RAM</span><br />
<span>210 GB RWO</span><br />
<span>200 GB (Logs)</span></td>
<td><span>CPU / RAM x3</span><br />
<span>342 GB RWO</span><br />
<span>400 GB RWX (Logs) / 300 GB RWX (Data)</span></td>
</tr>
</tbody>
</table>
</figure>

*Assumes 3 Exec/Analytics shards without RPA or AI. Initial sizing only.
Performance testing / observation and resource request / compute
right-sizing is required.*

## Parameters

### General parameters

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>siteName</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Appian site name. Must match the wildcard pattern of the
licenses provided. See </span><a
href="https://docs.appian.com/suite/help/latest/k8s/install-appian-on-k8s.html#request-licenses"><span>request
licenses</span></a><span>. </span><strong><span>This field is
immutable.</span></strong></td>
<td><span>true</span></td>
<td><code>metadata.name</code></td>
</tr>
<tr class="even">
<td><code>version</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The Low-Code Platform (LCP) version. This field will be
required in a future release. </span><strong><span>This field is
immutable.</span></strong></td>
<td><span>true</span></td>
<td><code>spec.version</code></td>
</tr>
<tr class="odd">
<td><code>url</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The scheme, host, and, optionally, port used to access Appian
(e.g. </span><code>https://appian.example.com</code><span>,
</span><code>http://appian.example.com:32767</code><span>, etc).
</span><em><span>For sites with a single Webapp replica, updating this
field requires restarting Webapp's pod.</span></em></td>
<td><span>true</span></td>
<td><code>spec.url</code></td>
</tr>
<tr class="even">
<td><code>staticUrl</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The scheme, host, and, optionally, port for Appian's static
content URL (e.g.
</span><code>https://appian.example-static.com</code><span>,
</span><code>http://appian.example-static.com:32767</code><span>, etc).
The scheme must be the same as that defined in
</span><code>spec.url</code><span>. Must use a different domain from
</span><code>spec.url</code><span> and
</span><code>dynamicUrl</code><span>. </span><em><span>For sites with a
single Webapp replica, updating this field requires restarting Webapp's
pod.</span></em><span> See </span><a
href="https://docs.appian.com/suite/help/latest/Post-Install_Configurations.html#configure-your-static-and-dynamic-content-urls"><span>Configure
Your Static and Dynamic Content URLs</span></a><span> for more
info.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp.staticUrl</code></td>
</tr>
<tr class="odd">
<td><code>dynamicUrl</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The scheme, host, and, optionally, port for Appian's dynamic
content URL (e.g.
</span><code>https://appian.example-dynamic.com</code><span>,
</span><code>http://appian.example-dynamic.com:32767</code><span>, etc).
The scheme must be the same as that defined in
</span><code>spec.url</code><span>. Must use a different domain from
</span><code>spec.url</code><span> and
</span><code>staticUrl</code><span>. </span><em><span>For sites with a
single Webapp replica, updating this field requires restarting Webapp's
pod.</span></em><span> See </span><a
href="https://docs.appian.com/suite/help/latest/Post-Install_Configurations.html#configure-your-static-and-dynamic-content-urls"><span>Configure
Your Static and Dynamic Content URLs</span></a><span> for more
info.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp.dynamicUrl</code></td>
</tr>
<tr class="even">
<td><code>class</code></td>
<td><span>enum</span></td>
<td><code>""</code></td>
<td><span>One of </span><code>"x-small", "small"</code><span>,
</span><code>"medium"</code><span>,
</span><code>"large", "x-large"</code><span>.</span><br />
<span>Changing </span><code>class</code><span> after an initial
deployment will not automatically affect all sizings driven by it (e.g.
disk volume sizes will not change). </span><strong><span>This field is
immutable.</span></strong><br />
<span>See </span><a
href="#t-shirt-sizing"><span>class</span></a><span>.</span></td>
<td><span>true</span></td>
<td><span>Multiple fields across all components.</span></td>
</tr>
<tr class="odd">
<td><code>enableCpuLimits</code></td>
<td><span>bool</span></td>
<td><code>false</code></td>
<td><span>Determines whether to apply CPU limits to pods. By default, no
CPU limits are set. Setting this field to </span><code>true</code><span>
will apply the class's defaults for each pod type, unless overridden by
</span><code>defaultCpuLimits</code><span> or
</span><code>[component].resources.limits.cpu</code><span>. When CPU
limits are enabled (when
</span><code>enableCpuLimits: true</code><span>), the order of
precedence for each component is 1. Component-level CPU limits override,
2. Global </span><code>defaultCpuLimits</code><span>, 3. Class CPU
limits.</span></td>
<td><span>false</span></td>
<td><code>spec.[component]</code><br />
<code>.resources.limits.cpu</code></td>
</tr>
<tr class="even">
<td><code>defaultCpuLimits</code></td>
<td><span>int or string</span></td>
<td><code>nil</code></td>
<td><span>Default CPU limits to set if not disabling CPU limits and not
using the built-in class's CPU limits. Only applied if
</span><code>enableCpuLimits: true</code><span>. Can be overridden for a
specific component by setting
</span><code>[component].resources.limits.cpu</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.[component]</code><br />
<code>.resources.limits.cpu</code></td>
</tr>
<tr class="odd">
<td><code>enableResourceRequests</code></td>
<td><span>bool</span></td>
<td><code>true</code></td>
<td><span>When set to </span><code>false</code><span> this sets CPU and
Memory resource requests to </span><code>0</code><span> for each
component. Overrides all other configurations for these
fields.</span><br />
<span>Only used when running on small, dedicated worker nodes. Must be
used in conjunction with </span><code>nodeSelector</code><span> (see
</span><a href="#t-shirt-sizing"><span>T-Shirt
Sizing</span></a><span>).</span></td>
<td><span>false</span></td>
<td><code>spec.[component]</code><br />
<code>.resources.requests.cpu</code><br />
<code>spec.[component]</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="even">
<td><code>highAvailability</code></td>
<td><span>bool</span></td>
<td><code>false</code></td>
<td><span>Determines whether the environment will be deployed in a High
Availability (HA) configuration.</span><br />
<span>Changing </span><code>highAvailability</code><span> after an
initial deployment will not automatically change the topology of the
site. </span><strong><span>This field is immutable.</span></strong></td>
<td><span>false</span></td>
<td><span>Multiple fields across all components.</span></td>
</tr>
<tr class="odd">
<td><code>passwordsPropertiesSecretName</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Name of an existing secret containing Appian's
</span><code>passwords.properties</code><span> file. </span><br />
<span>If using an authenticated SMTP server, the file should contain
</span><code>conf.password.SMTP=$YOUR_SMTP_PASSWORD_HERE</code><span>
</span><br />
<em><span>For sites with a single Webapp replica, updating this field
requires restarting Webapp's pod.</span></em></td>
<td><span>false</span><br />
<strong><span>Required when</span></strong><span>
</span><code>smtp.auth</code><span>
</span><strong><span>is</span></strong><span>
</span><code>true</code><strong><span>.</span></strong></td>
<td><code>spec.webapp</code><br />
<code>.passwordsPropertiesSecretName</code></td>
</tr>
<tr class="even">
<td><code>metricsAuthToken</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Base64 encoded password for authenticating to the Appian
self-managed monitoring metrics API. Setting this field automatically
sets two custom properties: </span><code>metricsauthtoken</code><span>
(to this value) and
</span><code>appian.feature.selfManagedMonitoring</code><span> (to
</span><code>true</code><span>). See </span><a
href="https://gitlab.com/appian-oss/self-managed-monitoring"><span>Self-Managed
Monitoring</span></a><span> for details of this solution.</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="odd">
<td><code>additionalCustomProperties</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Additional custom properties in addition to </span><a
href="#managed-custom-properties"><span>those set by the chart
automatically</span></a><span>. See </span><a
href="https://docs.appian.com/suite/help/latest/Custom_Configurations.html#custom-properties"><span>Custom
Properties</span></a><span> for more info. Note: Do not set any custom
properties here that are set by this chart by default. Doing so will
result in duplicate entries for that property under
</span><code>spec.customProperties</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="even">
<td><code>nodeSelector</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>A selector which must be true for the components' pod(s) to
fit on a node. See </span><a
href="https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#nodeselector"><span>nodeSelector</span></a><span>
for more info. Can be overridden for a specific component by setting
</span><code>[component].nodeSelector</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.[component]</code><br />
<code>.nodeSelector</code></td>
</tr>
<tr class="odd">
<td><code>securityContext</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Container-level security context applied to all components.
Passthrough to </span><a
href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#securitycontext-v1-core"><code>corev1.SecurityContext</code></a><span>.
See </span><a
href="https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1securitycontext"><span>securityContext</span></a><span>
for more info. Can be overridden for a specific component by setting
</span><code>[component].securityContext</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.[component]</code><br />
<code>.securityContext</code></td>
</tr>
<tr class="even">
<td><code>podSecurityContext</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Pod-level security context applied to all components.
Passthrough to </span><a
href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#podsecuritycontext-v1-core"><code>corev1.PodSecurityContext</code></a><span>.
Requires Appian Operator v0.200.0+. Can be overridden for a specific
component by setting
</span><code>[component].podSecurityContext</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.[component]</code><br />
<code>.podSecurityContext</code></td>
</tr>
<tr class="odd">
<td><code>rbac</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Configuration for creating RBAC resources.</span></td>
<td><span>false</span></td>
<td><code>spec.rbac</code></td>
</tr>
<tr class="even">
<td><code>networkPolicies</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Configuration for creating network policy
resources.</span></td>
<td><span>false</span></td>
<td><code>spec.networkPolicies</code></td>
</tr>
<tr class="odd">
<td><code>additionalLabels</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Additional labels for created objects - including pods.
</span><em><span>For stateful components with a single replica, updating
this field requires restarting the component's pod.</span></em></td>
<td><span>false</span></td>
<td><code>spec.additionalLabels</code></td>
</tr>
<tr class="even">
<td><code>cascadeVersionToComponentTags</code></td>
<td><span>bool</span></td>
<td><code>false</code></td>
<td><span>Whether to set </span><code>[component].image.tag</code><span>
to the value of </span><code>version</code><span>. Only required if
using the Appian Migration Tool, which enforces that
</span><code>{component}.image.tag</code><span> is present.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].image.tag</code></td>
</tr>
</tbody>
</table>
</figure>

### License parameters

<figure class="table-figure">
<table>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>license.k3SecretName</code></td>
<td><span>string</span></td>
<td><code>"k3lic"</code></td>
<td><span>Name of the existing secret containing the
</span><code>k3.lic</code><span> file. Defaults to
</span><code>k3lic</code><span>. </span><em><span>For sites with a
single replica of service-manager, updating this field requires
restarting all service-manager pods.</span></em></td>
<td><span>true</span></td>
<td><code>spec.k3LicSecretName</code></td>
</tr>
<tr class="even">
<td><code>license.k4SecretName</code></td>
<td><span>string</span></td>
<td><code>"k4lic"</code></td>
<td><span>Name of the existing secret containing the
</span><code>k4.lic</code><span> file. Defaults to
</span><code>k4lic</code><span>. </span><em><span>For sites with a
single Data Service replica, updating this field requires restarting
Data Service's pod.</span></em></td>
<td><span>true</span></td>
<td><code>spec.k4LicSecretName</code></td>
</tr>
<tr class="odd">
<td><code>appianConfigMapName</code></td>
<td><span>string</span></td>
<td><code>"appian-lic"</code></td>
<td><span>Name of the existing config map containing the
</span><code>appian.lic</code><span> file.</span></td>
<td><span>true</span></td>
<td><code>spec.appianLicConfigMapName</code></td>
</tr>
</tbody>
</table>
</figure>

### Storage parameters

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>storage.rwoStorageClassName</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Name of an existing Storage Class for provisioning
ReadWriteOnce (RWO) storage for the Appian stateful pods.</span><br />
<span>Changing </span><code>rwoStorageClassName</code><span> after an
initial deployment will not automatically change the storage class of
the provisioned RWO volumes.</span></td>
<td><span>true</span></td>
<td><code>spec.[component]</code><br />
<code>.volumeClaimTemplateSpec.storageClassName</code></td>
</tr>
<tr class="even">
<td><code>storage.sharedLogsPvc</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Name of an existing ReadWriteMany (RWX) persistent volume
claim to be used for Appian shared logs (aka </span><a
href="https://docs.appian.com/suite/help/latest/health-check.html"><span>Health
Check</span></a><span>) storage. Must differ from
</span><code>haSharedDataPvc</code><span>. </span><strong><span>This
field is immutable.</span></strong><span> See </span><a
href="https://kubernetes.io/docs/concepts/storage/persistent-volumes/"><span>Persistent
Volumes</span></a><span> for more info.</span></td>
<td><span>false</span><br />
<span>[Not required but strongly recommended for all
environments]</span></td>
<td><code>spec.webapp.healthCheckExistingClaim</code></td>
</tr>
<tr class="odd">
<td><code>storage.haSharedDataPvc</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Name of an existing ReadWriteMany (RWX) persistent volume
claim to be used for shared data. Must differ from
</span><code>sharedLogsPvc</code><span>. Required for HA environments.
For non-HA environments that may be converted to HA in future, setting
this field from the start (in addition to
</span><code>storage.sharedLogsPvc</code><span>) makes it easier to
convert the environment. This field cannot be set
</span><em><span>after</span></em><span> initial creation of an
environment without manual data copy operations!
</span><strong><span>This field is immutable.</span></strong><span> See
</span><a
href="https://kubernetes.io/docs/concepts/storage/persistent-volumes/"><span>Persistent
Volumes</span></a><span> for more info.</span></td>
<td><span>false</span><br />
<strong><span>Required when</span></strong><span>
</span><code>highAvailability</code><span>
</span><strong><span>is</span></strong><span>
</span><code>true</code><strong><span>.</span></strong></td>
<td><code>spec.webapp.haExistingClaim</code><span>,
</span><code>spec.serviceManager.haExistingClaim</code></td>
</tr>
</tbody>
</table>
</figure>

### Images parameters

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>images.pullSecrets</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>Names of existing image pull secrets. See </span><a
href="https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/"><span>Pull
an Image from a Private Registry</span></a><span> for more
info.</span></td>
<td><span>false</span></td>
<td><code>spec.imagePullSecrets</code></td>
</tr>
<tr class="even">
<td><code>images.appian.repository</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The URL to which </span><code>/[component]</code><span> can be
added to reference each of the Appian component container images (e.g.
</span><code>my.container.registry.com/appian</code><span>)</span></td>
<td><span>true</span></td>
<td><code>spec.[component]</code><br />
<code>.image.repository</code></td>
</tr>
<tr class="odd">
<td><code>images.minimal.repository</code></td>
<td><span>string</span></td>
<td><code>busybox</code></td>
<td><span>The path to the minimal container image to use where required.
This should be the full image path (e.g.
</span><code>my.container.registry.com/alpine</code><span> or
</span><code>busybox</code><span>). Required if not disabling the
built-in Search Server init container (via
</span><code>searchServer.setVmMaxMapCount: false</code><span>).</span></td>
<td><span>false</span></td>
<td><span>Any init containers configured by the chart (e.g. Search
Server vm max map count init container)</span></td>
</tr>
<tr class="even">
<td><code>images.minimal.tag</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The tag to use for the minimal image. Required if not
disabling the built-in Search Server init container (via
</span><code>searchServer.setVmMaxMapCount: false</code><span>).</span></td>
<td><span>false</span></td>
<td><span>Any init containers configured by the chart (e.g. Search
Server vm max map count init container)</span></td>
</tr>
</tbody>
</table>
</figure>

### SMTP parameters

<figure class="table-figure">
<table>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>smtp.senderAddress</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The address that will appear as the sender (the "From"
address) of notification and password reset emails from the
system</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="even">
<td><code>smtp.senderDomain</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The domain (portion after the "@") for the "from" email
address for addresses created via expressions functions; also applies to
the domain for alert emails when the custom property
</span><code>conf.mailhandler.ntf_sndr_addr</code><span> is not
set</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="odd">
<td><code>smtp.host</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The host is the FQDN, hostname, or IP address of the SMTP
server for sending email from the system. Muliple SMTP servers can be
specified using a comma-separated list. They will be tried in the order
specified. If a port other than 25 is required, append it to the
hostname (e.g. </span><code>mailhost3:9025</code><span>). If this is not
set, no email will be sent from the system. The Helm chart will not add
SMTP-related custom properties if </span><code>smtp.host</code><span> is
not set.</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="even">
<td><code>smtp.auth</code></td>
<td><span>bool</span></td>
<td><code>false</code></td>
<td><span>Set to </span><code>true</code><span> if user/password
authentication to the SMTP server is used. Leave the default
(</span><code>false</code><span>) to indicate that the SMTP server does
not require authentication. If multiple SMTP servers are defined above,
the same auth settings will apply to all servers</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="odd">
<td><code>smtp.user</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The username used to connect to the SMTP server</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="even">
<td><code>smtp.protocol</code></td>
<td><span>string</span></td>
<td><code>"smtp"</code></td>
<td><span>The protocol should be set to either
</span><code>smtp</code><span> or
</span><code>smtps</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="odd">
<td><code>smtp.starttlsEnabled</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>You can enable or require STARTTLS with the
</span><code>smtp</code><span> protocol. Setting
</span><code>smtp.starttlsEnabled</code><span> to
</span><code>true</code><span> will cause outgoing mail to use STARTTLS
if supported by the remote server, but will fall back to plain smtp
otherwise</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="even">
<td><code>smtp.starttlsRequired</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Setting </span><code>smtp.starttlsRequired</code><span> to
</span><code>true</code><span> will cause mail to fail if the remote
server does not support STARTTLS</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
</tbody>
</table>
</figure>

### Data Sources parameters

The `datasources` field allows primary and business data sources to be
configured with ease via built-in templates for each [supported
RDBMS](https://docs.appian.com/suite/help/latest/System_Requirements.html#databases).

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>dataSources.primary</code></td>
<td><a href="#primary-data-source-parameters"><span>Data Source
Template</span></a><span> object</span></td>
<td><code>{}</code></td>
<td><span>The data source for the Appian primary database. See </span><a
href="#data-source-template-parameters"><span>Data Source Template
parameters</span></a><span>. Ignored if
</span><code>webapp.dataSources</code><span> is provided!</span></td>
<td><span>true</span></td>
<td><code>spec.webapp</code><br />
<code>.dataSources.primary</code></td>
</tr>
<tr class="even">
<td><code>dataSources.business</code></td>
<td><a href="#primary-data-source-parameters"><span>Data Source
Template</span></a><span> list</span></td>
<td><code>[]</code></td>
<td><span>Optional business data sources. List of </span><a
href="#data-source-template-parameters"><span>Data Source
Template</span></a><span>. Ignored if
</span><code>webapp.dataSources</code><span> is provided!</span></td>
<td><span>false</span></td>
<td><code>spec.webapp</code><br />
<code>.dataSources.primary</code></td>
</tr>
</tbody>
</table>
</figure>

#### Data Source Template parameters

The following parameters are available for `dataSources.primary` and for
each item in the list `dataSources.business`. The chart\'s Data Source
Templates make it simpler to apply the correct configurations for each
data source with fewer, simpler parameters to be configured.

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>name</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The JNDI name for the data source (e.g.
</span><code>jdbc/AppianPrimary</code><span>).</span></td>
<td><span>true</span></td>
<td><code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].name</code></td>
</tr>
<tr class="even">
<td><code>dbType</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>One of </span><code>"mariadb"</code><span>,
</span><code>"mysql"</code><span>,
</span><code>"mysql-aurora"</code><span>,
</span><code>"oracle"</code><span>, </span><code>"mssql"</code><span>,
</span><code>"postgresql"</code><span>,
</span><code>"postgresql-aurora"</code><span>,
</span><code>"db2"</code><span>.</span></td>
<td><span>true</span></td>
<td><code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].driverClassName</code><br />
<code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].url</code></td>
</tr>
<tr class="odd">
<td><code>dbServerAndPort</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The server and port for the target database (e.g.
</span><code>my.database.com:3306</code><span>).</span></td>
<td><span>true</span></td>
<td><code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].url</code><span> or </span><br />
<code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].url</code></td>
</tr>
<tr class="even">
<td><code>schemaName</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The schema name for the target database. For Oracle this is
the service name. For MS SQL this is the database name. E.g.
</span><code>appian_primary</code></td>
<td><span>true</span></td>
<td><code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].url</code><span> or </span><br />
<code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].url</code></td>
</tr>
<tr class="odd">
<td><code>urlParameters</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>A string of appropriately separated connection string query
parameters.</span><br />
<span>For MySQL and MariaDB do not include
</span><code>useOldAliasMetadataBehavior</code><span> (this is prepended
by the chart).</span><br />
<span>For MSSQL do not include </span><code>databaseName</code><span> or
</span><code>socketTimeout</code><span> (these are prepended by the
chart).</span><br />
<span>Do not include leading </span><code>?</code><span>,
</span><code>;</code><span> or </span><code>&amp;</code><span> at the
start.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].url</code><span> or </span><br />
<code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].url</code></td>
</tr>
<tr class="even">
<td><code>usernameSecretKeyRef.name</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Name of an existing secret holding the username used to
connect to the data source (e.g.
</span><code>appian-primary-ds</code><span>).</span></td>
<td><span>true</span></td>
<td><code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].usernameSecretKeyRef.name</code></td>
</tr>
<tr class="odd">
<td><code>usernameSecretKeyRef.key</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Key within the existing secret
</span><code>dataSources.primary.usernameSecretKeyRef.name</code><span>
holding the username used to connect to the data source (e.g.
</span><code>username</code><span>).</span></td>
<td><span>true</span></td>
<td><code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].usernameSecretKeyRef.key</code></td>
</tr>
<tr class="even">
<td><code>passwordSecretKeyRef.name</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Name of an existing secret holding the password used to
connect to the data source (e.g.
</span><code>appian-primary-ds</code><span>).</span></td>
<td><span>true</span></td>
<td><code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].passwordSecretKeyRef.name</code></td>
</tr>
<tr class="odd">
<td><code>passwordSecretKeyRef.key</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Key within the existing secret
</span><code>dataSources.primary.passwordSecretKeyRef.name</code><span>
holding the password used to connect to the data source (e.g.
</span><code>password</code><span>).</span></td>
<td><span>true</span></td>
<td><code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].passwordSecretKeyRef.key</code></td>
</tr>
<tr class="even">
<td><code>attributes</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Optionally replaces the default set of attributes in
</span><code>spec.webapp.dataSources.[primary/business.[]].attributes</code><span>.
If not provided, the chart applies the default set of attributes as
defined in </span><a
href="https://docs.appian.com/suite/help/latest/Configuring_Relational_Databases.html#provide-data-source-connection-information"><span>Configuring
Relational Databases</span></a><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp.dataSources</code><br />
<code>.[primary/business.[]].attributes</code></td>
</tr>
</tbody>
</table>
</figure>

### Ingress Template parameters

The `ingressTemplate` field allows an ingress to be configured with ease
via built-in templates for 4 popular ingress controllers: [NGINX Ingress
Controller](https://docs.nginx.com/nginx-ingress-controller/), [AWS Load
Balancer
Controller](https://kubernetes-sigs.github.io/aws-load-balancer-controller),
[Azure Application Gateway Ingress Controller
(AGIC)](https://learn.microsoft.com/en-us/azure/application-gateway/ingress-controller-overview)
and [OpenShift Default ingress
controller](https://github.com/openshift/cluster-ingress-operator).
These templates apply standard annotations required for each ingress
class.

If you are using another ingress controller, configure this using
[Ingress](#ingress) instead.

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>ingressTemplate.name</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>One of </span><code>"nginx"</code><span>,
</span><code>"alb"</code><span>, </span><code>"agic"</code><span>,
</span><code>"openshift-default"</code><span>.</span><br />
<span>The ingress template to apply.</span></td>
<td><span>true</span></td>
<td><code>spec.ingress.ingressClassName</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.certificateReference</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>For </span><code>alb</code><span>, this is the
</span><code>certificate-arn</code><span>.</span><br />
<span>For </span><code>agic</code><span> this is
</span><code>appgw-ssl-certificate</code></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate</code><br />
<code>.additionalAnnotations</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Annotations to configure in addition to those deployed by the
chosen ingress template.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.tls</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>Configuration for TLS. Not necessary if using
</span><code>ingressTemplate.certificateReference</code><span> for
</span><code>alb</code><span> or </span><code>agic</code><span>. See
</span><a
href="https://kubernetes.io/docs/concepts/services-networking/ingress/#tls"><span>TLS</span></a><span>
for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.tls</code></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate</code><br />
<code>.hostname</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The hostname used to create the ingress. Useful if you'd like
ingress to use an internal hostname different from that used to access
Appian. Defaults to the hostname defined in
</span><code>url</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.hostname</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.staticHostname</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The hostname for Appian's static content URL used to create
the ingress. Useful if you'd like ingress to use an internal hostname
different from that used to access Appian. Defaults to the hostname
defined in </span><code>staticUrl</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.staticHostname</code></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate</code><br />
<code>.dynamicHostname</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The hostname for Appian's dynamic content URL used to create
the ingress. Useful if you'd like ingress to use an internal hostname
different from that used to access Appian. Defaults to the hostname
defined in </span><code>dynamicUrl</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.dynamicHostname</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.healthcheck.intervalSeconds</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate</code><br />
<code>.healthcheck.path</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.healthcheck.port</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate</code><br />
<code>.healthcheck.protocol</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.healthcheck.timeoutSeconds</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate</code><br />
<code>.healthcheck.healthyThresholdCount</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.healthcheck.unhealthyThresholdCount</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate</code><br />
<code>.listenPorts</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.loadBalancerName</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate</code><br />
<code>.scheme</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.usePrivateIp</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate</code><br />
<code>.trustedRootCertificate</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.successCodes</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate</code><br />
<code>.targetType</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
<tr class="even">
<td><code>ingressTemplate</code><br />
<code>.requestTimeout</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override ingress template value if chosen template applies
this value.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress.annotations</code></td>
</tr>
</tbody>
</table>
</figure>

### Replication parameters

The `replication` parameters enable a site to be configured for Kafka
real-time transaction replication via MirrorMaker for Kafka mirroring.
The site can be configured either as a replication source or destination
using these parameters.

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>replication.mirrorMaker.mode</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>One of </span><code>source</code><span>,
</span><code>destination</code><span>.</span><br />
<span>Setting </span><code>replication.mirrorMaker.mode</code><span> to
</span><code>source</code><span> configures this site's Kafka component
to expose listeners for a destination site to replicate
transactions.</span><br />
<span>Setting </span><code>replication.mirrorMaker.mode</code><span> to
</span><code>destination</code><span> configures this site's MirrorMaker
component to deploy the site in replication mode.</span></td>
<td><span>false</span></td>
<td><code>spec.kafka</code><span> (when
</span><code>replication.mirrorMaker.mode</code><span> is
</span><code>source</code><span>)</span><br />
<code>spec.mirrorMaker</code><span> (when
</span><code>replication.mirrorMaker.mode</code><span> is
</span><code>destination</code><span>)</span></td>
</tr>
<tr class="even">
<td><code>replication.mirrorMaker.listeners</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>List of externally addressable Kafka hosts in the source site,
used by MirrorMaker in the destination site. The order of the listeners
must match the order of Kafka's pods.</span></td>
<td><span>false</span><br />
<strong><span>Required when</span></strong><span>
</span><code>replication.mirrorMaker.mode</code><span>
</span><strong><span>is set.</span></strong></td>
<td><code>spec.kafka.mirrorMakerListeners</code><span> (when
</span><code>replication.mirrorMaker.mode</code><span> is
</span><code>source</code><span>)</span><br />
<code>spec.mirrorMaker.sourceBrokers</code><span> (when
</span><code>replication.mirrorMaker.mode</code><span> is
</span><code>destination</code><span>)</span></td>
</tr>
</tbody>
</table>
</figure>

### Per-Component overrides and additional parameters

Overrides for fields set automatically based on general parameters (e.g.
via `class`) and additional optional parameters can be specified at
component-level.

#### Zookeeper

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>zookeeper.minHeap</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the environment variable
</span><code>ZK_HEAP_MIN</code><span> set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.zookeeper.env</code></td>
</tr>
<tr class="even">
<td><code>zookeeper.maxHeap</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the environment variable
</span><code>ZK_HEAP_MAX</code><span> set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.zookeeper.env</code></td>
</tr>
<tr class="odd">
<td><code>zookeeper.storageSize</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the size of the component's RWO volumes set by
</span><code>class</code><span>. Changing this value after an initial
deployment will not automatically resize the volumes.
</span><strong><span>This field is immutable.</span></strong></td>
<td><span>false</span></td>
<td><code>spec.zookeeper</code><br />
<code>.volumeClaimTemplateSpec.resources</code><br />
<code>.requests.storage</code></td>
</tr>
<tr class="even">
<td><code>zookeeper.resources.requests.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.zookeeper</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="odd">
<td><code>zookeeper.resources.limits.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.zookeeper</code><br />
<code>.resources.limits.cpu</code></td>
</tr>
<tr class="even">
<td><code>zookeeper.resources.requests.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.zookeeper</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="odd">
<td><code>zookeeper.resources.limits.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.zookeeper</code><br />
<code>.resources.limits.memory</code></td>
</tr>
<tr class="even">
<td><a href="#common-additional-parameters"><span>Common Additional
Parameters</span></a></td>
<td> </td>
<td> </td>
<td><span>(Members of </span><a
href="#common-additional-parameters"><span>Common Additional
Parameters</span></a><span> are embedded into this type)</span></td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
</figure>

#### Kafka

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>kafka.minHeap</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the environment variable
</span><code>KAFKA_HEAP_MIN</code><span> set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.kafka.env</code></td>
</tr>
<tr class="even">
<td><code>kafka.maxHeap</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the environment variable
</span><code>KAFKA_HEAP_MAX</code><span> set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.kafka.env</code></td>
</tr>
<tr class="odd">
<td><code>kafka.storageSize</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the size of the component's RWO volumes set by
</span><code>class</code><span>. Changing this value after an initial
deployment will not automatically resize the volumes.
</span><strong><span>This field is immutable.</span></strong></td>
<td><span>false</span></td>
<td><code>spec.kafka</code><br />
<code>.volumeClaimTemplateSpec.resources</code><br />
<code>.requests.storage</code></td>
</tr>
<tr class="even">
<td><code>kafka.resources.requests.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.kafka</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="odd">
<td><code>kafka.resources.limits.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.kafka</code><br />
<code>.resources.limits.cpu</code></td>
</tr>
<tr class="even">
<td><code>kafka.resources.requests.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.kafka</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="odd">
<td><code>kafka.resources.limits.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.kafka</code><br />
<code>.resources.limits.memory</code></td>
</tr>
<tr class="even">
<td><a href="#common-additional-parameters"><span>Common Additional
Parameters</span></a></td>
<td> </td>
<td> </td>
<td><span>(Members of </span><a
href="#common-additional-parameters"><span>Common Additional
Parameters</span></a><span> are embedded into this type)</span></td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
</figure>

#### Search Server

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>searchServer.heap</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the environment variable
</span><code>SS_HEAP</code><span> set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.searchServer.env</code></td>
</tr>
<tr class="even">
<td><code>searchServer.storageSize</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the size of the component's RWO volumes set by
</span><code>class</code><span>. Changing this value after an initial
deployment will not automatically resize the volumes.
</span><strong><span>This field is immutable.</span></strong></td>
<td><span>false</span></td>
<td><code>spec.searchServer</code><br />
<code>.volumeClaimTemplateSpec.resources</code><br />
<code>.requests.storage</code></td>
</tr>
<tr class="odd">
<td><code>searchServer.resources.requests.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.searchServer</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="even">
<td><code>searchServer.resources.limits.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.searchServer</code><br />
<code>.resources.limits.cpu</code></td>
</tr>
<tr class="odd">
<td><code>searchServer.resources.requests.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.searchServer</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="even">
<td><code>searchServer.resources.limits.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.searchServer</code><br />
<code>.resources.limits.memory</code></td>
</tr>
<tr class="odd">
<td><code>searchServer.setVmMaxMapCount</code></td>
<td><span>boolean</span></td>
<td><code>true</code></td>
<td><span>Deploys a privileged init container to set the worker node
kernel's vm.max_map_count value to the </span><a
href="https://docs.appian.com/suite/help/latest/Search_Server.html#search-server-kernel-setting"><span>required
setting</span></a><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.searchServer.initContainers</code></td>
</tr>
<tr class="even">
<td><code>additionalInitContainers</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>A list of initialization containers belonging to the component
to deploy in addition to the default init container configured by the
chart for the </span><a
href="https://docs.appian.com/suite/help/latest/Search_Server.html#search-server-kernel-setting"><span>Search
Server kernel setting</span></a><span>. </span><em><span>For stateful
components with a single replica, updating this field requires
restarting the component's pod.</span></em><span> See </span><a
href="https://kubernetes.io/docs/concepts/workloads/pods/init-containers/"><span>Init
Containers</span></a><span> for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].initContainers</code></td>
</tr>
<tr class="odd">
<td><a href="#common-additional-parameters"><span>Common Additional
Parameters</span></a></td>
<td> </td>
<td> </td>
<td><span>(Members of </span><a
href="#common-additional-parameters"><span>Common Additional
Parameters</span></a><span> are embedded into this type)</span></td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
</figure>

#### Data Service

Note that the Data Service object is called `dataServer` in the Appian
CRD.

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>dataServer.class</code></td>
<td><span>enum</span></td>
<td><code>""</code></td>
<td><span>One of </span><code>"x-small", "small"</code><span>,
</span><code>"medium"</code><span>,
</span><code>"large", "x-large"</code><span>. Overrides the value of
</span><code>class</code><span> only for the Data Service component.
Used to scale Data Service independently of other platform components
(for example for sites with higher or lower Data Fabric
usage).</span><br />
<span>Changing </span><code>dataServer.class</code><span> after an
initial deployment will not automatically affect all sizings driven by
it (e.g. disk volume sizes will not change). </span><strong><span>This
field is immutable.</span></strong><br />
<span>See </span><a href="#t-shirt-sizing"><span>T-Shirt
Sizes</span></a><span>.</span></td>
<td><span>false</span></td>
<td><span>Multiple fields across all components.</span></td>
</tr>
<tr class="even">
<td><code>dataServer.rts.count</code></td>
<td><span>int</span></td>
<td><code>nil</code></td>
<td><span>Override the RTS count set by </span><code>class</code><span>.
</span><em><span>Updating this field requires restarting both Data
Service's and Webapp's pods.</span></em><span> See </span><a
href="https://docs.appian.com/suite/help/latest/Data_Server.html#real-time-store"><span>Real-time
Store</span></a><span> and </span><a
href="https://docs.appian.com/suite/help/latest/Configuring_the_Data_Server.html"><span>Configuring
the Data Service</span></a><span> for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.dataServer.topology.rtsCount</code></td>
</tr>
<tr class="odd">
<td><code>dataServer.rts</code><br />
<code>.threads</code></td>
<td><span>int</span></td>
<td><code>nil</code></td>
<td><span>Override the value of the custom property
</span><code>ads.adb.systemConfig__.rts.threads</code><span>. This
property is automatically defaulted in line with the chosen class's
default RTS count. Only use this field to override the built-in default.
See </span><a
href="https://docs.appian.com/suite/help/latest/Configuring_the_Data_Server.html#configuring-the-real-time-store"><span>Configuring
the real-time store</span></a><span> for guidance.</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code><br />
<code>.ads.adb.systemConfig__.rts.threads</code></td>
</tr>
<tr class="even">
<td><code>dataServer.rts</code><br />
<code>.memoryLimit</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the value of the custom property
</span><code>ads.adb.systemConfig__.rts.memory_limit</code><span>. This
property is automatically defaulted in line with the chosen class's
default RTS count. Only use this field to override the built-in default.
See </span><a
href="https://docs.appian.com/suite/help/latest/Configuring_the_Data_Server.html#configuring-the-real-time-store"><span>Configuring
the real-time store</span></a><span> for guidance.</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code><br />
<code>.ads.adb.systemConfig__.rts.memory_limit</code></td>
</tr>
<tr class="odd">
<td><code>dataServer.storageSize</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the size of the component's RWO volumes set by
</span><code>class</code><span>. Changing this value after an initial
deployment will not automatically resize the volumes.
</span><strong><span>This field is immutable.</span></strong></td>
<td><span>false</span></td>
<td><code>spec.dataServer</code><br />
<code>.volumeClaimTemplateSpec.resources</code><br />
<code>.requests.storage</code></td>
</tr>
<tr class="even">
<td><code>dataServer.resources.requests.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.dataServer</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="odd">
<td><code>dataServer.resources.limits.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.dataServer</code><br />
<code>.resources.limits.cpu</code></td>
</tr>
<tr class="even">
<td><code>dataServer.resources.requests.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.dataServer</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="odd">
<td><code>dataServer.resources.limits.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.dataServer</code><br />
<code>.resources.limits.memory</code></td>
</tr>
<tr class="even">
<td><a href="#common-additional-parameters"><span>Common Additional
Parameters</span></a></td>
<td> </td>
<td> </td>
<td><span>(Members of </span><a
href="#common-additional-parameters"><span>Common Additional
Parameters</span></a><span> are embedded into this type)</span></td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
</figure>

#### Service Manager

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>serviceManager.replicas</code></td>
<td><span>int</span></td>
<td><code>nil</code></td>
<td><span>Override the number of replicas for service manager set by
</span><code>highAvailability</code><span>. Defaults to
</span><code>1</code><span> for non-high availability and
</span><code>3</code><span> for high availability.
</span><em><span>Updating this field is disallowed both before Appian
has started and when </span><code>highAvailability</code><span> is not
</span><code>true</code><span>.</span></em></td>
<td><span>false</span></td>
<td><code>spec.serviceManager.replicas</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.komodoDirectMemMax</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the environment variable
</span><code>KOMODO_DIRECT_MEM_MAX</code><span> set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager.env</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.komodoHeapMax</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the environment variable
</span><code>KOMODO_HEAP_MAX</code><span> set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager.env</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.maxExecEngineLoadMetric</code></td>
<td><span>int</span></td>
<td><code>120</code></td>
<td><span>Override the value of the custom property
</span><code>server.conf.processcommon.MAX_EXEC_ENGINE_LOAD_METRIC</code><span>.
This property is defaulted to </span><code>120</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code><br />
<code>.server.conf.processcommon.MAX_EXEC_ENGINE_LOAD_METRIC</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.storageSize</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the size of the component's RWO volumes set by
</span><code>class</code><span>. Changing this value after an initial
deployment will not automatically resize the volumes.
</span><strong><span>This field is immutable.</span></strong></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.volumeClaimTemplateSpec.resources</code><br />
<code>.requests.storage</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.analyticsExecShardCount</code></td>
<td><span>int</span></td>
<td><code>3</code></td>
<td><span>Override the number of shards of the process analytics and
process execution engines. </span><strong><span>This field is
immutable.</span></strong><span> See </span><a
href="https://docs.appian.com/suite/help/latest/Scaling_Appian.html#add-execution-and-analytics-shards"><span>Add
Execution and Analytics Shards</span></a><span> for more
info.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.topology.analyticsExecShardCount</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.exec.resources.requests.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the execution engines' CPU requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.execution</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.exec.resources.limits.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the execution engines' CPU limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.execution</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.exec.resources.requests.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the execution engines' memory requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.execution</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.exec.resources.limits.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the execution engines' memory limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.execution</code><br />
<code>.resources.limits.memory</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.analytics.resources.requests.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the analytics engines' CPU requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.analytics</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.analytics.resources.limits.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the analytics engines' CPU limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.analytics</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.analytics.resources.requests.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the analytics engines' memory requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.analytics</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.analytics.resources.limits.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the analytics engines' memory limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.analytics</code><br />
<code>.resources.limits.memory</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.tier2.resources.requests.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the CPU requests for the groups, collaboration and
process design engines set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.[groups|content|processDesign]</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.tier2.resources.limits.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the CPU limits for the groups, collaboration and
process design engines set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.[groups|content|processDesign]</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.tier2.resources.requests.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the memory requests for the groups, collaboration and
process design engines set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.[groups|content|processDesign]</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.tier2.resources.limits.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the the memory limits for the groups, collaboration
and process design engines set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.engineOverrides.[groups|content|processDesign]</code><br />
<code>.resources.limits.memory</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.default.resources.requests.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the default CPU requests used by all other engines
set by </span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.default.resources.limits.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the default CPU limits used by all other engines set
by </span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.resources.limits.cpu</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.default.resources.requests.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the default memory requests used by all other engines
set by </span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="even">
<td><code>serviceManager.default.resources.limits.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the the memory limits used by all other engines set
by </span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager</code><br />
<code>.resources.limits.memory</code></td>
</tr>
<tr class="odd">
<td><code>serviceManager.engineOverrides</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Allows complete override of all per-engine configurations set
by </span><code>class</code><span>. </span><br />
<span>Used in the scenario where you require complete granular control
over every engine type's CPU and memory configuration. To set the
</span><code>engineOverrides</code><span> field for the first time,
generate the CR spec without </span><code>engineOverrides</code><span>
set using </span><code>helm template</code><span> and then use the
output value of </span><code>engineOverrides</code><span> in the
generated CR spec as the starting value for your Helm values
</span><code>engineOverrides</code><span> field. This way, you start
with the current engine-level configurations for your chosen class and
can adjust them accordingly.</span><br />
<span>See </span><a
href="https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1engineoverrides"><span>Engine
Overrides</span></a><span> for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.serviceManager.engineOverrides</code></td>
</tr>
<tr class="even">
<td><a href="#common-additional-parameters"><span>Common Additional
Parameters</span></a></td>
<td> </td>
<td> </td>
<td><span>(Members of </span><a
href="#common-additional-parameters"><span>Common Additional
Parameters</span></a><span> are embedded into this type)</span></td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
</figure>

#### Webapp

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>webapp.replicas</code></td>
<td><span>int</span></td>
<td><code>nil</code></td>
<td><span>Override the number of replicas for webapp set by
</span><code>highAvailability</code><span>. When set, this field also
sets the httpd component's replicas to match. </span><em><span>Updating
this field is disallowed both before Appian has started and when
</span><code>highAvailability</code><span> is not
</span><code>true</code><span>.</span></em></td>
<td><span>false</span></td>
<td><code>spec.webapp.replicas</code><br />
<code>spec.httpd.replicas</code></td>
</tr>
<tr class="even">
<td><code>webapp.minHeap</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Set the custom property
</span><code>conf.appserver.minHeapSize</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="odd">
<td><code>webapp.maxHeap</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the custom property
</span><code>conf.appserver.maxHeapSize</code><span> set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="even">
<td><code>webapp.autodeleteArchivesDelayDays</code></td>
<td><span>string</span></td>
<td><code>"30"</code></td>
<td><span>Override the custom property
</span><code>server.conf.processcommon.AUTODELETE_ARCHIVES_DELAY_DAYS</code><span>
set automatically by the chart. This </span><a
href="https://docs.appian.com/suite/help/latest/Configuring_Archived_Processes.html#automated-deletion"><span>setting</span></a><span>
defines when archived processes will automatically be deleted, both from
the Process Activity monitor view, and the .l files
themselves.</span></td>
<td><span>false</span></td>
<td><code>spec.customProperties</code></td>
</tr>
<tr class="odd">
<td><code>webapp.storageSize</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the size of the component's RWO volumes set by
</span><code>class</code><span>. Changing this value after an initial
deployment will not automatically resize the volumes.
</span><strong><span>This field is immutable.</span></strong></td>
<td><span>false</span></td>
<td><code>spec.webapp</code><br />
<code>.volumeClaimTemplateSpec.resources</code><br />
<code>.requests.storage</code></td>
</tr>
<tr class="even">
<td><code>webapp.resources.requests.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="odd">
<td><code>webapp.resources.limits.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp</code><br />
<code>.resources.limits.cpu</code></td>
</tr>
<tr class="even">
<td><code>webapp.resources.requests.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="odd">
<td><code>webapp.resources.limits.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp</code><br />
<code>.resources.limits.memory</code></td>
</tr>
<tr class="even">
<td><code>webapp.dataSources</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Override completely the webapp data source configuration set
via templates by </span><code>dataSources.primary</code><span> and
</span><code>dataSources.business</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp.dataSources</code></td>
</tr>
<tr class="odd">
<td><code>webapp.additionalInitContainers</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>A list of initialization containers belonging to the component
to deploy in addition to any default init containers configured by the
chart. If no default init containers would be deployed, this field has
the same effect as </span><code>webapp.initContainers</code><span>.
</span><em><span>For stateful components with a single replica, updating
this field requires restarting the component's pod.</span></em><span>
See </span><a
href="https://kubernetes.io/docs/concepts/workloads/pods/init-containers/"><span>Init
Containers</span></a><span> for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp.initContainers</code></td>
</tr>
<tr class="even">
<td><code>webapp.customLoggers</code></td>
<td><a href="#custom-logger"><span>Custom Logger</span></a><span>
list</span></td>
<td><code>[]</code></td>
<td><span>A list of </span><a href="#custom-logger"><span>Custom
Logger</span></a><span> to be applied to webapp components. Implements
the </span><a
href="https://docs.appian.com/suite/help/latest/customizing-application-logging.html#customizing-application-logging-for-the-first-time"><span>Customizing
Application Logging</span></a><span> pattern. If set, this chart deploys
an additional ConfigMap
</span><code>appian-log4j-override-properties</code><span> and mounts it
to all webapp pods.</span></td>
<td><span>false</span></td>
<td><code>spec.webapp.additionalVolumes</code><br />
<code>spec.webapp.additionalVolumeMounts</code></td>
</tr>
<tr class="odd">
<td><a href="#common-additional-parameters"><span>Common Additional
Parameters</span></a></td>
<td> </td>
<td> </td>
<td><span>(Members of </span><a
href="#common-additional-parameters"><span>Common Additional
Parameters</span></a><span> are embedded into this type)</span></td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
</figure>

#### Httpd

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>httpd.replicas</code></td>
<td><span>int</span></td>
<td><code>nil</code></td>
<td><span>Override the number of replicas for httpd set by
</span><code>highAvailability</code><span> or
</span><code>webapp.replicas</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.httpd.replicas</code></td>
</tr>
<tr class="even">
<td><code>httpd.resources.requests.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.httpd</code><br />
<code>.resources.requests.cpu</code></td>
</tr>
<tr class="odd">
<td><code>httpd.resources.limits.cpu</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's CPU limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.httpd</code><br />
<code>.resources.limits.cpu</code></td>
</tr>
<tr class="even">
<td><code>httpd.resources.requests.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory requests set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.httpd</code><br />
<code>.resources.requests.memory</code></td>
</tr>
<tr class="odd">
<td><code>httpd.resources.limits.memory</code></td>
<td><span>int or string</span></td>
<td><code>""</code></td>
<td><span>Override the component's memory limits set by
</span><code>class</code><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.httpd</code><br />
<code>.resources.limits.memory</code></td>
</tr>
<tr class="even">
<td><a href="#common-additional-parameters"><span>Common Additional
Parameters</span></a></td>
<td> </td>
<td> </td>
<td><span>(Members of </span><a
href="#common-additional-parameters"><span>Common Additional
Parameters</span></a><span> are embedded into this type)</span></td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
</figure>

#### MirrorMaker

<figure class="table-figure">
<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>mirrorMaker.resources</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Compute resources required by the component's container(s).
See </span><a
href="https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/"><span>Resource
Management for Pods and Containers</span></a><span> for more
info.</span></td>
<td><span>false</span></td>
<td><code>spec.mirrorMaker.resources</code></td>
</tr>
<tr class="even">
<td><code>mirrorMaker.sourceBrokers</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>Override the value set by
</span><code>replication.mirrorMaker.listeners</code><span>. List of
hosts that point to the Kafka brokers in the source cluster.
</span><em><span>Updating this field requires restarting MirrorMaker's
pod(s).</span></em></td>
<td><span>false</span></td>
<td><code>spec.mirrorMaker.sourceBrokers</code></td>
</tr>
<tr class="odd">
<td><code>mirrorMaker.storageSize</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Override the size of the component's RWO volumes set by
</span><code>class</code><span>. Changing this value after an initial
deployment will not automatically resize the volumes.
</span><strong><span>This field is immutable.</span></strong></td>
<td><span>false</span></td>
<td><code>spec.mirrorMaker</code><br />
<code>.volumeClaimTemplateSpec.resources</code><br />
<code>.requests.storage</code></td>
</tr>
<tr class="even">
<td><a href="#common-additional-parameters"><span>Common Additional
Parameters</span></a></td>
<td> </td>
<td> </td>
<td><span>(Members of </span><a
href="#common-additional-parameters"><span>Common Additional
Parameters</span></a><span> are embedded into this type)</span></td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
</figure>

#### Common Additional Parameters

The following optional parameters can be specified for any component
listed [above](#per-component-overrides-and-additional-parameters).

<figure class="table-figure">
<table>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>[component].initContainers</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>A list of initialization containers belonging to the
component. Initialization containers satisfy a variety of use cases -
including supplying RDBMS/JDBC drivers. </span><em><span>For stateful
components with a single replica, updating this field requires
restarting the component's pod.</span></em><span> See </span><a
href="https://kubernetes.io/docs/concepts/workloads/pods/init-containers/"><span>Init
Containers</span></a><span> for more info. For a component that has a
</span><code>[component].additionalInitContainers</code><span>
parameter, </span><code>[component].initContainers</code><span> will
override any init containers that are automatically configured by the
chart.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].initContainers</code></td>
</tr>
<tr class="even">
<td><code>[component].env</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>A list of environment variables to set in the component's
container(s). </span><em><span>For stateful components with a single
replica, updating this field requires restarting the component's
pod.</span></em><span> See </span><a
href="https://kubernetes.io/docs/tasks/inject-data-application/define-environment-variable-container/"><span>Define
Environment Variables for a Container</span></a><span> for more
info.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].env</code></td>
</tr>
<tr class="odd">
<td><code>[component].additionalVolumes</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>Additional volumes for the component's pod(s).
</span><em><span>For stateful components with a single replica, updating
this field requires restarting the component's pod.</span></em><span>
See </span><a
href="https://kubernetes.io/docs/concepts/storage/volumes/"><span>Volumes</span></a><span>
for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].additionalVolumes</code></td>
</tr>
<tr class="even">
<td><code>[component].additionalVolumeMounts</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>Additional volume mounts for the component's container(s).
</span><em><span>For stateful components with a single replica, updating
this field requires restarting the component's pod.</span></em><span>
See </span><a
href="https://kubernetes.io/docs/concepts/storage/volumes/"><span>Volumes</span></a><span>
for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].additionalVolumeMounts</code></td>
</tr>
<tr class="odd">
<td><code>[component].sidecarContainers</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>Sidecar containers for the component's container(s).
</span><em><span>For stateful components with a single replica, updating
this field requires restarting the component's pod.</span></em></td>
<td><span>false</span></td>
<td><code>spec.[component].sidecarContainers</code></td>
</tr>
<tr class="even">
<td><code>[component].nodeSelector</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>A selector which must be true for the component's pod(s) to
fit on a node. </span><em><span>For stateful components with a single
replica, updating this field requires restarting the component's
pod.</span></em><span> See </span><a
href="https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#nodeselector"><span>nodeSelector</span></a><span>
for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].nodeSelector</code></td>
</tr>
<tr class="odd">
<td><code>[component].tolerations</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>Tolerations for the component's pod(s). </span><em><span>For
stateful components with a single replica, updating this field requires
restarting the component's pod.</span></em><span> See </span><a
href="https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/"><span>Taints
and Tolerations</span></a><span> for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].tolerations</code></td>
</tr>
<tr class="even">
<td><code>[component].additionalNetworkPolicyIngressRules</code></td>
<td><span>list</span></td>
<td><code>[]</code></td>
<td><span>Additional ingress rules for the component's network policy.
</span><strong><span>Forbidden when
</span><code>spec.networkPolicies.enabled</code><span> is
</span><code>false</code><span>.</span></strong><span> See </span><a
href="https://kubernetes.io/docs/concepts/services-networking/network-policies/#the-networkpolicy-resource"><span>Network
Policies</span></a><span> for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].additionalNetworkPolicyIngressRules</code></td>
</tr>
<tr class="odd">
<td><code>[component].priorityClassName</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>Priority Class for the component's pod(s).
</span><em><span>For stateful components with a single replica, updating
this field requires restarting the component's pod.</span></em><span>
See </span><a
href="https://kubernetes.io/docs/concepts/scheduling-eviction/pod-priority-preemption/"><span>Pod
Priority and Preemption</span></a><span> for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].priorityClassName</code></td>
</tr>
<tr class="even">
<td><code>[component].dnsPolicy</code></td>
<td><span>object</span></td>
<td><code>""</code></td>
<td><span>DNS policy for the component's pod(s). </span><em><span>For
stateful components with a single replica, updating this field requires
restarting the component's pod.</span></em><span> This field will
default to </span><code>ClusterFirst</code><span> if not specified. See
</span><a
href="https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/#pod-s-dns-policy"><span>Pod
DNS Policy</span></a><span> for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].dnsPolicy</code></td>
</tr>
<tr class="odd">
<td><code>[component].dnsConfig</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>DNS Config for the component's pod(s). </span><em><span>For
stateful components with a single replica, updating this field requires
restarting the component's pod.</span></em><span> This field is required
when DNSPolicy is set to </span><code>None</code><span>. If DNS Policy
is not specified, then </span><code>ClusterFirst</code><span> is used.
See </span><a
href="https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/#pod-dns-config"><span>Pod
DNS Config</span></a><span> for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].dnsConfig</code></td>
</tr>
<tr class="even">
<td><code>[component].podAnnotations</code></td>
<td><span>map[string]string</span></td>
<td><code>{}</code></td>
<td><span>Annotations to be applied to the component's pod(s).
</span><em><span>For stateful components with a single replica, updating
this field requires restarting the component's pod.</span></em></td>
<td><span>false</span></td>
<td><code>spec.[component].podAnnotations</code></td>
</tr>
<tr class="odd">
<td><code>[component].podLabels</code></td>
<td><span>map[string]string</span></td>
<td><code>{}</code></td>
<td><span>Labels to be applied to the component's pod(s).
</span><em><span>For stateful components with a single replica, updating
this field requires restarting the component's pod.</span></em></td>
<td><span>false</span></td>
<td><code>spec.[component].podLabels</code></td>
</tr>
<tr class="even">
<td><code>[component].serviceAccount</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Configuration for the component's </span><a
href="https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1serviceaccount"><span>service
account</span></a><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].serviceAccount</code></td>
</tr>
<tr class="odd">
<td><code>[component].securityContext</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Container-level security context for the component. Overrides
the global </span><code>securityContext</code><span>. Passthrough to
</span><a
href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#securitycontext-v1-core"><code>corev1.SecurityContext</code></a><span>.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].securityContext</code></td>
</tr>
<tr class="even">
<td><code>[component].podSecurityContext</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Pod-level security context for the component. Overrides the
global </span><code>podSecurityContext</code><span>. Passthrough to
</span><a
href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#podsecuritycontext-v1-core"><code>corev1.PodSecurityContext</code></a><span>.
Requires Appian Operator v0.200.0+.</span></td>
<td><span>false</span></td>
<td><code>spec.[component].podSecurityContext</code></td>
</tr>
</tbody>
</table>
</figure>

#### Custom Logger

The following parameters are available for each item in the list
`webapp.customLoggers`. The chart\'s Custom Logger Template makes it
simpler to customize application logging. Logging for these custom
loggers will be output in the root `~/logs` directory of each pod and
named `{reference}.log`. Log rotation is enabled within the settings
output in the ConfigMap generated by this chart.

<figure class="table-figure">
<table>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>reference</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>An uppercase underscore separated reference for your logger,
containing letters only (e.g.
</span><code>COM_APPIAN_PACKAGE_DEBUG</code><span>).</span></td>
<td><span>true</span></td>
<td><code>appian-log4j-override-properties</code></td>
</tr>
<tr class="even">
<td><code>packageName</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The package name to be logged (e.g.
</span><code>com.appian.package</code><span>). Do not include the prefix
</span><code>log4j.logger.</code><span> in the package name
provided.</span></td>
<td><span>true</span></td>
<td><code>appian-log4j-override-properties</code></td>
</tr>
<tr class="odd">
<td><code>loggingLevel</code></td>
<td><span>string</span></td>
<td><code>""</code></td>
<td><span>The logging level to be logged (e.g.
</span><code>DEBUG</code><span>).</span></td>
<td><span>true</span></td>
<td><code>appian-log4j-override-properties</code></td>
</tr>
</tbody>
</table>
</figure>

#### Service

By default, a `service` is configured by the chart with
`spec.service.type: ClusterIP`. Configure this `service` object for any
alternative service configurations.

<figure class="table-figure">
<table>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>service</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Service defines configuration for creating Appian's service
resource. See </span><a
href="https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1service"><span>Service</span></a><span>
for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.service</code></td>
</tr>
</tbody>
</table>
</figure>

#### Ingress

Ingress for ingress controllers [NGINX Ingress
Controller](https://docs.nginx.com/nginx-ingress-controller/), [AWS Load
Balancer
Controller](https://kubernetes-sigs.github.io/aws-load-balancer-controller)
and [Azure Application Gateway Ingress Controller
(AGIC)](https://learn.microsoft.com/en-us/azure/application-gateway/ingress-controller-overview)
can be configured via [ingressTemplate](#ingress-template-parameters).
For any other ingress controller, use `ingress` below.

<figure class="table-figure">
<table>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>ingress</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Configuration for creating Appian's ingress resource if not
using </span><a
href="#ingress-template-parameters"><span>ingressTemplate</span></a><span>.
See </span><a
href="https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1ingress"><span>Ingress</span></a><span>
for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.ingress</code></td>
</tr>
</tbody>
</table>
</figure>

#### RPA

RPA can be configured for the Appian site via the `rpa` component. No
pre-configured options are included in this Helm chart for RPA at this
time. See the [sample YAML
file](https://docs.appian.com/suite/help/latest/k8s/install-appian-on-k8s.html#4.-create-an-appian-yaml-file),
the [Custom Resource
Definition](https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1.rpa)
and the [RPA Setup
section](https://docs.appian.com/suite/help/latest/rpa-setup-on-k8s.html)
for RPA configuration options.

<figure class="table-figure">
<table>
<thead>
<tr class="header">
<th><span>Key</span></th>
<th><span>Type</span></th>
<th><span>Default</span></th>
<th><span>Description</span></th>
<th><span>Required</span></th>
<th><span>CRD Field(s) Impacted</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>rpa</code></td>
<td><span>object</span></td>
<td><code>{}</code></td>
<td><span>Defines configuration for RPA. See </span><a
href="https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1.rpa"><span>RPA</span></a><span>
for more info.</span></td>
<td><span>false</span></td>
<td><code>spec.service</code></td>
</tr>
</tbody>
</table>
</figure>

### Managed Custom Properties

The following custom properties are automatically added based on either
default configurations, class or driven by values file fields.

<figure class="table-figure">
<table>
<thead>
<tr class="header">
<th><span>Component</span></th>
<th><span>Custom Properties</span></th>
<th><span>Driven By</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span>App Server Heap</span></td>
<td><code>conf.appserver.maxHeapSize</code></td>
<td><span>Class and </span><code>webapp</code><span> override
field</span></td>
</tr>
<tr class="even">
<td><span>App Server Heap</span></td>
<td><code>conf.appserver.minHeapSize</code></td>
<td><code>webapp</code><span> field</span></td>
</tr>
<tr class="odd">
<td><span>SMTP</span></td>
<td><code>conf.mailhandler.*</code><span> properties,
</span><code>conf.suite.MAIL_SCHEME</code><span> and
</span><code>conf.suite.MAIL_SERVER_AND_PORT</code></td>
<td><code>smtp</code><span> fields</span></td>
</tr>
<tr class="even">
<td><span>Data Service</span></td>
<td><code>ads.adb.systemConfig__.rts.memory_limit</code><span> and
</span><code>ads.adb.systemConfig__.rts.threads</code></td>
<td><span>Class and </span><code>dataServer</code><span> override
field</span></td>
</tr>
<tr class="odd">
<td><span>Process Engines</span></td>
<td><code>server.conf.processcommon.MAX_EXEC_ENGINE_LOAD_METRIC</code></td>
<td><span>Default value and </span><code>serviceManager</code><span>
override field</span></td>
</tr>
<tr class="even">
<td><span>Process Engines</span></td>
<td><code>server.conf.processcommon.AUTODELETE_ARCHIVES_DELAY_DAYS</code></td>
<td><span>Default value and </span><code>webapp</code><span> override
field</span></td>
</tr>
<tr class="odd">
<td><span>Metrics API</span></td>
<td><code>appian.feature.selfManagedMonitoring</code><span> and
</span><code>metricsauthtoken</code></td>
<td><code>metricsAuthToken</code><span> field</span></td>
</tr>
</tbody>
</table>
</figure>

### Excluded Appian CRD Fields

The following fields from the Appian CRD either cannot be set via this
Helm chart, or the value that this Helm chart configures cannot be
directly overridden. If you must customise one of these fields, this can
be done in the site YAML directly after generating it via
`helm template`.

<figure class="table-figure">
<table>
<thead>
<tr class="header">
<th><span>CRD Field</span></th>
<th><span>Reason</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>[component].podDisruptionBudget</code></td>
<td><span>Pod Disruption Budgets are set by the chart for each component
when </span><code>highAvailability</code><span> is
</span><code>true</code><span>.</span></td>
</tr>
<tr class="even">
<td><code>[component].replicas</code></td>
<td><code>[component].replicas</code><span>is set by the chart depending
on the value of </span><code>highAvailability</code><span>. For service
manager, webapp and httpd this value can be overridden. For all other
components this value cannot be overridden and will be
</span><code>1</code><span> for non-HA and </span><code>3</code><span>
for HA).</span></td>
</tr>
<tr class="odd">
<td><code>[component].affinity</code></td>
<td><span>The Appian operator deploys a default affinity configuration.
This cannot be customized for the Service Manager pods without breaking
exec/analytics engine shard-level affinity configuration. This chart
does not support customizing affinity. This chart does, however, deploy
a customised affinity rule for httpd to allow the additional httpd pod
that is deployed and terminated on site startup to be scheduled on the
same worker as another httpd pod to ensure it can launch and terminate
successfully. </span><code>nodeSelector</code><span> can still be
configured globally and per-component to constrain Pods to nodes with
specific labels.</span></td>
</tr>
<tr class="even">
<td><code>serviceManager.engineOverrides.[engine].replicas</code></td>
<td><span>Engine type replica count cannot be customised at engine
level. They will always use the global
</span><code>serviceManager.replicas</code><span> value.</span></td>
</tr>
</tbody>
</table>
</figure>

## Release Notes

#### 2.1.0 {#210}

**BREAKING CHANGES** This release includes breaking changes. If
upgrading to this version, read these Release Notes carefully before
upgrading and use `helm template` to compare the output with that from
your current version to ensure the result is as expected.

-   The minimum Appian Operator version compatible with this chart is
    v0.200.0.

-   **Breaking Change** `securityContext` is now a pure passthrough to
    [`corev1.SecurityContext`](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#securitycontext-v1-core)
    (container-level), aligning with the Appian Operator v0.200.0+ CRD.
    If you previously set `fsGroup` or `fsGroupChangePolicy` under
    `securityContext` (globally or per-component), you must move these
    to `podSecurityContext`. These fields are [deprecated on
    `securityContext`](https://docs.appian.com/suite/help/latest/k8s-0.201.0/crds.html#v1beta1securitycontext)
    and will be removed by the operator in a future release.

-   New `podSecurityContext` field added as a pure passthrough to
    [`corev1.PodSecurityContext`](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#podsecuritycontext-v1-core)
    (pod-level). Supports global and per-component override, same
    pattern as `securityContext` and `nodeSelector`.

**Migration example** --- if your current values contain:

``` {.md-fences .md-end-block .ty-contain-cm .modeLoaded spellcheck="false" lang="yaml"}
xxxxxxxxxx
```

::: CodeMirror-measure
:::

::: {style="position: relative; z-index: 1;"}
:::

::: {.CodeMirror-code role="presentation" style=""}
::: {.CodeMirror-activeline style="position: relative;"}
::: {.CodeMirror-activeline-background .CodeMirror-linebackground}
:::

::: {.CodeMirror-gutter-background .CodeMirror-activeline-gutter style="left: 0px; width: 0px;"}
:::

``` {.CodeMirror-line role="presentation"}
# Old (pre-2.1.0)
```
:::

``` {.CodeMirror-line role="presentation"}
securityContext:
```

``` {.CodeMirror-line role="presentation"}
  runAsUser: 500
```

``` {.CodeMirror-line role="presentation"}
  fsGroup: 500
```

``` {.CodeMirror-line role="presentation"}
  fsGroupChangePolicy: OnRootMismatch
```
:::

::: {style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 115px;"}
:::

::: {.CodeMirror-gutters style="display: none; height: 115px;"}
:::

Update to:

``` {.md-fences .md-end-block .ty-contain-cm .modeLoaded spellcheck="false" lang="yaml"}
xxxxxxxxxx
```

::: CodeMirror-measure
:::

::: {style="position: relative; z-index: 1;"}
:::

::: {.CodeMirror-code role="presentation" style=""}
::: {.CodeMirror-activeline style="position: relative;"}
::: {.CodeMirror-activeline-background .CodeMirror-linebackground}
:::

::: {.CodeMirror-gutter-background .CodeMirror-activeline-gutter style="left: 0px; width: 0px;"}
:::

``` {.CodeMirror-line role="presentation"}
# New (2.1.0+)
```
:::

``` {.CodeMirror-line role="presentation"}
securityContext:
```

``` {.CodeMirror-line role="presentation"}
  runAsUser: 500
```

``` {.CodeMirror-line role="presentation"}
  allowPrivilegeEscalation: false
```

``` {.CodeMirror-line role="presentation"}
podSecurityContext:
```

``` {.CodeMirror-line role="presentation"}
  fsGroup: 500
```

``` {.CodeMirror-line role="presentation"}
  fsGroupChangePolicy: OnRootMismatch
```
:::

::: {style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 161px;"}
:::

::: {.CodeMirror-gutters style="display: none; height: 161px;"}
:::

The same applies at component level --- e.g.
`httpd.securityContext.fsGroup` becomes
`httpd.podSecurityContext.fsGroup`.

#### 2.0.0 {#200}

**BREAKING CHANGES** This release includes breaking changes. If
upgrading to this version, read these Release Notes carefully before
upgrading and use `helm tempalate` to compare the output with that from
your current version to ensure the result is as expected.

-   The minimum Appian Operator version compatible with this chart is
    v0.194.0.

-   Corrected data source template for Oracle so the connection URL
    includes the required leading `//` after the `@`.

-   Support setting `securityContext` globally for all components, or at
    component level as `[component].securityContext`.

-   Support disabling the built-in Search Server init container that
    sets vm.max_map_count on the worker node via the new field
    `searchServer.setVmMaxMapCount`. This field defaults to `true`. If
    you choose to disable this init container, you must ensure via other
    means that vm.max_map_count is correctly set on all worker nodes
    onto which Search Server pods could be provisioned.

-   Support setting `images.pullPolicy` to be applied to all components
    and built-in init containers.

-   Removed support for deprecated
    `dataSources.mysqlDriverConfigMapName` field.

-   Added default CPU and memory requests and limits to httpd. Default
    httpd resources can be overridden in the same way as other
    components (instead of via the removed field `httpd.resources`).

-   httpd affinity rules updated to allow the n+1 httpd pod that is
    launched to run on the same worker as another pod if required, to
    ensure it is able to run and terminate. This avoids being left with
    a stuck httpd pod when httpd replica count is \<= number of worker
    nodes.

-   Support setting `spec.[component].serviceAccount` field for a
    component.

-   The chart sets the custom property
    `server.conf.processcommon.AUTODELETE_ARCHIVES_DELAY_DAYS` to a
    default of 30 days to automatically clean up archived processes.
    This can be customised via `webapp.autodeleteArchivesDelayDays`. If
    not customised, this will now result in your archived processes
    being automatically deleted after 30 days.

-   Support OpenShift Default ingress controller as `ingressTemplate`.

-   Chart now sets the new custom properties used by the Appian Data
    Service since 25.1 `ads.adb.systemConfig__.rts.memory_limit` and
    `ads.adb.systemConfig__.rts.threads`, instead of the deprecated
    `rts.queryMemoryLimits.circuitBreaker.threshold.bytes`. Removed
    corresponding override field
    `dataServer.rts.queryMemoryCircuitBreakerThresholdBytes` and added
    new override fields under `dataServer.rts`.

-   Restructured or renamed some existing chart values fields to align
    with a more standardised naming approach (see table below).

-   The chart no longer populates `spec.httpd.nslookupImage` (which is
    not used from Operator v0.194.0).

-   Data source username field
    `dataSources.[primary\|business[]].username` has been removed in
    favour of providing the username(s) via a secret
    `dataSources.[primary\|business[]].usernameSecretKeyRef`.

**Values field restructuring**

Some of the fields have been restructured in this release to be more
user friendly. The following table provides a guide to help you update
your values files to use the new field name.

<figure class="table-figure">
<table>
<thead>
<tr class="header">
<th><span>Old Field Name</span></th>
<th><span>New Field Name</span></th>
<th><span>Notes</span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>[component].cpuRequests</code></td>
<td><code>[component].resources.requests.cpu</code></td>
<td> </td>
</tr>
<tr class="even">
<td><code>[component].cpuLimits</code></td>
<td><code>[component].resources.limits.cpu</code></td>
<td> </td>
</tr>
<tr class="odd">
<td><code>[component].memoryRequests</code></td>
<td><code>[component].resources.requests.memory</code></td>
<td> </td>
</tr>
<tr class="even">
<td><code>[component].memoryLimits</code></td>
<td><code>[component].resources.limits.memory</code></td>
<td> </td>
</tr>
<tr class="odd">
<td><code>disableCpuLimits</code></td>
<td><code>enableCpuLimits</code></td>
<td><span>Default functionality is unchanged. CPU limits are disabled by
default.</span></td>
</tr>
<tr class="even">
<td><code>disableResourceRequests</code></td>
<td><code>enableResourceRequests</code></td>
<td><span>Default functionality is unchanged. Resource requests are
enabled by default.</span></td>
</tr>
<tr class="odd">
<td><code>webapp.minHeapSize</code></td>
<td><code>webapp.minHeap</code></td>
<td> </td>
</tr>
<tr class="even">
<td><code>webapp.maxHeapSize</code></td>
<td><code>webapp.maxHeap</code></td>
<td> </td>
</tr>
<tr class="odd">
<td><code>tshirtSize</code></td>
<td><code>class</code></td>
<td> </td>
</tr>
<tr class="even">
<td><code>images.imagePullSecrets</code></td>
<td><code>images.pullSecrets</code></td>
<td> </td>
</tr>
<tr class="odd">
<td><code>k3LicSecretName</code></td>
<td><code>license.k3SecretName</code></td>
<td> </td>
</tr>
<tr class="even">
<td><code>k4LicSecretName</code></td>
<td><code>license.k4SecretName</code></td>
<td> </td>
</tr>
<tr class="odd">
<td><code>appianLicConfigMapName</code></td>
<td><code>license.appianConfigMapName</code></td>
<td> </td>
</tr>
<tr class="even">
<td><code>dataSources.mysqlDriverConfigMapName</code></td>
<td><span>Removed</span></td>
<td><span>Removed. MySQL driver is now too large to support deployment
via ConfigMap</span></td>
</tr>
<tr class="odd">
<td><code>dataServer.rts.queryMemoryCircuitBreakerThresholdBytes</code></td>
<td><span>Removed</span></td>
<td><span>Removed. From 25.1 the Data Service uses alternative custom
properties instead, defaulted based on class and overridden via
</span><code>dataServer.rts.threads</code><span> and
</span><code>dataServer.rts.memoryLimit</code><span>.</span></td>
</tr>
<tr class="even">
<td><code>dataSources.[primary\|business[]].username</code></td>
<td><code>dataSources.[primary\|business[]].usernameSecretKeyRef.name</code><span>
and
</span><code>dataSources.[primary\|business[]].usernameSecretKeyRef.key</code></td>
<td><span>Data Source Template's </span><code>username</code><span>
field has been removed in favour of providing the username(s) via a
secret.</span></td>
</tr>
<tr class="odd">
<td><code>ingressTemplate.healthcheckIntervalSeconds</code></td>
<td><code>ingressTemplate.healthcheck.intervalSeconds</code></td>
<td> </td>
</tr>
<tr class="even">
<td><code>ingressTemplate.healthcheckPath</code></td>
<td><code>ingressTemplate.healthcheck.path</code></td>
<td> </td>
</tr>
<tr class="odd">
<td><code>ingressTemplate.healthcheckPort</code></td>
<td><code>ingressTemplate.healthcheck.port</code></td>
<td> </td>
</tr>
<tr class="even">
<td><code>ingressTemplate.healthcheckProtocol</code></td>
<td><code>ingressTemplate.healthcheck.protocol</code></td>
<td> </td>
</tr>
<tr class="odd">
<td><code>ingressTemplate.healthcheckTimeoutSeconds</code></td>
<td><code>ingressTemplate.healthcheck.timeoutSeconds</code></td>
<td> </td>
</tr>
<tr class="even">
<td><code>ingressTemplate.healthcheckHealthyThresholdCount</code></td>
<td><code>ingressTemplate.healthcheck.healthyThresholdCount</code></td>
<td> </td>
</tr>
<tr class="odd">
<td><code>ingressTemplate.healthcheckUnhealthyThresholdCount</code></td>
<td><code>ingressTemplate.healthcheck.unhealthyThresholdCount</code></td>
<td> </td>
</tr>
</tbody>
</table>
</figure>

*Built against Appian operator v0.194.0 and Appian platform 25.4. This
chart will work with older and newer versions of the Appian operator (to
a minimum of v0.194.0) and Appian platform, but some parameters may not
be valid.*

#### 1.2.0 {#120}

-   Removed `searchServerPassword` field. From Operator v0.181.0, and
    Appian platform versions hotfixed from July 03, 2025 or later, the
    Operator now manages the Search Server password for you. Manually
    specifying a Search Server password is no longer required nor
    recommended. If you previously configured a Search Server password,
    you must remove this from your `passwords.properties` file when
    upgrading to this version of the Helm chart (see [this
    KB](https://community.appian.com/support/w/kb/3582/kb-2322-application-server-fails-to-start-due-to-improperly-configured-search-server-credentials#:~:text=number%20of%20replicas.-,Operator%20v0.181.0%20and%20Later,-The%20following%20assumes)
    for more details).

*Built against Appian operator v0.181.0 and Appian platform 25.3. This
chart will work with older and newer versions of the Appian operator (to
a minimum of v0.181.0) and Appian platform, but some parameters may not
be valid.*

#### 1.1.3 {#113}

-   Fixed Search Server CPU requests for Medium t-shirt size to 200m.

*Built against Appian operator v0.178.0 and Appian platform 25.3. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

#### 1.1.2 {#112}

-   Fixed issue where setting `disableResourceRequests: true` removed
    resource requests altogether but left limits in place, resulting in
    Kubernetes automatically adding resource requests back in and set to
    the same values as the limits. Now, setting
    `disableResourceRequests: true` sets resource requests to `0` to
    prevent this.

*Built against Appian operator v0.173.0 and Appian platform 25.1. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

*Minimum operator version tested with this Helm chart is v0.159.0.*

#### 1.1.1 {#111}

-   Fixed issue where `webapp.engineOverrides` field could not be set as
    it was incorrectly defined as an array instead of an object.

-   Support setting `webapp.minHeapSize` to configure webapp\'s minimum
    heap size instead of using `customProperties`.

*Built against Appian operator v0.173.0 and Appian platform 25.1. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

*Minimum operator version tested with this Helm chart is v0.159.0.*

#### 1.1.0 {#110}

-   Minor increase to Search Server CPU requests for Small and Medium
    t-shirt sizes in-line with public docs update.

-   Added `dataServer.class` field to enable independent scaling of the
    Data Service component without changing global t-shirt size.

-   **Breaking Change** Aligned Data Service t-shirt sizing with latest
    public docs. This keeps resources relatively similar to earlier
    versions, but reduces RTS count for each t-shirt size. Use the new
    `dataServer.class` field or the `dataServer.rts.count` field to
    readjust if required.

-   **Breaking Change** CPU limits are no longer set by default. This is
    to align with K8s best practices (where accurate CPU limits for the
    specific usage scenario are not already known). CPU limits can be
    applied by setting the new field `disableCpuLimits` to `false` (it
    defaults to `true`). If enabled, the t-shirt size\'s CPU limits are
    applied. This can be overridden globally by setting the new field
    `defaultCpuLimits` or overridden per component by setting
    `[component].cpuLimits`. The field `workerNodeTotalCpu` has been
    removed in favour of `defaultCpuLimits`. Previous chart behaviour
    can be achieved by setting `disableCpuLimits` to `false` and setting
    `defaultCpuLimits` to the previous value of `workerNodeTotalCpu`.

-   **Breaking Change** Removed `serviceManager.cpuLimits` and
    `serviceManager.memoryLimits` fields. Use
    `serviceManager.default.cpuLimits` and
    `serviceManager.default.memoryLimits` instead.

-   `disableResourceRequests` now sets no `resources.requests` at all,
    rather than incorrectly setting them to `0`.

-   Deprecated `dataSources.mysqlDriverConfigMapName`, which enabled
    deploying the MySQL driver via a ConfigMap and webapp init
    container. The supported MySQL driver is now too large to be mounted
    via a ConfigMap. This field will be removed in a future version.

-   Fixed broken public docs links

*Built against Appian operator v0.173.0 and Appian platform 25.1. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

*Minimum operator version tested with this Helm chart is v0.159.0.*

#### 1.0.3 {#103}

-   Fixed an issue with the AGIC Ingress Template where an invalid
    `ingressClassName` was set. It now sets the annotation
    `kubernetes.io/ingress.class` instead, to the correct value, instead
    of setting `ingressClassName`.

-   AGIC Ingress Template now defaults `ingressTemplate.usePrivateIp` to
    `false` instead of `true`.

*Built against Appian operator v0.166.0 and Appian platform 24.4. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is v0.159.0.*

#### 1.0.2 {#102}

-   Allow `storage.haSharedData` to be specified when not in a high
    availability configuration

-   No longer enforces `passwordsPropertiesSecretName` to be set (as
    this need only be provided and loaded at first environment startup)

-   Support override of `serviceManager.replicas` in high availability
    configurations (from the default `3`)

*Built against Appian operator v0.166.0 and Appian platform 24.4. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is v0.159.0.*

#### 1.0.1 {#101}

-   Fixed bug preventing `ingress` from being used to completely
    override the templated ingress `ingressTemplate`

*Built against Appian operator v0.166.0 and Appian platform 24.4. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is v0.159.0.*

#### 1.0.0 {#100}

-   Fixed bug preventing `webapp.dataSources` from being used to
    completely override the templated data sources `dataSources.primary`
    and `dataSources.business`

-   Fixed bug where CPU and memory limits were not set for execution,
    analytics, groups, collaboration and process design engines when
    applying t-shirt sizes

-   Default value of the Data Service custom property
    `rts.queryMemoryLimits.circuitBreaker.threshold.bytes` automatically
    set based on RTS count

-   Added `webapp.customLoggers` to facilitate the addition of
    customized application logging

-   Added `metricsAuthToken` to enable Appian Self-Managed Monitoring
    metrics API

-   Added `cascadeVersionToComponentTags` for compatibility with the
    Appian Migration Tool

-   Built-in SMTP-related custom properties are only added by the chart
    if `smtp.host` is provided

-   `serviceManager.maxExecEngineLoadMetric` is now an integer
    (corrected from string)

-   `dataServer.rts.count` is now an integer (corrected from string)

-   `dataServer.rts.queryMemoryCircuitBreakerThresholdBytes` is now an
    integer (corrected from string)

*Built against Appian operator v0.166.0 and Appian platform 24.4. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is v0.159.0.*

#### 0.1.2 {#012}

-   Added `disableResourceRequests` for running on smaller, dedicated
    worker nodes

*Built against Appian operator v0.161.0 and Appian platform 24.3. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is v0.156.0.*

#### 0.1.1 {#011}

-   Supports new Search Server API password (introduced in 24.3)

-   Minor bug fixes

*Built against Appian operator v0.161.0 and Appian platform 24.3. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is now v0.156.0.*

#### 0.1.0 {#010}

First public release.

*Built against Appian operator v0.156.0 and Appian platform 24.1. This
chart will work with other versions of the Appian operator and platform,
both older and newer, but some parameters may not be valid (e.g.
`spec.rpa` was only introduced from v0.156.0).*

## License

Appian AppMarket (see
[here](https://community.appian.com/p/appmarket-faq#:~:text=How%20are%20Free%20Apps%20supported%3F))
