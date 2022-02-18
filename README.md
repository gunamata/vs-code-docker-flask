# python flask app example

This sample demonstrates the deployment of a simple python flask app to the kubernetes cluster within Rancher Desktop.

## Steps

Once Rancher Desktop is successfully installed and app started, Run below commands in a terminal.

```
docker build -t "simple-flask-app:v1.0" .
kubectl run --image simple-flask-app:v1.0 flaskapp
kubectl get pods
kubectl port-forward pods/flaskapp 5000:5000

or


nerdctl --namespace k8s.io build -t simple-flask-app:v1.0 .
nerdctl --namespace k8s.io run -p 5000:5000 -it simple-flask-app:v1.0

```
Run below api end points in a browser or a tool like postman

```
http://localhost:5000
http://localhost:5000/test

```
