### Run your first app on kubernet:


```
kubectl create -f helloworld.yml 
```

```
kubectl get deployment
```

Output:

```
NAME                    READY   UP-TO-DATE   AVAILABLE   AGE
helloworld-deployment   3/3     3            3           5m25s
```

```
kubectl get rs
```

Output:

```
NAME                               DESIRED   CURRENT   READY   AGE
helloworld-deployment-7b8f5b89bd   3         3         3       6m25s
```


### status of deployment:


```
kubectl rollout status deployment/helloworld-deployment
```
output:

```
deployment "helloworld-deployment" successfully rolled out
```

### Change image:

```
kubectl set image deployment/helloworld-deployment k8s-demo=cmaliwal/docker-demo:2
```

output:

```
deployment.extensions/helloworld-deployment image updated
```

```
kubectl rollout status deployment/helloworld-deployment
```

Output:

```
deployment "helloworld-deployment" successfully rolled out
```


### Expose port:

```
kubectl expose deployment helloworld-deployment --type=NodePort
```

Output:

```
service/helloworld-deployment exposed
```

```
minikube service helloworld-deployment --url
```

Output:

```
http://192.168.99.101:32659
```

```
curl http://192.168.99.101:32659
```

output:

```
Hello World!
```
