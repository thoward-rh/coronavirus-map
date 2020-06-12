# Covid React App for testing with OpenShift

This app was created following the great tutorial by Colby Faycock.
Link is here: <https://www.freecodecamp.org/news/how-to-create-a-coronavirus-covid-19-dashboard-map-app-in-react-with-gatsby-and-leaflet/>

# Deploy on OpenShift

To deploy on OpenShift, this should work right away on OpenShift 4.4 and above:

```bash
oc new-app nodeshift/ubi8-s2i-web-app:latest~https://github.com/thoward-rh/coronavirus-map --build-env YARN_ENABLED=true --build-env OUTPUT_DIR=/public
oc expose svc/coronavirus-map
```

If you deploy from the OpenShift console, then please make sure you add the following parameters in the build config:

```yaml
      env:
        - name: OUTPUT_DIR
          value: /public
        - name: YARN_ENABLED
          value: 'true'
```
