# miniBook-AboutGit
Transladando mi poco conocimiento sobre git a un mini libro, el cual espero que ayude a
muchos companeros

## Indice

### 1. Introduccion
### 2. Teoria
### 3. Instalacion y configuracion
### 4. Lista y explicacion de comandos
#### 4.1. Local
#### 4.2. Ramas
#### 4.3. Remoto
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

## Teoria

### Los tres estados de los archivos en Git
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

### Git y GitHub no son lo mismo
Parece un poco ovbio pero todavia escucho personas penser eso, y no tiene nada de malo
a simple vista cumplen la misma funcion.

- Git: Es un sistema de versionamiento y control, es decir nos ayuda a controlar nuestros cambios, este se ejecuta de manera local, de la misma manera almacena los repositorios en nuestra maquina.
- GitHub: Es un servicio de hospedamiento remoto de nuestros repositorios, ofrecido actualmente por Microsoft, y no es el unico que nos ofrece tal cosa, por ejemplo tenemos a GitLab o BitBucket, los cuales nos ofrecen los mismo. En resumen GitHub solo almacenara nuestros repositorios en la nube estando asi listos para podeer usarlos desde cualquier parte o momento, ya se por nosotros o por un equipo de desarrollo.

## Instalcion y configuracion
Aqui se daran algunos pasos y recomendaciones para descargar y configurar git, mas no reemplaza leer la documentacion de su pagina oficial,
ademas que solo veremos las formas de instalarlo en algunos sistemas operativos.

### Comprobando si ya tengo instalado Git
Esto es muy facil solo es ejecutar el siguiente comando en la terminal. Una aclaracion,
siempre que vean un signo de dolar anteponiendo al comando, quiere decir que ese comando se
ejecuta en una terminal, no es nesesario y no se debe copiar directamente en esta.

        $ git --version

Si tenemos instalado git nos saldra lo siguiente:

        git version 2.41.0

Si al contrario el mensaje de vuelta es algo como `git: command not found` es porque aun no tenemos
instaldo Git

### Instalando Git
- Ubuntu: Tan simple como ejecutar

        $ apt-get install git

- Windows: Tambien simple, dirijete a la pagina oficil y descarga el instalador, sigues lo pasos y le das siguiente a todo.


### Configurando mi nombre y correo
Al hacer cambios en el repositorio estamos modificando archivos que podrian ser muy importante
ya se en el caso de estar trabanjo solo o en un equipo por esta razon tenemos que firmar
con nuestro nombre y correo cada cambio que hacemos, de esta manera, los demas integrnates podran
saber quien hizo que cosa y haci tener un mejor control.

Ejecutamos los siguientes comandos cambiando la informacion con la correspondiente:

        $ git config --global user.name "miNombreDeUsuario"
        $ git config --global user.email "miCorreo@example.com"

En mi caso seria de la siguiente manera:

        $ git config --global user.name "Diegoo11"
        $ git config --global user.email "ynoacamino@gmail.com"

Explicacion: Con la bandera `--global` le estamos diciendo que queremos que esta configuracion
se guarde y este disponible para todos nuestros repositorios, tambien podemos querer
que solo se guarde en un repositorio en especifico, para ese caso nos dirijimos a la carpeta raiz de este
y ejecutamos.

        $ git config user.name "miOtroNombre"

De esta manera se guardara solo en el repositorio especifico.

### Listar la configuracion
Un comando muy util que uso siempre antes de abrir mi editor de codigo, es listar mi configuracion
ya sea porque no estoy seguro cual sera mi rama por defecto o aun mas importante, saber
con que correo estoy trabajando, ya que si uso un correo y nombre diferente del que tienen concimiento
mi equipo de desarrollo causare confucion y es lo que menos queremos. <br>
Para esto usaremos el siguiente comando.

        $ git config --list

Nos mostrara toda nuestra configuracion global, en caso de solo querer la configuracion local del repositorio
podemos ejecutar el siguiente.

        $ git config --local --list

## Lista y explicacion de comandos
Los comandos listados acontinuacion tendran la siguiente forma

        $ <comando> <argumento|opcional> <archivo>
        $ ...variantes del mismo comando
        
        Breve expliacion.
        Casos de uso.
        Opinion.

### git init : Inicializar un remositorio
Un dato curioso es que cuando ya iva por mas de la mitad del libro me di cuenta que no explique como inicializar un repositorio, mi error.

        $ git init
        $ git init <ubicacion del directorio>

