# When deploying on OpenShift

Add the following to your build config when installing on openshift. File is also available in this repo.

```yaml
      env:
        - name: OUTPUT_DIR
          value: /public
        - name: YARN_ENABLED
          value: 'true'
```

You can deploy using the following commands:

```bash
oc new-app https://github.com/thoward-rh/coronavirus-map --build-env YARN_ENABLED=true --build-env OUTPUT_DIR=/public
oc expose svc/coronavirus-map
```
