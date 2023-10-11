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