Para inicializar un nuevo repositorio basta con ejecutar `git init` en la carpeto donde queremos que sea el repositorip o sino decirle en donde queremos inicalizarlo pasandole una ruta desde de `init`. Esto creara una carpeta `.git` en donde se guardaran todas nuestras versiones e informacion nesesaria para esta, por defecto esta carpeta esta oculta y es mejor dejarla asi ya que cualquier cambio podria dejar inutilizable el repositorio local

### git restore : Eliminar los cambios hechos a un archivo

        $ git restore archivo.txt
        $ git restore archivo.txt archivo2.md
        $ git restore .

Con el mas minimo cambio nuestro archivo pasara del estado `commited` a `modified` pero
aveces modificamos un archivo por error y queremos volver a la ultima ves donde nuestro archivo
estada `commited`.<br>
Para esto usamos `git restore <ruta del archivo>`, tenemos de tener mucho cuidado ya que
de hacer accidentamente podemos perder muchas horas de trabajo

Tenemos que tener en cuenta que tanto `archivo.txt`,
`archivo.txt archivo2.md` y `.` son rutas y eso es lo que acepta Git.

### git add : Anadir archivos al area de `stage`

        $ git add archivo.txt                   (1)
        $ git add archivo.txt archivo2.md       (2)
        $ git add .                             (3)

Git add sirve para pasar un archivo del estado `modified` al estado `staging`. <br>

|   Archivos    |   Modified    |   Staging     |
|---------------|---------------|---------------|
|   archivo.txt |   X           |               |
|   archivo2.md |   X           |               |

Despues de haber ejecutado los mandos nustros archivos que inicialmente tenian le estado
de `modified` pasaron a estar en `staging`.

|   Archivos    |   Modified    |   Staging     |
|---------------|---------------|---------------|
|   archivo.txt |               |   x           |
|   archivo2.md |               |   x           |


### git reset : Sacar ficheros del area de `stage`

        $ git reset archivo.js
        $ git reset archivo.js README.md
        $ git reset .

Hay veces donde escribimos mal la ruta de una archivo y lo anadimos por error al area de `stage`. <br>
No hay problema, lo sacaremos. Con el comando `git reset <ruta>` podemos sacar esos archivos
que no queremos que esten en `stage`.

Estado inicial:

|   Archivos    |   Modified    |   Staging     |
|---------------|---------------|---------------|
|   archivo.js  |               |   x           |
|   README.md   |               |   x           |

Despues de: `git reset .`

|   Archivos    |   Modified    |   Staging     |
|---------------|---------------|---------------|
|   archivo.js  |   x           |               |
|   README.md   |   x           |               |


### git commit : Guardando con commit

        $ git commit                                (1)
        $ git commit -m "<mensaje>"                 (2)
        $ git commit -m "<mensaje>" <ruta>          (3)


Si no leiste 'Los 3 estados de los archivos en Git' te recomiendo encaresidamente que
le des una leida antes de continuar.<br>
Digamos que ya editamos nuestro archivo `App.js`, decidimos que terminamos de hacer los
cambios correspondientes asi que ejecutamos

        $ git add App.js

De paso anadimos otros archivo que tambien estan listos

        $ git add README.md
        $ git add index.js
        $ git add package.json

Ahora estamos listos para hacer nustro primer commit

        $ git commit -m "mi primer commit"

De esta manera terminamos el ciclo de vida de los ficheros y pasan a estar otraves al
estado `commited`

                           edit                  add
        -----> commited ----------> modified -----------> staged -----
        |                                                            |
        |                                                            |
        |                                                            |
        --------------------------------------------------------------
                                    commit

- **(1):** Guarda el commit de todos los archivos que esten en el area de `staging`, ademas habre un editor de texto para incluir el asunto del commit

- **(2):** Guarda el commit de todos los archivos que esten en el area de `staging`, mas no habre nigun editor ya que le pasamos el mensaje del commit como parametro

- **(3):** Cumple la misma funcion que **(2)** pero solo guarda un archivo en particular y los demas los ignora.

### git reset : Quiero eliminar mi commit y devolver una version anterior

        $ git reset HEAD~1                          (1)
        $ git reset HEAD~i                          (2)
        $ git reset <hash>                          (3)

Que ha pasado, al parecer cometiste un error al subir el commit y quiere volver a un version
anterior, no hay problema con `git reset` podemos lograrlo pero antes:

