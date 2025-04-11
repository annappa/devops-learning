## General
```shell
kubectl get pods

kubectl exec -ti babylon-database-5f45cbb9b7-qhzzb -- /bin/bash

kubectl describe pod babylon-database-5f45cbb9b7-wfrzj

kubectl get deployment,rs,pod

kubectl delete deployment babylon-database

kubectl delete deployment babylon-filestore-service

repos
cd babylon
kubectl apply -k ./kubernetes-manifests/application/overlays/local

repos
cd babylon-filestore-service
kubectl apply -k ./kubernetes-manifests/application/overlays/local
```

## Database
```shell
kubectl exec -ti babylon-database-5f45cbb9b7-qhzzb -- /bin/bash
cd /opt/mssql-tools/bin
./sqlcmd -S localhost -U aconexsql -P aconexsql
> use babylon;
> GO

> select * from dbo.filex_obs;
> GO

> select top 1 * from dbo.filex;
> GO
```