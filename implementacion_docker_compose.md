# Examen Final
Proyecto final de arquitectura web enfocado en recrear el ejercicio desarrollado en https://learn.microsoft.com/es-es/azure/container-instances/tutorial-docker-compose?source=recommendations , donde se implementa una aplicación  básica de votaciones mediante DevOps. Para ello se  implementa un componente web front-end y una instancia back-end de Redis. El componente web se empaqueta en una imagen de contenedor personalizada. La instancia de Redis usa una imagen sin modificar de Docker Hub
## Instalación del CLI de azure
Se hizo la respectiva descarga de Azure CLI para poder utilizar los comandos dentro de nuestro computador.

![Captura de pantalla 2022-11-24 125332](https://user-images.githubusercontent.com/88751751/203849324-5f3f7876-291b-4791-a099-b847080cf416.png)

Verificación de Instalación:

* Ejecutamos el comando: az --version

![Captura de pantalla 2022-11-24 134547](https://user-images.githubusercontent.com/88751751/203849755-35d6d330-528c-4adf-84e7-64410d3e13c4.png)

Configuración de suscripción de estudiantes en Portal Azure:

![Captura de pantalla 2022-11-24 135008](https://user-images.githubusercontent.com/88751751/203850174-f764f6ee-9b73-4129-943c-9c432ed4294d.png)

Configuración de acceso y suscripción en Cli Azure:

* Ejecutamos el comando: az login

![Captura de pantalla 2022-11-24 135321](https://user-images.githubusercontent.com/88751751/203850464-8bc913b0-64ac-42de-9c8a-c67fa0c67f5a.png)

## Creación de una instancia de Azure Container Registry

Creación de grupo de recursos

* Ejecutamos el comando: az group create --name myResourceGroup --location eastus

![Captura de pantalla 2022-11-24 135433](https://user-images.githubusercontent.com/88751751/203850616-2703ec9f-653f-4b49-9dca-8351d0af32bc.png)

Creación de registro de contenedor de Azure

* Ejecutamos el comando: az acr create --resource-group myResourceGroup --name <acrName> --sku Basic

![Captura de pantalla 2022-11-24 135705](https://user-images.githubusercontent.com/88751751/203850954-be001fde-2b29-4479-918b-8f7e65086dfd.png)
  
Iniciar sesión en el contenedor creado
  
* Ejecutamos el comando: az acr login --name examenFinal
  
![Captura de pantalla 2022-11-24 140520](https://user-images.githubusercontent.com/88751751/203851646-c2f7caaf-2397-44bf-a0f7-01333f902fb2.png)

Clonación de repositorio de la aplicación de voto.
  
* Ejecutamos el comando: git clone https://github.com/Azure-Samples/azure-voting-app-redis.git
 
![Captura de pantalla 2022-11-24 140939](https://user-images.githubusercontent.com/88751751/203852189-e1def60a-b60a-4300-a6ab-53bedcb3f817.png)

Se modifica el archivo docker-compose en un editorde texto para que funcione con el registro creado anteriormente. El archivo configura los servicios azure-vote-back y azure-vote-front.

```
version: '3'
services:
  azure-vote-back:
    image: mcr.microsoft.com/oss/bitnami/redis:6.0.8
    container_name: azure-vote-back
    environment:
      ALLOW_EMPTY_PASSWORD: "yes"
    ports:
        - "6379:6379"

  azure-vote-front:
    build: ./azure-vote
    image: mcr.microsoft.com/azuredocs/azure-vote-front:v1
    container_name: azure-vote-front
    environment:
      REDIS: azure-vote-back
    ports:
        - "8080:80"
```
  
  ![Captura de pantalla 2022-11-24 141321](https://user-images.githubusercontent.com/88751751/203852557-7921c8a2-08e7-43c3-97df-e107930f4733.png)

Se compila el archivo docker-compose.
  
* mediante el comando: docker-compose up --build -d

  ![Captura de pantalla 2022-11-24 141632](https://user-images.githubusercontent.com/88751751/203852740-e31e1a03-c3e4-4390-be1e-71c860bd548d.png)
![Captura de pantalla 2022-11-24 141714](https://user-images.githubusercontent.com/88751751/203852774-eb57c403-7cdf-4eca-bd5e-7877f930abe4.png)

Se comprueba que la imagen haya sido creada correctamente
  
* Ejecutar el comando: docker images
  
  ![Captura de pantalla 2022-11-24 142309](https://user-images.githubusercontent.com/88751751/203853397-f85eeba3-db28-480e-82cf-8cccd565eff6.png)

 Se comprueba que los contenedores se estén ejecutando
 
  * Ejecutar el comando: docker ps
  
 ![Captura de pantalla 2022-11-24 142540](https://user-images.githubusercontent.com/88751751/203854122-8d4236f3-5111-4fc4-90f7-fe5122842bed.png)

Comprobación de funcionamiento de la aplicación

  ![Captura de pantalla 2022-11-24 142737](https://user-images.githubusercontent.com/88751751/203854236-04210263-f418-4e25-b3da-2e89d0a93e73.png)

  Inserción de las imágenes de docker en Container Registry.
  
* Mediante el comando: docker-compose push
  
  ![Captura de pantalla 2022-11-24 142958](https://user-images.githubusercontent.com/88751751/203854454-2e34d98b-31f8-4249-bb7b-178221a333df.png)

Logueo de docker en Azure
  
* Ejecutando el comando: docker login azure
  
  ![Captura de pantalla 2022-11-24 143256](https://user-images.githubusercontent.com/88751751/203854671-40d55df0-3c89-4daa-9467-1d8568221458.png)
  
Creación de un contexto de Azure
  
* Ejecutando el comando: docker context create aci myacicontext
  
  ![Captura de pantalla 2022-11-24 143651](https://user-images.githubusercontent.com/88751751/203854964-be4ec668-4113-490c-9826-b71bc335f8ec.png)
  

 Confirmar que agregó el contexto de ACI a los contextos de Docker
* Ejecutando el comando: docker context ls
  
  ![Captura de pantalla 2022-11-24 143841](https://user-images.githubusercontent.com/88751751/203855111-51bfc161-f1a6-4fa1-acaf-4b552011071f.png)