- `git reset` puede ser muy peligroso ya que alteramos los commis osea los nodos de nuestra rama esto puede cuasar problemas tanto para nosostros como para nuestro equipo de desarrollo si no se hace con precucion.

- Siempre podemos optar por volver a editar nuestro fichero y hacer otro comint solucionando los cambios, aveces esta es la mejor opcion ya que no solo no alteramos el flujo de la rama sino dejamos constancia del error.

Si aun asi lo necesitas adelante.

- **(1):** Con `HEAD~1` le estamos diciendo que retroceda un commit anterior.

- **(2):** En este `i` se debe cambiar por el numero de commits que queremos retroceder.

- **(3):** En caso de tener el hash del commit al cual nos queremos transladar podemos usarlo tambien.

### git checkout : Viajar en el tiempo o entre commits

        $ git checkout HEAD~1
        $ git checkout HEAD~i
        $ git checkout <hash>

Talves uno de los comando mas interesantes en mi opinion y el que mas recomiendo usar sobre comandos como
`git reset` o `git rebase` ya que `checkout` no altera la rama en ningun sentido, solo nos permite
viajar y transladarnos entre commits y asi rebuscar entre el codigo que nos interesa.<br>
Algo importante de aclarar es que cuando nos movemos entre commits con `checkout` HEAD se cuentra
en un estado `separado` que no nos permite editar archivos pasados.

Que ya te aburriste de ver tu codigo de commits antiguos y quieres volver al commit mas reciente? Ejecuta este comando

        $ git switch <nombre de la rama>

### Introducciondo HEAD
HEAD no es la cabeza de la rama, eso hay que tenerlo claro, podemos pensar en HEAD como un GPS para
saber con precicion en que parte de la rama nos encontramos. <br>
Explicacion con grafico para entender con facilidad.

        main | git init ----> A ----> B ----> C ----> D (HEAD)

Podemos observar la rama `main` la cual inicia con git init, luego se hacen los siguientes commits,
A, B, C, D; sinedo D el ultimo por lo tanto seria nuestro HEAD ya que es el ulitmo lugar donde nos encontramos. <br>
Pero ahora ejecutaremos `git checkout` para movernos entre commits.

        $ git checkout HEAD~2

Y nuestro grafico quedaria de la siguiente manera.

        main | git init ----> A ----> B (HEAD) ----> C ----> D

Podemos observar como HEAD nos sigue y apunta al commit donde nos encontramos.

Anteriormente vimos como deshacer un commit y para eso usamos el parametro `HEAD~1`, este parametro queria decir,
**un commit anterior a HEAD** o en caso de `HEAD~i`, **retrocede 'i' veces en commits a partir de HEAD**.

### Ignorando ficheros
Ya sea porque tenemos archivos innesesarios, claves privadas o carpetas con codigo de produccion tarde o temparno
querremos ingonar algun fichero y de esta manera impedir que se muestre en el repositorio
publico, esto se logra escribiendo el nombre del archivo en el archivo `.gitignore`.

        .env
        dist
        public
        test.js
        app.test.js
        CLAVE_PRIVADA.js

De esta manera le estamos diciendo a git que no haga seguimiento de esos archivos

### git rm : Ignorar archivos que ya tienen seguimiento
Hay veces que no nos damos cuenta o nos olvidamos a de colocar el nombre en `.gitignore`
no pasa nada lo solucionaremos. <br>
Primero simularemos el posible caso.

        $ nvim clave.js
        $ git add .
        $ git commit -m "init project"

Ahora Git hara seguimiento de nuestra clave junto con todo el projecto, para solucionarlo
ejecutamos el siguiente comando

        $ git rm --cached clave.js

Este comando solo hara que `clave.js` se deje de rastrear, si ademas queremo borrarlo tenemos
este otro comando.

        $ git rm clave.js


### Que es una rama
Antes dijimos que deberiamos pensar en los estamos de commit como una sesion fotographica, de la
misma manera podemos pensar en una rama como un album de fotos.<br>
Por defecto nuestra rama se llamara `main` y estara formada por el historial de nuestros commits

        main || git init <---- commit A <---- B <---- C (HEAD)

Podemos ver nuestra unica rama `main` esta contiene nuestros commit, mas no es la unica rama
que podemos tener podemos crear ramas a partir de otra en nuestro caso `main` pero esto lo veremos un
poco mas adelante.

