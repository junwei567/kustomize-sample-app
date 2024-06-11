# Deploy to OpenShift with Kustomize

This is a sample web application that uses Kustomize to deploy to different environments (production and staging).

## Deploy to your cluster

To deploy, run the following:

`oc apply -k overlays/staging`

`oc apply -k overlays/production`

Tasks:

`oc apply -k https://raw.githubusercontent.com/tektoncd/catalog/main/task/git-clone/0.6/git-clone.yaml`
