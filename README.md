# Logs
### web-api
```bash
kubectl -n dotdata logs -f --tail=10 "$(kubectl -n dotdata get pods -l component=web-api -o name)"
```

### ICS
```bash
kubectl -n dotdata logs -f --tail=10 "$(kubectl -n dotdata get pods -l component=interactive-computation-server -o name)"
```

# Port forward
## JMX
### web-api
```bash
kubectl -n dotdata port-forward --address=0.0.0.0 service/interactive-computation-server-service 9875:9875
```

### process-manager
```bash
kubectl -n dotdata port-forward --address=0.0.0.0 service/process-manager 9874:9874
```

### ICS
```bash
kubectl -n dotdata port-forward --address=0.0.0.0 service/interactive-computation-server-service 9876:9876
```

## Admin console
### ICS
```bash
kubectl -n dotdata port-forward --address 0.0.0.0 service/interactive-computation-server-service 8443:8443
```