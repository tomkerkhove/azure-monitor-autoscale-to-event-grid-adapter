# Azure Event Grid adapter for Azure Monitor Autoscale

Bring Azure Monitor Autoscale events to Azure Event Grid with this adapter.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Ftomkerkhove%2Fazure-monitor-autoscale-to-event-grid-adapter%2Fprovide-template%2Fdeploy%2Fazuredeploy.json%3Ftoken%3DABBE6P7H5UGZSWVS67TSABTAFQL46)

## Supported Events

- Scale In Activated
- Scale Out Activated

### Scale In Activated

**Event Type:** `Azure.Monitor.Autoscale.ScaleIn.Activated`

**Payload:**
```json
{
    "specversion": "1.0",
    "type": "Azure.Monitor.Autoscale.ScaleIn.Activated",
    "id": "A234-1234-1234",
    "subject": "/autoscalesettings/{autoscale-rule-name}",
    "source": "azure-monitor-autoscale-to-event-grid-adapter",
    "time": "2018-04-05T17:31:00Z",
    "datacontenttype": "application/json",
    "data": {
        "name": "{autoscale-rule-name}",
        "details": "Autoscale successfully started scale operation for resource '{resource-name}' from capacity '2' to capacity '1'",
        "capacity": {
            "new": 1,
            "old": 2
        },
        "scaleTarget": {
            "subscriptionId": "{subscription-id}",
            "resourceGroupName": "{resource-group-name}",
            "resource": {
                "id": "/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}/providers/{resource-type}/{resource-name}",
                "type": "{resource-type}",
                "name": "{resource-name}",
                "region": "{region-name}",
                "portalLink": "https://portal.azure.com/#resource/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}/providers/{resource-type}/{resource-name}"
            }
        }
    }
}
```

### Scale Out Activated

**Event Type:** `Azure.Monitor.Autoscale.ScaleOut.Activated`

**Payload:**
```json
{
    "specversion": "1.0",
    "type": "Azure.Monitor.Autoscale.ScaleOut.Activated",
    "id": "A234-1234-1234",
    "subject": "/autoscalesettings/{autoscale-rule-name}",
    "source": "azure-monitor-autoscale-to-event-grid-adapter",
    "time": "2018-04-05T17:31:00Z",
    "datacontenttype": "application/json",
    "data": {
        "name": "{autoscale-rule-name}",
        "details": "Autoscale successfully started scale operation for resource '{resource-name}' from capacity '1' to capacity '2'",
        "capacity": {
            "new": 2,
            "old": 1
        },
        "scaleTarget": {
            "subscriptionId": "{subscription-id}",
            "resourceGroupName": "{resource-group-name}",
            "resource": {
                "id": "/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}/providers/{resource-type}/{resource-name}",
                "type": "{resource-type}",
                "name": "{resource-name}",
                "region": "{region-name}",
                "portalLink": "https://portal.azure.com/#resource/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}/providers/{resource-type}/{resource-name}"
            }
        }
    }
}
```
