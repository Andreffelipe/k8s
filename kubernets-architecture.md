## Definição de um pod 

```yaml
apiVersion: v1
kind: Pod
metadata:
    name: nginx-pod
    labels:
        app: myapp
spec: 
    containers:
        - name: nginx-container
          image: nginx
```
* apiVersion => definição da versão da API Kubernetes.
* kind => tipo de implementação
* metadata name => nome do pod
* metadata labels => usado para agrupar pods
* spec 

# Versão da apiVersion

```
$ kubectl api-resources
```

# Aplicando o aquivo .yaml

```
$ kubectl apply -f pod-definition.yaml
```
# Ver os pods implementados
```
$ kubectl get pods
```
# Ver detalhes do pods
```
$ kubectl describe pod meupod
```
# Deletar um pod
```
$ kubectl delete pod meupod
```
# Escalonar mais pods no replicaset
```
$ kubectl scale replicaset/meureplicaset --replicas=10
``` 
# Deletar replicaset
```
$ kubectl delete replicaset meureplicaset
```
# trocar versão da apiVersion
```
$ kubectl set image deployment/meudeployment webapi=fabricioveronez/metricas-api:v2
```
# Desfazendo alteração da versão anterior
```
$ kubectl rollout undo deployment/meudeployment
```

# Redirecionamento de porta 

```
kubectl port-forward pod/meupod 8080:80
```

replicaset => escalabilidade e resiliencia
deployment => atualização

services
    clusterIp
        - comunicação interna no cluster
    nodePort
        - 
    loadBalancer
        - 