ToDo Challenge that involves all exercises

1 Dockerfiles
```
Make a Dockerfile fill with:

LABEL algo=pepe
ENV foo=myenv
EXPOSE 3 PORTS
COPY ./dir /dir
RUN unzip del copy /dir (the .zip is in another directory, copy with gui files to the Dockerfile dir)

Make a build and tag with some label
```

2 Containers with local resources
```
Modify a script to make a podman run with a volume that is with permisions already, especific port, label
```
3 Communicating between containers
```
Modify a script to make sudo podman run -d -e -e  envs --pod -p port image
Modify another script to make sudo podman run -d -e -e alot's envs  -p port image
Test comunication between containers
```
4 Managing images
```
Make a build, tag, save, load and push to a registry.

build
tag 
save
load
push to testregistry
```

5. Managing OCP projects
```
ToDo
```
6. New app from template on OCP
```
Make a service from a template.
The template is in a directory and also in openshift namespace
Tag all resourses with a label
oc process -f file.yaml -p POSTGRES_DB=testdb -p POSTGRES_USER=test -p POSTGRES_PASSWORD=redhat  -p POSTGRES_SERVIC=test -l foo=test |oc create -f -
```
7. New app from image on OCP
```
Make a new project named test with display name foo
Make a app with name foo-name from image (test.com/ex180/image)
With this env MYSQL_USER=user1,MYSQL_PASSWORD=mypa55,MYSQL_DATABASE=do180,MYSQL_ROOT_PASSWORD=r00tpa55
Expose svc with custom name www.custom.com
Test

oc new-project test --display-name="foo"
oc new-app --name foo-name --docker-image=test.com/ex180/image -e MYSQL_USER=user1 -e MYSQL_PASSWORD=mypa55 -e MYSQL_DATABASE=do180 -e MYSQL_ROOT_PASSWORD=r00tpa55 
oc expose svc pepe --hostname=www.custom.com
curl www.custom.com
```
8 Multiple app on OCP
```
New app from this git https://github.com/${RHT_OCP4_GITHUB_USER}/DO180-apps, with this dir nodejs-dir, nodejs12 and with this env MYSQL_USER=user1 -e MYSQL_PASSWORD=mypa55 -e MYSQL_DATABASE=do180  name do180-p6
with this env  npm_config_registry=http://${RHT_OCP4_NEXUS_SERVER}/repository/npm-proxy

oc new-app --as-deployment-config nodjs:12 --name=do180-p6 https://github.com/${RHT_OCP4_GITHUB_USER}/DO180-apps  --context-dir --build-env  npm_config_registry=http://${RHT_OCP4_NEXUS_SERVER}/repository/npm-proxy nodejs-dir  

Make a mysql app with this envs MYSQL_USER=user1 -e MYSQL_PASSWORD=mypa55 -e MYSQL_DATABASE=do180 -e MYSQL_ROOT_PASSWORD=r00tpa55 from image test.com/ex180/image
oc new-app --name foo-name --docker-image=test.com/ex180/image -e MYSQL_USER=user1 -e MYSQL_PASSWORD=mypa55 -e MYSQL_DATABASE=do180 -e MYSQL_ROOT_PASSWORD=r00tpa55 

Expose route 
Test with curl
```
9 Troubleshooting apps on OCP
```
Make 3 scripts to:

Get last 10 logs
oc log --tail 10 pod-name
oc log --tail 10 $(oc get pods |grep podname)

Copy files to pod
oc cp /home/pepe/carpeta pod:/work/tools

Exec an script and show it 
oc exec -ti pod-name /work/tools/script.sh

```


