# My Helm Chart repo

Helm packages for my personal site.

This helm chart repo is hosted on Github pages. Packages are served from the docs directory in this repo.

See: https://github.com/helm/helm/blob/master/docs/chart_repository.md#github-pages-example

## Adding a new Helm package

Create helm chart
```
helm create go-vue-websockets
```
Create package artifact
```
helm package go-vue-websockets
```
Move package artifact to docs directory
```
mv go-vue-websockets-0.1.0.tgz docs
```
Update repo index
```
helm repo index docs --url https://cvasq.github.com/helm-charts
```
Track all new files
```
git add .
```
Commit and push
```
git commit -am "Add new chart"
git push origin master
```

## Using this Helm repo

Add the repo to helm
```
helm repo add cvasq https://cvasq.github.com/helm-charts
```

Verify it was created
```
helm repo list
```

View available packages in the repo
```
helm search cvasq

NAME                    CHART VERSION   APP VERSION     DESCRIPTION                
cvasq/go-vue-websockets 0.1.0           1.0             A Helm chart for Kubernetes
```

Install a helm chart from the repo
```
helm install cvasq/go-vue-websockets
```
