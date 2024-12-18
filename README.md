# Rapidast for WTO


## Scan for APIs
After using https://github.com/jeremychoi/get-k8s-openapi-docs, the APIs determined to scan were:
```
apidocs/api-controller.devfile.io-v1alpha1-openapi.json
apidocs/api-workspace.devfile.io-v1alpha1-openapi.json
apidocs/api-workspace.devfile.io-v1alpha2-openapi.json
```

## Running RapiDAST

RapiDast was run using podman:
```
podman run -v ./kubeconfig:/home/rapidast/.kube/config:Z -v ./config.yaml:/opt/rapidast/config/config.yaml:Z quay.io/redhatproductsecurity/rapidast:latest /bin/bash -c "./rapidast.py && echo Done! && tail -f /dev/null"
```

Results were retrieved using `podman cp`:
```
podman cp <container id>:/opt/rapidast/results/ocptest/<DAST folder path> <dest folder path>
```

## Results

Results for the passive scan, `Kubernetes-API-scan` scan and `API-scan-minimal` scan are available [here](https://drive.google.com/drive/folders/1Ixv07vbsw7mfBu1EzdXkqPN4Y6TXmN_q).