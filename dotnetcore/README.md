### Prepare Container

## Create Jenkins Pipeline image
```
docker build -t sonarscanner .
docker tag sonarscanner <<OPENSHIFT_DOCKER_REGISTRY>>/openshift/dotnet-21-sonar-jenkins-slave-rhel7:latest
docker push <<OPENSHIFT_DOCKER_REGISTRY>>/openshift/dotnet-21-sonar-jenkins-slave-rhel7
```
## Create Objects
```
oc replace --force -f dotnet-jenkins-slave
oc replace --force -f dotnet-pipeline.yaml
```