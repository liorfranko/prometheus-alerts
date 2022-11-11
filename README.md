## prometheus-alerts chart
This chart is built to maintain prometheus alerts accross multiple clusters, by utilizing Helm's multiple values files.

## Example
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