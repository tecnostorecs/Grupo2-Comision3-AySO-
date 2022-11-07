# TP-AySO-2022
Requirements:
-------------

	>Crear k8s cluster con minikube k3s o kind.
	>Crear dockerfile con nginx y donde copie un index.html diga “Hola mundo, somos el grupo 2 de la UTN”.
	>Buildear y pushear dicha imagen con el tag v1 a hub.docker.com
	>Crear namespace que se llame grupo2
	>Crear un Replicaset in kubernetes en el ns que se creo anteriormente: Requisitos, debe tener 2 replicas, y debe levantar la imagen de nginx previa.
	>Subir todo el codigo a github.
	>Crear README.

Tips:
-----
	>No olvidar .gitignore y .dockerignore files .
	>Usar imagenes alpine o stables.
	>Probar todo local antes de pushear a git.
	
INTRODUCTION

once we enter the console we create the folder "TP DE KUBERNETES GRUPO2" to work with it <br>
<br>
we are able to find the folder fllowing the next commands to see the path in our system: <br>
pwd <br>
/home/solchuuu <br>
cd TP DE KUBERNETES GRUPO2 

1) create INDEX.HTML <br>
sudo vim index.html

2) create DOCKERFILE <br>
sudo vim Dockerfile

3) once we have this file, we are able to build an image with the tag "v1" <br>
docker build --tag v1 .

4) create a container to test te image <br>
docker run -d -p 8080:80 --name grupo2 v1

5) once the container is created we can test the image with the port <br>

6) once the dockerhub user is created <br>
docker tag v1:latest tecnostorecs/grupo2-tup:v1

7) push the image on dockerhub <br>
docker push tecnostorecs/grupo2-tup:v1

8) create .YAML FILE <br>
vim docker-prueba.yaml

9) create K8S cluster <br>
minikube start --driver=docker

10) create the alias of kubectl, now minikube recognize the kubectl command <br>
alias kubectl="minikube kubectl --"

11) create namespace <br>
kubectl create ns grupo2

12) aplly the changes <br>
kubectl apply -f docker-prueba.yaml

13) check the status of the replicaset by opening the dashboard <br>
minikube dashboard
