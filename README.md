## How to run

Start Minikube with minikube start

## Create the configmap

kubectl apply -f cm1.yaml

## Run integration

jbang --fresh -Dcamel.jbang.version=4.9.0-SNAPSHOT camel@apache/camel run --logging-level=DEBUG --properties=application.properties timer-kubernetes-configmap.yaml

## Modify the cm1.yaml

Change some field like username and run

kubectl apply -f cm1.yaml

Notice that the Reload Trigger task doesn't start at all and there is no trace of it in the Debug log.
