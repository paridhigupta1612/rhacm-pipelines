--RACHNA DODIA BOOKINFO APP---
> oc new-project bookinfo-cicd

>  oc get serviceaccount pipeline

> cd onecluster-multiple-envs/tekton

> oc create -f tasks/01_create_namespaces.yaml

> oc create -f tasks/02_create_dev_app_using_acm.yaml

> oc apply -f tasks/03_create_qa_app_using_acm.yaml

> oc apply -f tasks/04_create_prd_app_using_acm.yaml

> oc adm policy add-cluster-role-to-user cluster-admin system:serviceaccount:bookinfo-cicd:pipeline

> oc apply -f pipeline-acm.yaml

> oc apply -f prepare/tekton-source-pvc.yaml

> oc apply -f pipelinerun.yaml
