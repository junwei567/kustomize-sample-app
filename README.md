# Deploy to OpenShift with Kustomize

This is a sample web application that uses Kustomize to deploy to different environments (production and staging).

## Deploy to your cluster

To deploy, run the following:

`oc apply -k overlays/staging`

`oc apply -k overlays/production`

## Implement the pipeline to your cluster

1. Install Red Hat Openshift Pipelines operator.

2. Install the relevant tasks needed from Tekton hub.

Tasks:

`oc apply -k https://raw.githubusercontent.com/tektoncd/catalog/main/task/git-clone/0.6/git-clone.yaml`

