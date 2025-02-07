[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-c66648af7eb3fe8bc4f294546bfd86ef473780cde1dea487d3c4ff354943c9ae.svg)](https://classroom.github.com/online_ide?assignment_repo_id=7705717&assignment_repo_type=AssignmentRepo)


# Cámara virtualizada utilizando Simics
Este proyecto utiliza la herramienta [Simics](https://www.intel.com/content/www/us/en/developer/articles/tool/simics-simulator.html), una plataforma que permitirá simular un dispositivo (en este caso una cámara) que se conectará a algún computador mediante un puerto [PCI](https://pcisig.com/specifications). Dicho dispositivo podrá tomar fotos, aplicar filtros, además el proyecto incluirá una aplicación para el usuario con la cual realizar dichas acciones y poder visualizar los resultados.


## 🗃️ Tabla de contenidos
- [Guía de compilación](#-guía-de-compilación)
- [Cómo usarlo](#-cómo-usarlo)
- [Funcionalidades básicas](#-funcionalidades-básicas)
- [Protocolo](#-protocolo)
- [Cosas por hacer](#-cosas-por-hacer)
- [Autores, licencia](#-autores)

## 📦 Guía de compilación

Primeramente es necesario clonar el repositorio:  
````
$ git clone https://github.com/ECCIUCRLQ/proyecto-ode.git
````

### Proyecto de Simics
Para poder utilizar el proyecto de Simics se deben seguir los pasos de [instalación](https://github.com/ECCIUCRLQ/proyecto-ode/wiki/Simics#instalaci%C3%B3n), una vez hecha la instalación hay que realizar los siguientes pasos:
* Hacer el project setup
````
$ <instalación de simics>/simics-6.0.XXX/bin/project-setup <dirección de este repositorio>/src/ODEcam 
````
* Compilar los modulos
````
$ cd <dirección de este repositorio>/src/ODEcam/modules
$ make
$ make
````

### Editro de imagenes
Para compilar el programa editor de imagenes dentro del folder `src/User Program`
````
$ make
````

## 🚀 Cómo usarlo

Para utilizar los filtros solo se ejecuta le programa:
````
$ ./program <dirección a la imagen por editar> <nombre de la nueva imagén>
````
Luego en el menú elegir el filtro según el numero que muestre.

## 📷 Funcionalidades básicas

Esta cámara virtual empleará el formato de archivo [BMP](https://github.com/ECCIUCRLQ/proyecto-ode/wiki/Bitmap). Por limitaciones del proyecto, la captura de fotografías se basará en tomar una imagen aleatoria preinstalada en el dispositivo y enviarla como resultado, ha esta se le podrán aplicar distintos [filtros](https://github.com/ECCIUCRLQ/proyecto-ode/wiki/Dispositivo#filtros) para cambiar su apariencia, además de incluir metadatos de la imagen, como fecha de captura, tamaño, etc.

### Filtros 🪟

Estos son algunos de los filtros que  se le podrán aplicar a las fotos:

[normal]: https://github.com/ECCIUCRLQ/proyecto-ode/blob/main/doc/img/imagen_referencia_normal.jpg "Imagen de referencia normal"
[vintage]: https://github.com/ECCIUCRLQ/proyecto-ode/blob/main/doc/img/imagen_referencia_vintage.jpg "Imagen de referencia con filtro vintage"
[negativo]: https://github.com/ECCIUCRLQ/proyecto-ode/blob/main/doc/img/imagen_referencia_negativo.jpg "Imagen de referencia con filtro negativo"

<details>
  <summary>Vintage</summary>
  
| ![alt text][normal] | ![alt text][vintage] |
|:-------------------:|:--------------------:|
  
> Las anteriores imágenes no representan el aspecto final del resultado de los filtros que va a aplicar el dispositivo.
  
  El filtro vintage le da una apariencia antigua a las fotos.
</details>

<details>
  <summary>Negativo</summary>
  
| ![alt text][normal] | ![alt text][negativo] |
|:-------------------:|:---------------------:|
  
> Las anteriores imágenes no representan el aspecto final del resultado de los filtros que va a aplicar el dispositivo.
  
  Con este filtro los blancos son tratados como negros y los negros como blancos.
</details>

## 🧮 Protocolo
Es la forma en la que comunica el dispositivo con el driver, se implementará según un consenso de la clase.
## ✅ Cosas por hacer
- [X] Diseño del producto final
- [X] Guía de compilación
- [X] Como utilizarlo
- [ ] La especificación formal del dispositivo
- [ ] El controlador (driver)
- [X] Un programa de usuario
- [ ] Pruebas de validación 
- [ ] Protocolo

## 👤 Autores
Oscar Quesada Webb
- oscar.quesadawebb@ucr.ac.cr

## 📝 Licencia
Este repositorio tiene una licencia [MIT](LICENSE)

[1]: https://docs.microsoft.com/en-us/windows/win32/gdi/bitmaps
