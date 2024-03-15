# Recursos de infra para o App do framework Nextjs

- Git: `https://github.com/raphac-mar/03-app-k8s`

- O Argo CD não cria o PipelineRun
- "resourceExclusions": "- apiGroups:\n  - tekton.dev\n  clusters:\n  - '*'\n  kinds:\n  - TaskRun\n  - PipelineRun        \n",

```
resourceExclusions: |
    - apiGroups:
      - tekton.dev
      clusters:
      - '*'
      kinds:
      - TaskRun
      - PipelineRun
```

## Branch's

- dev
- homolog
- prod

## Argo CD

```sh
cd 03-app-k8s/admin-dashboard
oc apply -f argocd/application.yaml

oc delete ApplicationSet admin-dashboard -n openshift-gitops
```

https://developers.redhat.com/articles/2023/02/20/multiple-sources-argo-cd-applications#examples_of_multiple_sources_applications
https://developers.redhat.com/articles/2023/05/25/3-patterns-deploying-helm-charts-argocd?source=sso#
