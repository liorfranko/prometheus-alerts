## prometheus-alerts chart
This chart is built to maintain prometheus alerts accross multiple clusters, by utilizing Helm's multiple values files.

## Examples
### Disable alert
Having the following values file `override-values.yaml`:
```
PrometheusAlerts:
    prometheus-alerts:
        PrometheusAllTargetsMissing:
            enabled: false
```
Running the following command will deploy all the alerts beside `PrometheusAllTargetsMissing`:

```
helm template . --values override-values.yaml
```

### Override alert
Having the following values file `override-values.yaml`:
```
PrometheusAlerts:
    k8s-node-alerts:
        HostHighCpuLoadWarning:
            for: 60m
```
Running the following command will deploy all the default alerts and `HostHighCpuLoadWarning` will alert after `60m` instead of `30m`  :

```
helm template . --values override-values.yaml
```