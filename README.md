# snappass in k8s

Build
```
ansible-bender build snappass.yml
```

Push
```
buildah login quay.io

buildah push 345d863f2225 quay.io/tonyskapunk/snappass
buildah push 345d863f2225 docker-daemon:snappass:latest
```

Run
```
kubectl create -f redis.yml
kubectl create -f snappass.yml
```

Test
```
kubectl port-forward pod/snappass 8080:5000
```