### git branch : Creando ramas

        $ git branch <nombre>                       (1)
        $ git switch -c <nombre>                    (2)

En el siguiente ejemplo crearemos una rama con el nombre `newRama`.

Estado inicial(antes de crear la rama)

        main || git init <---- A <---- B (HEAD)

Despues de crear la nueva rama a partir del commit 2, por lo que ejecutamos los siguiente

        $ git branch newRama

        main || git init <---- A <---- B
                                        \
                                         \
                               newRama || B (HEAD)

Como podemos ver nuestra rama desiende del commit B por lo que se crea como una copia
exacta de este. A partir de este punto cada rama es independiente una de otra, cada una
puede continuar con commits que la agan crecer, eliminarse, o incluso fucionarse con otra
rama en algun momento.<br>
En el siguiente ejemplo cada rama seguira creicendo por su lado y la rama `main` se
volvera a dividir(bifurcar).

                               otraRama || D <---- H
                                          /
                                         /
        main || A <---- B <---- C <---- D <---- J <---- K (HEAD)
                         \
                          \
                newRama || B <---- F <---- G

- **(1)** Crea la nueva rama pero no cambiamos a esta.
- **(2)** Crea la nueva rama y cambia a esta automaticamente.

### git switch : Comandos utiles para manejar ramas
    
        $ git branch

Muestra las ramas disponibles y la rama en la que nos encontramos, esta marcada con un asterisco.

        $ git switch nombreDeLaRama
        $ git switch -

Git switch sirve para cambiar entre ramas, pasandole como parametro el nombre de la rama, o si
solo queremo movernos a la rama donde estabamos previamnete podemos usar el `-`

### git merge : Fusionando ramas

        $ git merge nombreDeUnaRama

Llego el momento, la pesadilla de muchos 'Fusionar ramas', mas no hay que asustarse
aqui lo entenderas de una vez por todas y nunca mas le tendras miedo.

Para esto vamos a imaginar que tenemos 3 commits, A, B, C, en C es que nos damos cuenta
que queremos probar un nuevo framework o utilidad mas no queremos comprometer al projecto
principal para esto creamos una rama llamada `experiment`.

        main || A <----- B <----- C
                                   \
                                    \
                       experiment || C

Ya con nuestra rama creadad podemos continuar trabajando en el projecto principal y al
mismo tiempo probar el nuevo framework, por lo que continuaremos haciendo commits
a ambas ramas

        main || A <----- B <----- C <---- D <----- E
                                   \
                                    \
                       experiment || C <---- X <---- Y (HEAD)

Todo a ido bien con las pruebas del nuevo framework y decides que es lo mejor para el
projecto por lo que ahora quieres unir las ramas para tener tanto el nuevo framework
como los cambios que fuiste avanzando mientras probabas este.

Para esto debemos tener claro que queremos hacer, queremos que `main` contenga los cambios
de `experiment` y dejar a `experiment` intacto? o quremos que experemente contenga los cambios de
`main` y dejar a `main` intacto?

Normamnete es la primera opcion ya que `main` debe contener los cambios principales y
`experiment` desaparecer despues de cumplir su funcion, probar una nueva funcionalidad. Por
lo que tomada una decicion nos aseguramos que estamos en la rama donde queremos ver
reflejados los cambios. Ejecutamos:

        $ git switch main


        main || A <----- B <----- C <---- D <----- E (HEAD)
                                   \
                                    \
                       experiment || C <---- X <---- Y

Ya habiendonos movido ejecutamos

        $ git merge experiment

Despues de ejecutar git merge nos quedaria del siguiente modo:

        main || A <----- B <----- C <---- D <----- E <---- F
                                   \                     /
                                    \                   /
                       experiment || C <----- X <----- Y

### git branch -d : Eliminando ramas

        $ git branch -d <nombreDeRama>              (1)           
        $ git branch -D <nombreDeRama>              (2)

Ya habiendo fusinado nuestras ramas con la principal probablemente querramos borrarla ya que ya no nos es de uso. Para esto usaremos un comando ya conocido pero con un parametro nuevo, `-d` o `-D`.

- **(1):** Eliminar la rama selecionada pero se asegura de haberle dado un uso primero, como hacer una pull request o un git merge, de otro modo no te dejara eliminarlo. ESto es muy util para no tener accidentes y perder muchas horas de trabajo.

- **(2):** Elimina las ramas sin ningun tipo de advertencia, aveces es lo que queremos ya que habra casos donde no le hallamos dado ningun uso a esta, por lo tanto debamos eliminarla sin mas

