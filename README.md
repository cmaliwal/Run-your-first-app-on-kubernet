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