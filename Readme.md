## Steps to pull in and package external chart

**Pull in chart using helm to the releases directory:**

```
helm pull bitnami/nginx --version 20.0.0 --destination ./releases
```


**Untar into charts directory:**

```
tar -xzf ./releases/nginx-20.0.0.tgz -C charts/nginx/20.0.0 --strip-components=1
```

## Make custom changes to chart and package new release:

```
cd ./charts/nginx
helm package . -d ../../releases/
```



## Create index file using helm

```
helm repo index releases/ --url https://raw.githubusercontent.com/daveschmidt86/test_helm_repo/main/releases

```