### git remote prune origin : Sincronizando ramas

        $ git remote prune main
        $ git remote prune <nombreDelRepositorioRemoto>

Pero que pasa si llevamos varios dias sin sincronizarnos a nuestro repositorio remoto y ademas hemos creado varias ramas que no llegaron a nada en el remositorio local, o en el caso que las ramas que descargamos inicialmente ya no se encuentran en el repositorio remoto sino que las eliminaron.<br>
Para sincronizar nuestras usamos `git remote prune origin`, ahhh no entiendo la sintaxis, me imagino que estaras diciendo algo asi pero esta bien que no entiendas ya que aun no vemos git desde la parte de repositorios remotos, aun asi me gustaria explicartelo de modo que cuando lleves a esa parte puedas regresar y entender con mas claridad. <br>

- `git remote` con esto le decimos a Git que nos referimos a uno de los repositorios remotos (si, podemos tener mas de uno)
- `prune` es la accion a realizar, en este caso elimnar ramas, "prune" traducido al espanol significa "podar"
- `origin` con esto nos referimos al nombre del repositorio remoto, ya que podemos tener varios debemos darles un nombre para referenciar a uno, por defecto se le asigna origin por lo que la mayoria de veces usaremos este

### Trabajando con repositorios remotos
Ahora que sabes como controlar tu flujo de trabajo ya te encuentras listo para conpartir tu codigo con el mundo, espero mucho de ti. Talvez no estas convencido de subir tus repositorios a paginas como GitHub o GitLab ya que piensa que no es nesesario y hasta pesado, no temas yo te hare cambiar de opinion.

#### Porque hacer mi codigo publico? Que gano yo?
- Colaboracion: Al subir tu codigo a un repositorio publico tienes la oportunidad de trabajar con mas personas en un solo proyecto, retroalimentarse unos a otros y mejorar juntos.

- Llevar un portafolio: Se que pensaras que aunque subas lo que desarrollas nadie querra ver tu trabajo, pero no es cierto cuando llegue el momento de buscar una oportunidad o demostrar tus habilidades te servira tener tus trabajos listos y publicos desde que comenzaste a programar hasta tus proyectos mas recientes e impresionantes. Todo cuenta!

- Codigo abierto: Por que contribuir al codigo abierto? Pues nos ayuda a trbajar colaborativamente con otros desarrolladores y resivir feedback sobre nuestro codigo, es un ganar ganar. Aun no estas convencido? Pues quiero recordarte que muchas de las herramientas que usamos dia a dia se las debemos al codigo abierto, sin irnos muy lejos esta la plataforma virtual de la UNSA, asi es, "Moodle" es de codigo abierto y como todos los proyectos de codigo abierto es mantenido por desarrolladores que aportan su grano de arena para contruir tecnologias increibles. 

- Mejoramiento personal: Si subimos un repositorio a GitHub, a menos que este en privado, todos podran ver tu codigo y jusgarlo y aunque suene feo es lo mejor. Recordemos que el desarrollador ya no escribe codigo para si mismo sino que escribe para todo su equipo de desarrollo actual y el que lo reemplazara cuando este se valla, esto quiere decir que tenemos que estar en constante mejoramiento de nustras practicas y una forma de lograrlo es haciendo nuestro codigo libre a miradas. Almenos yo cuando se esto entiendo que debo esforzarme mas y seguir las buenas practicas, mejorando constantemente.

### Iniciando un repositorio en GitHub

#### Aclaracion:
Se esta suponiendo que usted ya tiene configurado las credenciales ssh con github, sino aun no lo a hecho dejare algun libro y link para que pueda seguir los pasos sin ningun problema

- Para esto vamos a la seccion repositorios en nuestro perfil y le pulsamos `new`
- Luego con pedira llenar los datos, aqui escribimos el nombre, descripcion, si queremos que se cree el archivo .gitignore o el archivo README.txt, la visibilidad del repositorio, etc.
- Ya despues de crear el repositorio veras la pestana `code` la cual presionaras y te dirigiras a `SHH`, ya estando ahi le das al boton de copiar
- Listo ya tienes la referencia a tu repositorio remoto

### git clone : Clonando un repositorio ya creado

        $ git clone <Lo que copiaste anteriormente>

Por ejemplo:

        $ git clone git@github.com:Diegoo11/miniBook-aboutGit.git

