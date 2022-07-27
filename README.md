# Debug Pod
Simple pod spec to quickly spin up a pod in a Kubernetes cluster

## Start a simple nginx pod

```
oc run nginx --image=nginx --port=80 --restart=Never -n openshift-nfd
```

## Create a simple deployment yaml

```
oc create deployment --image nginx nginx --dry-run=client -o yaml > deployment.yaml
```

## Sample pod manifest

```
kind: Pod
apiVersion: v1
metadata:
  name: nginx
  namespace: jude-test
  labels:
    run: nginx
spec:
  restartPolicy: Never
  containers:
    - name: nginx
      image: nginx
      imagePullPolicy: Always
      ports:
        - containerPort: 80
          protocol: TCP
```
