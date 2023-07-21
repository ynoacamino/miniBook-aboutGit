# conclusions-of-AprendiendoGit
Conclusiones del libro Aprendiendo Git de Miguel Angel Duran

## Indice

### 1. Introduccion
### 2. Teoria
### 3. Instalacion y configuracion
### 4. Lista y expliacion de comandos
#### Local
#### Ramas
#### Remoto
### 5. Conceptos utiles
### 6. Flujos de trabajo
### 7. Buenas Practicas
### 8. Stash
### 9. Trucos utiles
### 10. GitHub CLI

## Introduccion
### Que es este repositorio
Creo este repositorio para dar seguridad a mis conocmientos adquiridos al leer el libro, ademas de dejar escrito lo que aprendi y en especial mi punto de vista como desarrollador que al igual que mis companeros esta en constante aprendizaje.

### Que es git
Git es un software de codigo abierto, disenado originalmente por el creador de linux...<br>
Si bien la historia de git, de donde sale, cual fue la nesecidad de crearlo, porque en la actulidad solo
escuchamos de git y no de otro software que cumpla la misma funcion, es muy interesante y vale la pena
entenderlo, en este repositorio solo se hablara de la parte practica, entonces, que es git. <br>
Git es un software de control de veriones y copias de seguridad, este de base en repositorios
en el cual se encuentra el codigo del proyecto y el historico de los cambios

Un repositorio puede ser locales o remotos, estos ultimos son los que nos permiten trabajar de manera colaborativa
Cada repositorio tiene un rama `main`, cuando nombramos ramas debemos pensar en estas como una linea de tiempo
en la cual se puede retroseder, dividir y fusionar

Git nos ayuda a llevar ese registro de cambios que hacemos a nuestro codigo, y ademas darnos la seguridad
que nuestro codigo puede retroceder a una verison anterior


### Los tres estados de Git
Nuestro repositorio contiene los archivos de nuestro proyecto, estos archivos pueden tener diferentes
estados cada uno con un proposito:

- Modified (modificado): Este estado es al que pasa un archivo que alteramos en algun aspecto, ya sea borrar, anadir o modificar una linea, estos cambios todavia no estas preparados para ser confirmados.
- Staged (preparado): Cuando marcamos nuestros archivos con este estado le estamos diciendo a Git que estan preparados para ser confirmados. Estos se encuentra en un estado transitoria para luego ser confirmados.
- Commited (confirmado): ESto quiere decir que nuestro archivo se encuntra confirmado y guardad en nuestro repositorio local. La accion de pasar de `stage` => `commited` se llama "commit".

#### NO ENTIENDO, AYUDA 
Es normal que esto te confunda, la mejor forma de entender los estados de los ficheros en Git es pensado
en una sesion de fotografia. Con un panel, una camara y los objetos que queremos fotografiar.

- Al principio nuestro panel va a estar vacio ya que no tenemos nada nuevo a lo sque queramos fotografiar.
- Oh, uno de nuestros objetos cambio de color. Esto representa el estado de `Modified`.
- Como nuestro objeto cambio, asi que lo preparamos y lo dejamos dentro de panel. Mover nuestro objeto y prepararlo representa al accion de `add` y el panel el estado `Stage`.
- Al parecer mas objetos an estado cambiando, de modo que tambien los preparemos y los dejamos dentro del panel. Podemos preparar varios archivos al mismo tiempo, esto es porque algunos cambios tienen relacion directa con otros de modo que los podemos guardar juntos.
- Ahora con todos nuestros objetos listos para la fotografia procedemos a tomar la foto, de esta manera no nos olvidaremos de este momento. La accion de tomar la foto hace referencia a la accion `commit` ya que con esto guardamos nuestros cambios ademas de darles un nombre o asunto.
- Ya tenemos nuestra foto!, ahora nunca olvidaremos este momento, procedemos a dejar nuestros obejtos en su lugar, fuera del panel. Esto representa el fin del ciclo de vida de los ficheros, de este modo despuse de hacer `commit` pasaran a estar sin modificar otrave, de modo que podemos repetir el ciclo.

Espero que de esta manera ayas podido entender con mas claridad como funionan los estados de los archivos y las accioines que pueden modificar a estos.

### Que es una rama
Antes dijimos que deberiamos pensar en los estamos de commit como una sesion fotographica, de la
misma manera podemos pensar en una rama como un album de fotos.<br>
Por defecto nuestra rama se llamara `main` y estara formada por el historial de nuestros commits

        main || git init <---- commit 1 <---- commit 2 <---- commit 3

Podemos ver nuestra unica rama `main` esta contiene nuestros commit, mas no es la unica rama
que podemos tener podemos crear ramas a partir de otra en nuestro caso `main` pero esto lo veremos un
poco mas adelante.

### Introduciendo HEAD
HEAD es una variable que contiene la direccion actual de nustra posicion en las ramas

### Creando ramas
En el siguiente ejemplo crearemos una rama con el nombre `newRama`.

Estado inicial(antes de crear la rama)

        main || git init <---- commit 1 <---- commit 2

Despues de crear la nueva rama a partir del commit 2

        main || git init <---- commit 1 <---- commit 2
                                                 \
                                                  \
                                        newRama || commit 2

Como podemos ver nuestra rama desiende del commit 2 por lo que se crea como una copia exacta de este