### git remote : Subir mi proyecto local a remoto y otras explicaciones

#### Subir de local a remoto

        $ git remote add <nombre> <direccion del nuevo repositorio>

Ejemplo:
        
        $ git remote add origin git@github.com:Diegoo11/miniBook-aboutGit.git

Te acuerdas que anteriormente ya vino `remote`, llego el momento de entenderlo a la perfeccion

1. `remote`: le desimoq que queremos acceder a la configuracion de los repositorios remotos
2. `add`: en este caso queremos anadir una nueva direccion a nuestro repositorio
3. `<nombre>`: Hay que aclarar que podemos tener mas de un repositorio remoto enlazado al mismo en local, entonces la forma de diferenciar uno de otro es darle un nombre, este por defecto es `origin` pero tambien podemos darle cualquier nombre
4. `<direccion>`: Aqui copiamos la direccion ssh de un repositorio remoto, de preferecia que este vacio ya que asi no tendremos problemas al subir los archivos por primera vez, por el contrario si ya contiene ficheros y estos llevan los mismos nombre podriamos estar en problemas ya que habra conflictos.

#### Eliminar en enlace entre local y remoto

        $ git remote remove <nombre>

#### Listar los repostirios remotos

        $ git remote

#### Renombrar un repositorio remoto

        $ git remote rename <nombreActual> <nuevoNombre>

### git push : Subir commits a remoto

        $ git push                                  (1)
        $ git push <remoto> <rama>                  (2)

**(1):** Aclaracion, cuando no se envia ningun parametro despues de `push` git asumira lo siguiente, `git push origin <ramaActual>`, por lo que siempre seria mejor completar los otros parametros en especial si tenemos varias ramas, ya que nos permitira tener conciencia de en donde queremos hacer el push
**(2):** Ejemplo:

        $ git push origin main

La palabra `push` traducida al espanol seria "empujar", y tiene todo el sentido porque queremos subir nuestros cambios a remoto
empujandolos desde el local, empujamos lo commits que aun no estan subidos a remoto


        A ----> B ----> C ----> D ----> E ----> F
                        ^                       ^
                        |                       |
                    git push (1)            git push (2)

En el psuh (1) subimos los commits A, B, C; posteriormente seguimos trabanjando y volvemos
a hacer git push (2) en este caso subiremos los commits C, E y F ya que git sabes que commit ya estan subidos en remoto y solo sube lo que son nuevos


### git pull : Sincronizar con remoto

        $ git pull
        $ git pull <remoto> <rama>

Antes solo nos preocupabamos por nuestros cambios pero ahora trabajamos con repostirios remoto
y esto incluye que podemos tener cambios que nosotros no hicimos, sino que los hizo nuestro equipo de
desarrollo, estos cambios no se sincronnizan automaticamente con nuestro repositroio local para esto
ejcutamos `git pull`. Con esto le estamos diciendo que sincronize los cambios con el remoto.

### git fetch : Trae los cambios mas no altera tu espacio de trabajo

        $ git fetch
        $ git fetch <remoto> <rama>

Pero que pasa si estamos trabajando en algo importante en local pero en remoto borraron o sobrescribieron nuestro codigo,
al hacer pull perderiamos nuestro avanze y horas de trabajo, para esto existe git fetch.
Trae los cambios mas no los fusiona automaticamente sino que nosotros tenemos que hacerlo, pero primero
podemos ver que cambios hay y a que parte de nuestro proyecto compromete. A continuacion dejo comandos utiles
que nos ayudaran con este proposito:

        $ git log origin/main

Con este podemos ver que commits no estan en nuestro repositorio y q archivos modifican pero nada mas.

        $ git diff origin/main

Este comando nos proporsionara cierta informacion aunque un poco confusa sobre los cambios en cada arhivo,
si bien puede ser util en ciertos casos, lo nomral es que se torne turbio cuando hay muchos cambios a diferentes archivos

        $ git difftools origin/main

Antes de ejecutar este comando debemos tener configurado una herramienta para este, normalmente yo uso
vim o neoVim para esta tarea ya que son las mas faciles de configurar. Si quires que te explique como hacerlo, al final
del libro tendre una seccion para eso.
Este comando es muy util ya que habre una interfas grafica para mostrarnos el repositorio actual a la izquierda y el modificado con los nuevos commits
a la derecha, de esta manera comparar con mayor presicion y tomar una mejor decicion


        
