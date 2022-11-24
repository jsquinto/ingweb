# Examen Final
Proyecto final de arquitectura web enfocado en recrear el ejercicio desarrollado en https://learn.microsoft.com/es-es/azure/container-instances/tutorial-docker-compose?source=recommendations , donde se implementa una aplicación  básica de votaciones mediante DevOps. Para ello se  implementa un componente web front-end y una instancia back-end de Redis. El componente web se empaqueta en una imagen de contenedor personalizada. La instancia de Redis usa una imagen sin modificar de Docker Hub
## Instalación del CLI de azure
Se hizo la respectiva descarga de Azure CLI para poder utilizar los comandos dentro de nuestro computador.

![Captura de pantalla 2022-11-24 125332](https://user-images.githubusercontent.com/88751751/203849324-5f3f7876-291b-4791-a099-b847080cf416.png)

Verificación de Instalación:

Ejecutamos el comando: az --version

![Captura de pantalla 2022-11-24 134547](https://user-images.githubusercontent.com/88751751/203849755-35d6d330-528c-4adf-84e7-64410d3e13c4.png)

Configuración de suscripción de estudiantes en Portal Azure:

![Captura de pantalla 2022-11-24 135008](https://user-images.githubusercontent.com/88751751/203850174-f764f6ee-9b73-4129-943c-9c432ed4294d.png)

Configuración de acceso y suscripción en Cli Azure:

Ejecutamos el comando: az login

![Captura de pantalla 2022-11-24 135321](https://user-images.githubusercontent.com/88751751/203850464-8bc913b0-64ac-42de-9c8a-c67fa0c67f5a.png)

## Creación de una instancia de Azure Container Registry

Creación de grupo de recursos

Ejecutamos el comando: az group create --name myResourceGroup --location eastus

![Captura de pantalla 2022-11-24 135433](https://user-images.githubusercontent.com/88751751/203850616-2703ec9f-653f-4b49-9dca-8351d0af32bc.png)

Creación de registro de contenedor de Azure

Ejecutamos el comando: az acr create --resource-group myResourceGroup --name <acrName> --sku Basic

![Captura de pantalla 2022-11-24 135705](https://user-images.githubusercontent.com/88751751/203850954-be001fde-2b29-4479-918b-8f7e65086dfd.png)
  
Iniciar sesión en el contenedor creado
  
Ejecutamos el comando: az acr login --name examenFinal
  
![Captura de pantalla 2022-11-24 140520](https://user-images.githubusercontent.com/88751751/203851646-c2f7caaf-2397-44bf-a0f7-01333f902fb2.png)

 
