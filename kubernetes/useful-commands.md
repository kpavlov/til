
# Useful kubernetes commands

## Get information about pods

Get pod names, filtered by label `app=my-service`:

    kubectl get pods --selector=app=my-service -o=name

Get information about pods with label `app=my-service`, output in YAML format:

    kubectl get pods --selector=app=my-service -o yaml

Get pod names, images, statuses and readiness, filtered by label `app=my-service`:

    kubectl get pods --selector=app=my-service \
        -o=custom-columns=NAME:.metadata.name,IMAGE:.status.containerStatuses[*].image,STATUS:.status.phase,READY:.status.containerStatuses[*].ready
example:   
```log
$ kubectl get pods --selector=app=my-service \
    -o=custom-columns=NAME:.metadata.name,IMAGE:.status.containerStatuses[*].image,STATUS:.status.phase,READY:.status.containerStatuses[*].ready
NAME                          IMAGE                                           STATUS    READY
my-service-1229220694-9brdk   registry.acme.com/my-service:1.5.1-1515502758   Running   true
my-service-1229220694-vdmpp   registry.acme.com/my-service:1.5.1-1515502758   Running   true
```  

# Configuring ConfigMaps 

    kubectl create configmap my-service \
        --from-literal=DATASOURCE_URL='jdbc:mysql://localhost:3306/mydb' \
        --from-literal=MY_ENVIRONMENT='Dev' \
        -o yaml --dry-run | kubectl apply -f -
    
## Links:

- [kubectl: output options / custom colmns](https://kubernetes.io/docs/reference/kubectl/overview/#custom-columns)
