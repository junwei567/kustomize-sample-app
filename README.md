# Deploy to OpenShift with Kustomize

This is a sample web application that uses Kustomize to deploy to different environments (staging and production).

Clone the repo to get started!

## Deploy to your cluster

To deploy, run the following:

`oc apply -k overlays/staging` for staging environment.

`oc apply -k overlays/production` for production environment.

## Implement the pipeline to your cluster

1. Install Red Hat Openshift Pipelines operator.

2. Install the relevant tasks needed from Tekton hub.

Tasks:

`oc apply -f https://raw.githubusercontent.com/tektoncd/catalog/main/task/git-clone/0.6/git-clone.yaml`

`oc apply -f https://raw.githubusercontent.com/tektoncd/catalog/main/task/maven/0.3/maven.yaml`

`oc apply -f https://raw.githubusercontent.com/tektoncd/catalog/main/task/buildah/0.7/buildah.yaml`

`oc apply -f https://raw.githubusercontent.com/tektoncd/catalog/main/task/openshift-client/0.2/openshift-client.yaml`

3. Provision for the Persistent Volume Claims

`oc apply -f pipeline/pvc.yaml`

4. Run the pipeline

`oc apply -f pipeline/pipeline.yaml -f pipeline/pipeline-run.yaml`