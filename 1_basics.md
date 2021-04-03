# Basics

## Create an alias to kubectl

> `alias k="kubectl"`

- this should save you time from retyping kubectl over and over again

## Add auto completion to the online terminal

> `source <(kubectl completion bash)`

- less errors, this does not support `k` tho so be warned

## Creating stuff

> `kubectl create ns <ns-name>`

- creates a new namespace

> `kubectl create deployment examplehttpapp --image=katacoda/docker-http-server`

> `kubectl create deployment namespacedeg -n <ns-name> --image=katacoda/docker-http-server`

- creates a deployment in the specified namescpace

## Get deployments, pods, etc.

> `kubectl get namespaces` or `kubectl get ns`

- this contains the "environment where your work at"
- `ns` or `namescpaces` works

> `kubectl get pods -n kube-system`

- the pods reponsible for managing the other pods

> `kubectl get deployments`

> `kubectl get pods`

- this gets the pod from the current namespace

> `kubectl get pods -o wide`

- pods with extra info
- adds IP, NODE, NOMINATED ODE, READINESS GATES

> `kubectl get pods -n <ns-name>`

- get the pods from a specific namespace

## Describing pods

> `kubectl describe pod <pod-name>`

- get the pod name from the commands above
- returns the information as well as events that happened on the pod
- auto complete works here

## Updating deployments and pods

> `kubectl edit deployment examplehttpapp`

- lets you modify the deployment yaml
- immediately takes effect

> `kubectl scale deployment examplehttpapp --replicas=5`

- updates the number of pods of a deployment

> `kubectl --record=true set image deployment examplehttpapp docker-http-server=katacoda/docker-http-server:v2`

- this udpated the image of the deployment to the specified version
- notice additional `:v2`

## Apply changes

> `kubectl rollout status deployment examplehttpapp`

- checks the status of a rollout

> `kubectl rollout undo deployment examplehttpapp`

- reverses the edit by 1 change
