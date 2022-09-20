# Flow4 - NodeRed

## Introducción
El flow 4 es el cuerto ejercicio a realizar en el curso de NodeRed. Este ejecicio consiste en darle un formato legible para humanos al timestamp y mostrar los datos de temperatura y humedad enviados desde la terminal hacia la sección dashboard.

## Material necesario
Para realizar este flow necesitas lo siguiente:

- [Ubuntu 20.04](https://releases.ubuntu.com/20.04/)
- [NodeJS](https://nodejs.org/es/)
      
    - [NPM](https://www.npmjs.com/) 
    - [NodeRed](https://nodered.org/docs/getting-started/local)

## Instrucciones 
### Resquisitos previos:
Para que este flow funcione, debes cumplir con los siguientes requisitos previos:
1. Instalación de NodeJS. Se recomienda tener instalado NodeJS en alguna versión LTS. Al momento de creación de este documento, se usó la versión 16.17.0LTS. Esta instalación debe incluir las Build-Tools para hacer uso de NPM
2. Instalación de NodeRed. La instalación se realiza por NPM. Al momento de la creación de este contenido, se usó la versión 3.0.2

### Instrucciones de preparación del entorno:

Para ejecutar este flow, es necesario lo siguiente.
1. Arrancar NodeRed con el comando `node-red`.
2. Importar el flow del repositorio.

![](https://github.com/DiegoJm10/Flow-4/blob/main/Captura%20desde%202022-09-19%2012-46-48.png?raw=true)


3. En el bloque de `Mqtt in` se debe colocar lo siguente:
    
- Server: `localhost:1883`
- Topic: `codigoIoT/Mor/mqtt/flow4`

4. En el bloque de `json` se debe colocar lo siguente:

- Action: `Always convert to JavaScript Object`

5. En el bloque de `Temperatura` y `Humedad` se debe colocar lo siguente:

- On message: 
```
 msg.payload = msg.payload temp;

 msg.topic = "Temperatura";

 return msg;
```
6. En la parte de Graficas e indicadores solo es editar al gusto.
7. Abriremos el Dashboard y colocaremos un `Tab` y dentro del `Tab` colocaremos un `group`.
8. Hacer clic en el boton Deploy.

### Instrucciones de operación:
1. Abriremos dashboard en el siguente servidor. [localhost:1880/ui](http://localhost:1880/ui)

2. Mandaremos los datos por mosquito(Terminal)con los siguentes datos:
```
mosquitto_pub -h localhost -t codigoIoT/Mor/mqtt/flow4 -m '{"ID":"Diego Jasso","temp":21,"hum":73}
```
![](https://github.com/DiegoJm10/Flow-4/blob/main/Captura%20desde%202022-09-19%2012-51-58.png?raw=true)


## Resultados
Los resultados son los siguentes tenemos dos imagenes que lo representa

![](https://github.com/DiegoJm10/Flow-4/blob/main/Captura%20desde%202022-09-19%2012-46-25.png?raw=true)
[Bloques de función.](https://github.com/DiegoJm10/Flow-4/blob/main/Captura%20desde%202022-09-19%2012-46-25.png?raw=true)

![](https://github.com/DiegoJm10/Flow-4/blob/main/Captura%20desde%202022-09-19%2012-47-09.png?raw=true)
[Dashboard.](https://github.com/DiegoJm10/Flow-4/blob/main/Captura%20desde%202022-09-19%2012-47-09.png?raw=true)

## Evidencias

- [Youtube](https://youtu.be/nL-me1Geef4)

## Creditos
Desarrollado por Ing. Diego Jasso Miranda
- [Facebook](https://www.facebook.com/jasso.diego.5/)
- [GitHub](https://github.com/DiegoJm10)