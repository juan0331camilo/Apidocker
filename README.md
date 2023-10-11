# despliegue de aplicacion Docker , Web api .NET

EJECUCION 

PASO 1 
Clonar el repositorio 
https://github.com/juan0331camilo/Apidocker.git
cd WebApi.Docker
paso 2 
Crear la Imagen docker

$ docker build -t dotnet:v0.0.1 .
$ Docker images

paso 3
ejecutar la imagen en docker

docker run -p 8080:80 dotnet:v0.0.1 .

paso 4 
acceder a la url que se esta ejecutando en la consola de comandos o la puedes acceder desde  Dockerdesktop
 http://localhost:8080/swagger

 
![captura](https://github.com/juan0331camilo/Apidocker/assets/54645813/44916f35-02b6-4c37-a65b-21b3e4dfb6f8)

paso 5 
desarrollar un Pipeline y publicar en docker hub -->  para ver el pipeline dirijase  a la carpeta .github/workflow

![dockerhub](https://github.com/juan0331camilo/Apidocker/assets/54645813/19066fd7-f2ea-4d80-973c-5cf556da2295)

paso 6 
ejecutar el contenedor a partir de la imagen publicada en dockerhub
docker run -p 8080:80 dotnet:v0.0.1 .

DESPLIEGUE DE API en Kubernetes

paso 1
abrir power shell como administrador 
y ejecutar los siguientes comandos
$ start minikube
$ minikube dashboard
![minikube](https://github.com/juan0331camilo/Apidocker/assets/54645813/bbd387e2-459a-453a-ae68-717b25867e2d)

paso 2 
ejecutar el archivo deployment.yaml
kubectl apply -f dotnet-deployment.yaml 

![desplieguekubernetes](https://github.com/juan0331camilo/Apidocker/assets/54645813/79a9a0b8-993f-4f9a-b932-90dca354a05a)

paso 3 
ejecutar el archivo service.yaml
$ kubectl apply -f dotnet-service.yaml 


![services_minikube](https://github.com/juan0331camilo/Apidocker/assets/54645813/2250cb88-8e92-4964-9f8b-8b0c7af799b8)

paso 4 
escribe el siguiente comando para verificar la url 
minikube service dotnet-service --url

![desplieguekubernetes](https://github.com/juan0331camilo/Apidocker/assets/54645813/cb097a5b-d18d-44e6-9b34-857e5f2964cd)

![kubernetes_general](https://github.com/juan0331camilo/Apidocker/assets/54645813/f419ed10-ca8a-46c1-ac0d-add1754f6991)

