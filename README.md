# Mobile CI/CD Workshop

## Usage on Local Docker
```
$ docker run -p 8080:8080 \
    -v /Users/eshortis/workspaces/mobile/workshops/mobile-buildfarm-lab:/app-data \
    -e CONTENT_URL_PREFIX="file:///app-data" \
    -e WORKSHOPS_URLS="file:///app-data/workshop.yml" \
    osevg/workshopper:latest
```

## Usage on OpenShift
```
$ oc new-app osevg/workshopper:latest --name=mobile-workshop \
    -e CONTENT_URL_PREFIX=https://raw.githubusercontent.com/evanshortiss/mobile-buildfarm-lab/master \
    -e WORKSHOPS_URLS=https://raw.githubusercontent.com/evanshortiss/mobile-buildfarm-lab/master/workshop.yml
$ oc expose svc/mobile-workshop
```