# Tekton Example
---
This directory contains the complete configurations for the Tekton Pipeline. You can make reference to the files stored here to build your own Tekton Pipeline. 

**Prereq**
# A ConfigMap to hold the maven-settings.xml which is required by `maven` Task
kubectl create cm maven-settings --from-file=settings.xml=Resources/maven-settings.xml 

# A dedicated sa for the pipeline
kubectl create sa tekton-pipeline 

# Run this if it's on OpenShift
oc adm policy add-role-to-user edit -z tekton-pipeline 
oc adm policy add-scc-to-user privileged -z tekton-pipeline 
