# Install with HelmChart Example
### Register Repo
```shell
helm repo add datadog https://helm.datadoghq.com
helm repo add grafana https://grafana.github.io/helm-charts
helm repo add kafka-lag-exporter https://seanglover.com/kafka-lag-exporter/repo/
helm repo add lensesio https://helm.repo.lenses.io/
helm repo update 
```

### Get the helm chart file
```shell
# check the version
helm search repo datadog
helm search repo -l grafana/grafana

# get a helm chart file
helm show values datadog/datadog > datadog.yaml
helm show values grafana/grafana --version 6.11.0 > grafana.yaml
```

### Install
```shell
helm install datadog datadog/datadog -f datadog.yaml
helm install grafana grafana/grafana -f grafana.yaml
```

### Update
```shell
helm upgrade datadog datadog/datadog -f datadog.yaml -n management
helm install grafana grafana/grafana -f grafana.yaml -n management
```