### HELM

We use **HELM** in real time for 2 purposes.
* Parameterize our application manifest files to supply image version, number of replicas, etc. at runtime.
* As package manager to install the opensource applications into Kubernetes cluster.

Helm important files are

* Chart.yaml
* templates folder
* values.yaml

#### Chart.yaml

This file is to supply metadata for helm. We need to give apiVersion, chartname, chart version, etc through this file.
**NOTE:** Make sure you increase the chartVersion and appVersion every time we do the change.

#### templates folder

Here we keep all the required Kubernetes resource YAML files. We can use placeholders inside the files.

#### values.yaml

This file is used to supply the default values to the placeholders of resources files in templates folder.

Create the above files to convert any Kubernetes manifest into HELM.

To install Helm chart. make sure you are in the directory where Chart.yaml is there

```
helm install [any-name-you-prefer] .
```

to list the charts running

```
helm list
```

to upgrade

```
helm upgrade [chart-name] .
```

to rollback

```
helm rollback [chart-name] [revision-no]
```

to list all revision numbers

```
helm history [chart-name]
```
to delete

```
helm delete/uninstall [chart-name] 
```

to supply your own values.yaml

```
helm install [chart-name] . --values=[path-of-your-values.yaml]
```

### Helm as package manager

We can use helm as package manager just like yum, apt-get, etc. It can bring the open source charts from internet and install inside kubernetes cluster.

to add open source repos

```
helm repo add [repo-name] [URL]
```

to search

```
helm search repo [name]
```

