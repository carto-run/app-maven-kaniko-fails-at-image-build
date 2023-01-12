# app-maven-kaniko-fails-at-image-build

a maven/spring-boot application that uses kaniko to build the image, but fails.

## Creating the Workload

```
tanzu apps workload create app-maven-kaniko-fails-at-image-build \
  --namespace dev \
  --git-branch main \
  --git-repo https://github.com/carto-run/app-maven-kaniko-fails-at-image-build \
  --label apps.tanzu.vmware.com/has-tests=true \
  --label app.kubernetes.io/part-of=app-maven-kaniko-fails-at-image-build \
  --type web \
  --param dockerfile=./Dockerfile \
  --yes
```

## Logs

```
tanzu apps workload tail app-maven-kaniko-fails-at-image-build
```

## Configuration

| Item            | Config                                                                                |
| --------------- | ------------------------------------------------------------------------------------- |
| Scan Policy     | [default](resources/scan-policy.yaml)                                                 |
| Pipeline        | [developer-defined-tekton-pipeline](resources/developer-defined-tekton-pipeline.yaml) |
| tap-values.yaml | na                                                                                    |
| Supply Chain    | source-test-scan-to-url                                                               |

