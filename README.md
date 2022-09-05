# Arquitectura Monolítica vs Microservicios
![Imagen de Arquitectura Monolítica vs Microservicios](https://www.ilimit.com/wp-content/uploads/2020/09/Monolith-vs-Microservices-1024x568.png)

## Arquitectura Monolítica
Consiste en crear una aplicación autosuficiente que contenga absolutamente toda la funcionalidad necesaria para realizar la tarea para la cual fue diseñada, sin contar con dependencias externas que complementen su funcionalidad. En este sentido, sus componentes trabajan juntos, compartiendo los mismos recursos y memoria.
## Arquitectura basada en Microservicios
Consiste en crear pequeños componentes de software que solo hacen una tarea, la hace bien y son totalmente autosuficientes, lo que les permite evolucionar de forma totalmente independiente del resto de componentes.

## Caracteríticas Arquitectura Monolítica
- Programas que son fáciles de desarrollar.
- El costo de desarrollo es bajo.
- La ejecución y el despliegue del software son sencillos.
## Arquitectura basada en Microservicios
- Facilita las actualizaciones.
- Despliegue independiente.
- Permite desarrrollarse por medio de distintos lenguajes de programación.
- Escalabilidad por módulos.
- Facilita los procesos de prueba y test.

## Ventajas y desventajas
### Monolítica: 
- Ventajas
  - Implementación sencilla
  - Desarrollo.
  - Rendimiento.
  - Depuración sencilla.
  - Pruebas simplificadas.
- Desventajas
  - Velocidad de desarrollo más lenta.
  - Escalabilidad.
  - Fiabilidad.
  - Barrera para la adopción de tecnología.
  - Falta de flexibilidad.
  - Implementación.

### Microservicios: 
- Ventajas
  - Agilidad.
  - Escalado flexible.
  - Implementación continua.
  - Muy fácil de mantener y probar.
  - Alta fiabilidad.
- Desventajas
  - Desarrollo descontrolado.
  - Costes exponenciales de infraestructura.
  - Más sobrecarga organizativa.
  - Desafíos para la depuración.
  - Falta de estandarización.
  
## Comparación
![Imagen de Arquitectura Monolítica vs Microservicios](https://wac-cdn.atlassian.com/dam/jcr:b2be0d53-f4b2-46d8-9a34-993048cc6225/Monolith%20Vs%20Microservice%20image.png?cdnVersion=506)

| Monolítica | Microservicios |
| ------------- | ------------- |
| Compila como una sola unidad unificada, es decir como solo una aplicación  | Es una serie de servicios pequeños que presentan diferentes funcionalidades que se pueden implementar de forma independiente.|
| Velocidad de desarrollo más lenta  |  Promueve formas ágiles de trabajar con equipos pequeños que implementen con frecuencia  |
| No se pueden escalar componentes individuales  | Escalado flexible  |
| Depuración sencilla  | Desafíos para la depuración  |
| Si hay un error en algún módulo, puede afectar a la disponibilidad de toda la aplicación  |  Alta fiabilidad. Implementar cambios para un servicio en concreto sin el riesgo de que se caiga toda la aplicación |

## Casos de aplicabilidad
### Arquitectura Monolítica: 
El modelo monolítico puede ser aplicado a aplicaciones de poco crecimiento y funcionalidad fija. De modo tal, que su despliegue es rápido y relativamente económico.
### Arquitectura Microservicios: 
Se está utilizando una arquitectura de microservicios para poder escalar servicios y garantizar que pueden prestarlos de forma continua y sin interrupciones.

## Referencias
Atlassian. (s. f.). Comparación entre la arquitectura monolítica y la arquitectura de microservicios. Recuperado 5 de septiembre de 2022, de https://www.atlassian.com/es/microservices/microservices-architecture/microservices-vs-monolith#:%7E:text=Una%20aplicaci%C3%B3n%20monol%C3%ADtica%20se%20compila,pueden%20implementar%20de%20forma%20independiente. 

¿Qués Es Una Aplicación Monolítica Vs. Microservicios? (2022, 16 mayo). Codster. Recuperado 5 de septiembre de 2022, de https://codster.io/blog/aplicacion-monolitica-vs-microservicios/
