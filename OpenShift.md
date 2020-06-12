# When deploying on OpenShift

Add the following to your deployment config when installing on openshift. File is also available in this repo.

```yaml
      env:
        - name: OUTPUT_DIR
          value: /public
        - name: YARN_ENABLED
          value: 'true'
```
