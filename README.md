# miniBook-AboutGit
Transladando mi poco conocimiento sobre git a un mini libro, el cual espero que ayude a muchos compañeros

## Prologo
La idea de hacer un libro surgió de imprevisto, no estaba planeado y comenzó como una broma, “¿Y si hago un libro de Git? Jajajaja”, pero en mi cabeza pasó la típica idea:

“NO SOY UN ESCRITOR, NADIE LO LEERÁ Y NO ESTOY PREPARADO PARA ESTO”

Aquí solo leo “NO”, “NO”, “NO”, siempre es no, “NO estoy listo para colaborar con mi equipo”, “NO me siento capaz de destacar en la competencia”, “NO me siento listo para buscar trabajo”, cuantas veces al día decimos “NO”, en todas esas ocasiones perdemos oportunidades que pueden cambiar nuestro futuro… ¿Y si en verdad era “no”? Si te atreviste a dar el primer paso y no salió como esperabas esta perfecto, hasta puede que sea mejor para ti porque te da la oportunidad de darte cuenta que te falta, en que puedes mejorar y crecer. No te rindas.

¿Cómo me animé y cómo creo que tú también te puedes animar a cumplir tus metas? ¡Comienza! Alguien no vendrá y te obligará a dar el primer paso, solo tú tienes esa decisión y es lo mas hermoso que podrás experimentar, saber que solo tu puedes cambiar tu futuro y esta en ti guiarte para lograrlo. Si ya comenzaste y te diste cuenta que no es lo tuyo, esta bien puedes dejarlo nunca te diría que continues con algo que no te apasiona lo importante es darse cuenta a tiempo.
En mi caso aunque ya tenía la idea desde hace un tiempo persiguiendome fue recién por aburrimiento que comencé a escribir esta guia/libro, estaba en la clase de matemática y después de mucho tiempo no me sentaba solo, talvez si hubiera sido lo contrario no me sentía aburrido nunca hubiera comenzado y mucho menos tu podrías leer esto. A veces pequeños eventos pueden cambiar grandes cosas, es por eso que otra vez te pido que no dejes de pasar oportunidades.

¡Es momento de ponerse una meta! Nada llega por sí solo, ¿Todo siempre te sale bien, apruebas los exámenes sin esfuerzo y te crees muy especial? No eres nadie y no llegarás a ningún lugar con ese pensamiento, si por el contrario confias tu ángel guardián y esperas que este te solucione tus problemas, estás en una peor situación que el anterior caso. Nada, ningún certificado, ninguna acreditación, ninguna universidad te puede asegurar que tendrás éxito en la carrera que escogiste, solo depende de ti.

Pondrás la música que más te guste, cierras los ojos, y te responderás estas dos preguntas, ¿Quién quiero ser acá a 5, 10, 15 años? La fecha la escoges tú, ¿Si sigo con este estilo de vida, lo podré conseguir? Adelante haz lo que te dije.
Piensalo detenidamente el tiempo y las veces que creas necesario, espero profundamente esto te pueda ayudar en tu crecimiento personal. Una vez más te diré: ¡No te rindas!

Un poco de mí, en el momento que escribo esto soy un estudiante de primer año de la carrera profesional Ingenieria de Sistemas de la Universidad Nacional de San Agustín de Arequipa, pero mi historia no comienza aquí, sino un poco más de un año antes de comenzar mis estudios, intentaré no entrar en detalles ya que el cómo comencé daría para varias hojas y no quiero que te aburras, en ese tiempo estaba un poco perdido sobre qué quiero de mi vida, estaba frustrado por ser como soy y no poder cambiar eso que me hace diferente y ni que decir sobre mi familia, se podría decir que estaba esperando lo que viniera “total no puedo hacer nada”. Por casualidad me meti a un pagina que me guio por el trayecto de “no saber nada” hasta “sentirme cómodo con mi conocimiento y no tener miedo a superar los obstáculos que me ponga el destino”. Aprender de blogs y texto plano que nisiquiera esta en tu idioma natal es complicado, no tener a nadie para preguntarle tus dudas e inquietudes es frustrante, ¿Por que no me rendi? Porque tenía un sueño ¡No soy menos que los demás! !¡Demostraré que no importa como soy sino que puedo llegar a ser! Esa meta me dio ánimos de continuar hasta finalizar mi aprendizaje que me proporcionaron y me sigue animando cada día al despertar, porque lo voy a lograr.

Este prólogo ya se hizo extenso por lo que solo me queda pedirte que te quedes con la siguiente reflexión y la repitas antes de irte a dormir.

¿QUE HE HECHO HOY QUE ME HACER MÁS A QUIEN QUIERO SER ACA A 5 AÑOS?


## Índice

### 1. Introducción
### 2. Teoría
### 3. Instalación y configuración
### 4. Lista y explicación de comandos
#### 4.1. Local
#### 4.2. Ramas
#### 4.3. Remoto
### 5. Conceptos útiles
### 6. Flujos de trabajo
### 7. Buenas Prácticas
### 8. Stash

## Introducción
### ¿Qué es este repositorio?
Creo este repositorio para dar seguridad a mis conocimientos adquiridos, además de dejar escrito lo que aprendí y en especial mi punto de vista como desarrollador que, al igual que mis compañeros, está en constante aprendizaje.

### ¿Qué es git?
Git es un software de código abierto, diseñado originalmente por el creador de Linux...<br>
Si bien la historia de git, de dónde sale, cuál fue la necesidad de crearlo, por qué en la actualidad solo escuchamos de git y no de otro software que cumpla la misma función, es muy interesante y vale la pena entenderlo; en este repositorio solo se hablará de la parte práctica. Entonces, ¿qué es git? <br>
Git es un software de control de versiones y copias de seguridad, este se basa en repositorios en los cuales se encuentra el código del proyecto y el histórico de los cambios.

Un repositorio puede ser local o remoto, estos últimos son los que nos permiten trabajar de manera colaborativa.
Cada repositorio tiene una rama `main`; cuando nombramos ramas debemos pensar en estas como una línea de tiempo en la cual se puede retroceder, dividir y fusionar.

Git nos ayuda a llevar ese registro de cambios que hacemos a nuestro código y además darnos la seguridad de que nuestro código puede retroceder a una versión anterior.

## Teoría

### Los tres estados de los archivos en Git
Nuestro repositorio contiene los archivos de nuestro proyecto, estos archivos pueden tener diferentes estados, cada uno con un propósito:

- **Modified** (modificado): Este estado es al que pasa un archivo que alteramos en algún aspecto, ya sea borrar, añadir o modificar una línea, estos cambios todavía no están preparados para ser confirmados.

- **Staged** (preparado): Cuando marcamos nuestros archivos con este estado le estamos diciendo a Git que están preparados para ser confirmados. Estos se encuentran en un estado transitorio para luego ser confirmados.

- **Committed** (confirmado): Esto quiere decir que nuestro archivo se encuentra confirmado y guardado en nuestro repositorio local. La acción de pasar de `stage` => `committed` se llama "commit".

#### NO ENTIENDO, AYUDA 
Es normal que esto te confunda, la mejor forma de entender los estados de los ficheros en Git es pensando en una sesión de fotografía. Con un panel, una cámara y los objetos que queremos fotografiar.

- Al principio nuestro panel va a estar vacío ya que no tenemos nada nuevo a lo que queramos fotografiar.

- Oh, uno de nuestros objetos cambió de color. Esto representa el estado de `Modified`.

- Como nuestro objeto cambió, así que lo preparamos y lo dejamos dentro del panel. Mover nuestro objeto y prepararlo representa la acción de `add` y el panel representa el estado `Staged`.

- Al parecer más objetos han estado cambiando, de modo que también los preparamos y los dejamos dentro del panel. Podemos preparar varios archivos al mismo tiempo, esto es porque algunos cambios tienen relación directa con otros, de modo que los podemos guardar juntos.

- Ahora con todos nuestros objetos listos para la fotografía, procedemos a tomar la foto, de esta manera no nos olvidaremos de este momento. La acción de tomar la foto hace referencia a la acción `commit` ya que con esto guardamos nuestros cambios además de darles un nombre o asunto.

- ¡Ya tenemos nuestra foto! Ahora nunca olvidaremos este momento, procedemos a dejar nuestros objetos en su lugar, fuera del panel. Esto representa el fin del ciclo de vida de los ficheros, de este modo después de hacer `commit` pasarán a estar sin modificar otra vez, de modo que podemos repetir el ciclo.

Espero que de esta manera hayas podido entender con más claridad cómo funcionan los estados de los archivos y las acciones que pueden modificarlos.

### Git y GitHub no son lo mismo
Parece un poco obvio pero todavía escucho personas pensar eso, y no tiene nada de malo
a simple vista cumplen la misma función.

- Git: Es un sistema de versionamiento y control, es decir, nos ayuda a controlar nuestros cambios. Se ejecuta de manera local y almacena los repositorios en nuestra máquina.

- GitHub: Es un servicio de hospedaje remoto de nuestros repositorios, ofrecido actualmente por Microsoft, y no es el único que nos ofrece tal cosa. Por ejemplo, tenemos a GitLab o BitBucket, los cuales nos ofrecen lo mismo. En resumen, GitHub solo almacenará nuestros repositorios en la nube, estando así listos para poder usarlos desde cualquier parte o momento, ya sea por nosotros o por un equipo de desarrollo.

## Instalación y configuración
Aquí se darán algunos pasos y recomendaciones para descargar y configurar Git, pero no reemplaza leer la documentación de su página oficial. Además, solo veremos las formas de instalarlo en algunos sistemas operativos.

### Comprobando si ya tengo instalado Git
Esto es muy fácil, solo es ejecutar el siguiente comando en la terminal. Una aclaración: siempre que vean un signo de dólar anteponiendo al comando, quiere decir que ese comando se ejecuta en una terminal. No es necesario y no se debe copiar directamente en esta.

        $ git --version

Si tenemos instalado git nos saldra lo siguiente:

        git version 2.41.0

Si, por el contrario, el mensaje de vuelta es algo como `git: command not found`, es porque aún no tenemos instalado Git.

### Instalando Git
- Ubuntu: Tan simple como ejecutar

        $ apt-get install git

- Windows: También es simple, dirígete a la página oficial y descarga el instalador. Luego, sigue los pasos y dale "Siguiente" a todo.


### Configurando mi nombre y correo

Al hacer cambios en el repositorio, estamos modificando archivos que podrían ser muy importantes. Ya sea en el caso de estar trabajando solo o en un equipo, por esta razón, tenemos que firmar con nuestro nombre y correo cada cambio que hacemos. De esta manera, los demás integrantes podrán saber quién hizo qué cosa y así tener un mejor control.

Ejecutamos los siguientes comandos, cambiando la información con la correspondiente:

        $ git config --global user.name "miNombreDeUsuario"
        $ git config --global user.email "miCorreo@example.com"

En mi caso seria de la siguiente manera:

        $ git config --global user.name "Diegoo11"
        $ git config --global user.email "ynoacamino@gmail.com"

Explicación: Con la bandera `--global` le estamos diciendo que queremos que esta configuración
se guarde y esté disponible para todos nuestros repositorios, también podemos querer
que solo se guarde en un repositorio en específico, para ese caso nos dirigimos a la carpeta raíz de este
y ejecutamos.

        $ git config user.name "miOtroNombre"

De esta manera se guardará sólo en el repositorio específico.

### Listar la configuración
Un comando muy útil que uso siempre antes de abrir mi editor de código, es listar mi configuración ya sea porque no estoy seguro cual será mi rama por defecto o aún más importante, saber con que correo estoy trabajando, ya que si uso un correo y nombre diferente del que tienen conocimiento mi equipo de desarrollo causará confusión y es lo que menos queremos. 
<br>
Para esto usaremos el siguiente comando.

        $ git config --list

Nos mostrará toda nuestra configuración global, en caso de solo querer la configuración local del repositorio podemos ejecutar el siguiente.

        $ git config --local --list

## Lista y explicacion de comandos
Los comandos listados acontinuacion tendran la siguiente forma

        $ <comando> <argumento|opcional> <archivo>
        $ ...variantes del mismo comando
        
        Breve expliacion.
        Casos de uso.
        Opinion.

### git init : Inicializar un repositorio
Un dato curioso es que cuando ya iba por más de la mitad del libro me di cuenta que no explique cómo inicializar un repositorio, mi error.

Para inicializar un nuevo repositorio basta con ejecutar `git init` en la carpeta donde queremos que sea el repositorio o sino decirle en donde queremos inicializarlo pasándole una ruta desde de `init`. Esto creará una carpeta `.git` en donde se guardaran todas nuestras versiones e información necesaria para esta, por defecto esta carpeta esta oculta y es mejor dejarla así ya que cualquier cambio podría dejar inutilizable el repositorio local

        $ git init
        $ git init <ubicacion del directorio>


### git restore : Eliminar los cambios hechos a un archivo
Con el más mínimo cambio nuestro archivo pasará del estado `committed` a `modified` pero a veces modificamos un archivo por error y queremos volver a la última vez donde nuestro archivo estaba `committed`.<br>
Para esto usamos `git restore <ruta del archivo>`, tenemos de tener mucho cuidado ya que
de hacer accidentalmente podemos perder muchas horas de trabajo.

        $ git restore archivo.txt
        $ git restore archivo.txt archivo2.md
        $ git restore .


Tenemos que tener en cuenta que tanto `archivo.txt`, `archivo.txt archivo2.md` y `.` son rutas ya que eso es lo que acepta la mayoría de comandos de Git.

### git add : Anadir archivos al area de `stage`

        $ git add archivo.txt                   (1)
        $ git add archivo.txt archivo2.md       (2)
        $ git add .                             (3)

Git add sirve para pasar un archivo del estado `modified` al estado `staging`. <br>

|   Archivos    |   Modified    |   Staging     |
|---------------|---------------|---------------|
|   archivo.txt |   X           |               |
|   archivo2.md |   X           |               |

Después de haber ejecutado los mandos nuestros archivos que inicialmente tenían el estado de `modified` pasaron a estar en `staging`.

|   Archivos    |   Modified    |   Staging     |
|---------------|---------------|---------------|
|   archivo.txt |               |   x           |
|   archivo2.md |               |   x           |


### git reset : Sacar ficheros del area de `stage`
Hay veces donde escribimos mal la ruta de un archivo y lo añadimos por error al área de `stage`. <br>
No hay problema, lo sacaremos. Con el comando `git reset <ruta>` podemos sacar esos archivos
que no queremos que estén en `stage`.


        $ git reset archivo.js
        $ git reset archivo.js README.md
        $ git reset .

Estado inicial:

|   Archivos    |   Modified    |   Staging     |
|---------------|---------------|---------------|
|   archivo.js  |               |   x           |
|   README.md   |               |   x           |

Después de: `git reset .`

|   Archivos    |   Modified    |   Staging     |
|---------------|---------------|---------------|
|   archivo.js  |   x           |               |
|   README.md   |   x           |               |


### git commit : Guardando con commit
Si no leiste 'Los 3 estados de los archivos en Git' te recomiendo encarecidamente que le des una leída antes de continuar.<br> Hay varias formas de hacer commit, aquí te presento algunas.

        $ git commit                                (1)
        $ git commit -m "<mensaje>"                 (2)
        $ git commit -m "<mensaje>" <ruta>          (3)

- **(1):** Guarda el commit de todos los archivos que esten en el area de `staging`, ademas habre un editor de texto para incluir el asunto del commit.

- **(2):** Guarda el commit de todos los archivos que esten en el area de `staging`, mas no habre nigun editor ya que le pasamos el mensaje del commit como parametro.

- **(3):** Cumple la misma funcion que **(2)** pero solo guarda un archivo en particular y los demas los ignora.

Explicacion:<br>
Digamos que ya editamos nuestro archivo `App.js`, decidimos que terminamos de hacer los cambios correspondientes así que ejecutamos.

        $ git add App.js

De paso añadimos otros archivo que también están listos.

        $ git add README.md
        $ git add index.js
        $ git add package.json

Ahora estamos listos para hacer nuestro primer commit.

        $ git commit -m "mi primer commit"

De esta manera terminamos el ciclo de vida de los ficheros y pasan a estar otra vez al estado `committed`.

                          edit                add
        ----> commited ---------> modified ---------> staged ----
        |                                                        |
        |                                                        |
        |                                                        |
        ---------------------------------------------------------
                                    commit



### git reset : Quiero eliminar mi commit y devolver una versión anterior
¿Qué ha pasado?, al parecer cometiste un error al subir el commit y quiere volver a un version
anterior, no hay problema con `git reset` podemos lograrlo pero antes:

- `git reset` puede ser muy peligroso ya que alteramos los commis osea los nodos de nuestra rama esto puede causar problemas tanto para nosotros como para nuestro equipo de desarrollo si no se hace con precaución.

- Siempre podemos optar por volver a editar nuestro fichero y hacer otro comint solucionando los cambios, a veces esta es la mejor opción ya que no solo no alteramos el flujo de la rama sino dejamos constancia del error.

Si aún así lo necesitas, adelante.


        $ git reset HEAD~1                          (1)
        $ git reset HEAD~i                          (2)
        $ git reset <hash>                          (3)

- **(1):** Con `HEAD~1` le estamos diciendo que retroceda un commit anterior.

- **(2):** En este `i` se debe cambiar por el número de commits que queremos retroceder.

- **(3):** En caso de tener el hash del commit al cual nos queremos trasladar podemos usarlo también.

### git checkout : Viajar en el tiempo o entre commits
Tal vez uno de los comando más interesantes en mi opinión y el que más recomiendo usar sobre comandos como `git reset` o `git rebase` ya que `checkout` no altera la rama en ningun sentido, solo nos permite viajar y transladarnos entre commits y así rebuscar entre el código que nos interesa.<br>
Algo importante de aclarar es que cuando nos movemos entre commits con `checkout` HEAD se encuentra en un estado `separado` que no nos permite editar archivos pasados.

        $ git checkout HEAD~1
        $ git checkout HEAD~i
        $ git checkout <hash>

¿Ya te aburriste de ver tu código de commits antiguos y quieres volver al commit más reciente? Ejecuta este comando.

        $ git switch <nombre de la rama>

### Introduciendo HEAD
HEAD no es la cabeza de la rama, eso hay que tenerlo claro, podemos pensar en HEAD como un GPS para saber con precisión en qué parte de la rama nos encontramos. <br>
Explicación con gráfico para entender con facilidad.

        main | git init ----> A ----> B ----> C ----> D (HEAD)

Podemos observar la rama `main` la cual inicia con git init, luego se hacen los siguientes commits, A, B, C, D; siendo D el último por lo tanto sería nuestro HEAD ya que es el último lugar donde nos encontramos. <br>
Pero ahora ejecutaremos `git checkout` para movernos entre commits.

        $ git checkout HEAD~2

Y nuestro gráfico quedaría de la siguiente manera.

        main | git init ----> A ----> B (HEAD) ----> C ----> D

Podemos observar como HEAD nos sigue y apunta al commit donde nos encontramos.

Anteriormente vimos cómo deshacer un commit y para eso usamos el parámetro `HEAD~1`, este parámetro queria decir,
**un commit anterior a HEAD** o en caso de `HEAD~i`, **retrocede 'i' veces en commits a partir de HEAD**.

### Ignorando ficheros
Ya sea porque tenemos archivos innecesarios, claves privadas o carpetas con codigo de produccion tarde o temprano queremos ignorar algún fichero y de esta manera impedir que se muestre en el repositorio público, esto se logra escribiendo el nombre del archivo en el archivo `.gitignore`.

        .env
        dist
        public
        test.js
        app.test.js
        CLAVE_PRIVADA.js

De esta manera le estamos diciendo a git que no haga seguimiento de esos archivos.

### git rm : Ignorar archivos que ya tienen seguimiento
Hay veces que no nos damos cuenta o nos olvidamos de colocar el nombre en `.gitignore` no pasa nada lo solucionaremos. <br> Primero simularemos el posible caso.

        $ nvim clave.js
        $ git add .
        $ git commit -m "init project"

Ahora Git hará seguimiento de nuestra clave junto con todo el proyecto, para solucionarlo ejecutamos el siguiente comando.

        $ git rm --cached clave.js

Este comando solo hará que `clave.js` se deje de rastrear, si además queremo borrarlo tenemos este otro comando.

        $ git rm clave.js


### ¿Qué es una rama?
Antes dijimos que deberíamos pensar en los estados de commit como una sesión fotográfica, de la misma manera podemos pensar en una rama como un álbum de fotos.<br>
Por defecto nuestra rama se llamará `main` y estará formada por el historial de nuestros commits.

        main || git init <---- commit A <---- B <---- C (HEAD)

Podemos ver nuestra única rama `main` esta contiene nuestros commit, mas no es la única rama que podemos tener podemos crear ramas a partir de otra en nuestro caso `main` pero esto lo veremos un poco más adelante.

### git branch : Creando ramas
Para esto usaremos:

        $ git branch <nombre>                       (1)
        $ git switch -c <nombre>                    (2)

- **(1)** Crea la nueva rama pero no cambiamos a esta.
- **(2)** Crea la nueva rama y cambia a esta automáticamente.

Ejemplo:<br>
En el siguiente ejemplo crearemos una rama con el nombre `newsRama`.

Estado inicial(antes de crear la rama).

        main || git init <---- A <---- B (HEAD)

Después de crear la nueva rama a partir del commit 2, por lo que ejecutamos lo siguiente.

        $ git branch newRama

        main || git init <---- A <---- B
                                        \
                                         \
                               newRama || B (HEAD)

Como podemos ver nuestra rama desciende del commit B por lo que se crea como una copia exacta de este. A partir de este punto cada rama es independiente una de otra, cada una puede continuar con commits que la hagan crecer, eliminarse, o incluso fusionarse con otra rama en algún momento.<br>
En el siguiente ejemplo cada rama seguirá creciendo por su lado y la rama `main` se volverá a dividir(bifurcar).

                               otraRama || D <---- H
                                          /
                                         /
        main || A <---- B <---- C <---- D <---- J <---- K (HEAD)
                         \
                          \
                newRama || B <---- F <---- G


### git branch, git switch : Comandos útiles para manejar ramas
    
        $ git branch

Muestra las ramas disponibles y la rama en la que nos encontramos, está marcada con un asterisco.

        $ git switch nombreDeLaRama
        $ git switch -

Git switch sirve para cambiar entre ramas, pasandole como parametro el nombre de la rama, o si solo queremos movernos a la rama donde estábamos previamente podemos usar el `-`.

### git merge : Fusionando ramas
Llegó el momento, la pesadilla de muchos 'Fusionar ramas', más no hay que asustarse aquí lo entenderás de una vez por todas y nunca más le tendras miedo.

        $ git merge nombreDeUnaRama

Para esto vamos a imaginar que tenemos 3 commits, A, B, C, en C es que nos damos cuenta que queremos probar un nuevo framework o utilidad mas no queremos comprometer al proyecto principal para esto creamos una rama llamada `experiment`.

        main || A <----- B <----- C
                                   \
                                    \
                       experiment || C

Ya con nuestra rama creada podemos continuar trabajando en el proyecto principal y al mismo tiempo probar el nuevo framework, por lo que continuaremos haciendo commits a ambas ramas.

        main || A <----- B <----- C <---- D <----- E
                                   \
                                    \
                       experiment || C <---- X <---- Y (HEAD)

Todo a ido bien con las pruebas del nuevo framework y decides que es lo mejor para el proyecto por lo que ahora quieres unir las ramas para tener tanto el nuevo framework como los cambios que fuiste avanzando mientras probabas este.

Para esto debemos tener claro qué queremos hacer, queremos que `main` contenga los cambios de `experiment` y dejar a `experiment` intacto? o queremos que `experiment` contenga los cambios de `main` y dejar a `main` intacto?

Normalmente es la primera opción ya que `main` debe contener los cambios principales y `experiment` desaparecer después de cumplir su función, probar una nueva funcionalidad. Por lo que tomada una decisión nos aseguramos que estamos en la rama donde queremos ver reflejados los cambios. Ejecutamos:


        $ git switch main


        main || A <----- B <----- C <---- D <----- E (HEAD)
                                   \
                                    \
                       experiment || C <---- X <---- Y

Ya habiéndonos movido ejecutamos

        $ git merge experiment

Después de ejecutar git merge nos quedaría del siguiente modo:

        main || A <----- B <----- C <---- D <----- E <---- F
                                   \                     /
                                    \                   /
                       experiment || C <----- X <----- Y

### git branch -d : Eliminando ramas
Ya habiendo fusionado nuestras ramas con la principal probablemente querramos borrarla ya que ya no nos es de uso. Para esto usaremos un comando ya conocido pero con un parámetro nuevo, `-d` o `-D`.

        $ git branch -d <nombreDeRama>              (1)           
        $ git branch -D <nombreDeRama>              (2)

- **(1):** Eliminar la rama seleccionada pero se asegura de haberle dado un uso primero, como hacer una pull request o un git merge, de otro modo no te dejará eliminarlo. Esto es muy útil para no tener accidentes y perder muchas horas de trabajo.

- **(2):** Elimina las ramas sin ningún tipo de advertencia, a veces es lo que queremos ya que habrá casos donde no le hayamos dado ningún uso a esta, por lo tanto debemos eliminarla sin más

### git remote prune origin : Sincronizando ramas
Pero qué pasa si llevamos varios días sin sincronizarnos a nuestro repositorio remoto y además hemos creado varias ramas que no llegaron a nada en el repositorio local, o en el caso que las ramas que descargamos inicialmente ya no se encuentran en el repositorio remoto sino que las eliminaron.<br>

        $ git remote prune main
        $ git remote prune <nombreDelRepositorioRemoto>

Para sincronizar nuestras usamos `git remote prune origin`, "ahhh no entiendo la sintaxis", me imagino que estarás diciendo algo así pero está bien que no entiendas ya que aun no vemos git desde la parte de repositorios remotos, aun así me gustaría explicárselo de modo que cuando lleves a esa parte puedas regresar y entender con más claridad. <br>

- `git remote` con esto le decimos a Git que nos referimos a uno de los repositorios remotos (si, podemos tener más de uno).
- `prune` es la acción a realizar, en este caso eliminar ramas, "prune" traducido al español significa "podar".
- `origin` con esto nos referimos al nombre del repositorio remoto, ya que podemos tener varios debemos darles un nombre para referenciar a uno, por defecto se le asigna origin por lo que la mayoría de veces usaremos este.

### Trabajando con repositorios remotos
Ahora que sabes cómo controlar tu flujo de trabajo ya te encuentras listo para compartir tu código con el mundo, espero mucho de ti. Tal vez no estás convencido de subir tus repositorios a paginas como GitHub o GitLab ya que piensa que no es necesario y hasta pesado, no temas yo te haré cambiar de opinión.

#### ¿Por qué hacer mi código público? ¿Qué gano yo?
- Colaboración: Al subir tu código a un repositorio público tienes la oportunidad de trabajar con más personas en un solo proyecto, retroalimentarse unos a otros y mejorar juntos.

- Llevar un portafolio: Se que pensaras que aunque subas lo que desarrollas nadie querrá ver tu trabajo, pero no es cierto cuando llegue el momento de buscar una oportunidad o demostrar tus habilidades te servirá tener tus trabajos listos y públicos desde que comenzaste a programar hasta tus proyectos más recientes e impresionantes. ¡Todo cuenta!

- Código abierto: ¿Por qué contribuir al código abierto? Pues nos ayuda a trabajar colaborativamente con otros desarrolladores y recibir feedback sobre nuestro código, es un ganar ganar. Aún no estás convencido? Pues quiero recordarte que muchas de las herramientas que usamos día a día se las debemos al código abierto, sin irnos muy lejos está la plataforma virtual de la UNSA, así es, "Moodle" es de código abierto y como todos los proyectos de código abierto es mantenido por desarrolladores que aportan su grano de arena para construir tecnologías increíbles.

- Mejoramiento personal: Si subimos un repositorio a GitHub, a menos que esté en privado, todos podrán ver tu código y juzgarlo y aunque suene feo es lo mejor. Recordemos que el desarrollador ya no escribe código para sí mismo sino que escribe para todo su equipo de desarrollo actual y el que lo reemplazará cuando este se vaya, esto quiere decir que tenemos que estar en constante mejoramiento de nuestras prácticas y una forma de lograrlo es haciendo nuestro código libre a miradas. Al menos yo cuando se esto entiendo que debo esforzarme más y seguir las buenas prácticas, mejorando constantemente.

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

        $ git remote add <nombre> <dirección del nuevo repositorio>

Ejemplo:
        
        $ git remote add origin git@github.com:Diegoo11/miniBook-aboutGit.git

Te acuerdas que anteriormente ya vimos `remote`, llegó el momento de entenderlo a la perfección

1. `remote`: le decimos que queremos acceder a la configuración de los repositorios remotos
2. `add`: en este caso queremos añadir una nueva dirección a nuestro repositorio
3. `<nombre>`: Hay que aclarar que podemos tener más de un repositorio remoto enlazado al mismo en local, entonces la forma de diferenciar uno del otro es darle un nombre, este por defecto es `origin` pero también podemos darle cualquier nombre
4. `<dirección>`: Aquí copiamos la dirección ssh de un repositorio remoto, de preferencia que esté vacío ya que así no tendremos problemas al subir los archivos por primera vez, por el contrario si ya contiene ficheros y estos llevan los mismos nombre podríamos estar en problemas ya que habrá conflictos.

#### Eliminar en enlace entre local y remoto

        $ git remote remove <nombre>

#### Listar los repostirios remotos

        $ git remote

#### Renombrar un repositorio remoto

        $ git remote rename <nombreActual> <nuevoNombre>

### git push : Subir commits a remoto
La palabra `push` traducida al español sería "empujar", y tiene todo el sentido porque queremos subir nuestros cambios a remoto empujandolos desde el local, empujamos lo commits que aún no están subidos a remoto.


        A ----> B ----> C ----> D ----> E ----> F
                        ^                       ^
                        |                       |
                    git push (1)            git push (2)

En el push (1) subimos los commits A, B, C; posteriormente seguimos trabajando y volvemos a hacer git push (2) en este caso subiremos los commits C, E y F ya que git sabes que commit ya están subidos en remoto y solo sube lo que son nuevos.

        $ git push                                  (1)
        $ git push <remoto> <rama>                  (2)

- **(1):** Aclaración, cuando no se envia ningun parametro después de `push` git asumirá lo siguiente, `git push origin <ramaActual>`, por lo que siempre sería mejor completar los otros parámetros en especial si tenemos varias ramas, ya que nos permitirá tener conciencia de en donde queremos hacer el push.

- **(2):** Ejemplo:

        $ git push origin main


### git pull : Sincronizar con remoto
Antes solo nos preocupamos por nuestros cambios pero ahora trabajamos con repositorios remoto y esto incluye que podemos tener cambios que nosotros no hicimos, sino que los hizo nuestro equipo de desarrollo, estos cambios no se sincronizan automáticamente con nuestro repositorio local para esto ejecutamos `git pull`. Con esto le estamos diciendo que sincronice los cambios con el remoto.

        $ git pull
        $ git pull <remoto> <rama>

### git fetch : Trae los cambios mas no altera tu espacio de trabajo

        $ git fetch
        $ git fetch <remoto> <rama>

Pero qué pasa si estamos trabajando en algo importante en local pero en remoto borraron o sobrescribiendo nuestro código, al hacer pull perderíamos nuestro avance y horas de trabajo, para esto existe git fetch. Trae los cambios mas no los fusiona automáticamente sino que nosotros tenemos que hacerlo, pero primero podemos ver que cambios hay y a que parte de nuestro proyecto se compromete. A continuación dejo comandos útiles que nos ayudaran con este propósito:

        $ git log origin/main

Con este podemos ver que commits no están en nuestro repositorio y archivos modifican pero nada más.

        $ git diff origin/main

Este comando nos proporciona cierta información aunque un poco confusa sobre los cambios en cada archivo, si bien puede ser útil en ciertos casos, lo normal es que se torne turbio cuando hay muchos cambios a diferentes archivos.

        $ git difftools origin/main

Antes de ejecutar este comando debemos tener configurada una herramienta para este, normalmente yo uso vim o neoVim para esta tarea ya que son las más fáciles de configurar. Si quieres que te explique como hacerlo, al final del libro tendrás una sección para eso. Este comando es muy útil ya que abre una interfaz gráfica para mostrarnos el repositorio actual a la izquierda y el modificado con los nuevos commits a la derecha, de esta manera comparar con mayor precisión y tomar una mejor decisión.


## Conceptos utiles
### Que es fork
Fork cuando hablamos de git es la acción de copiar el codigo de alguien es más, esta copia puede recibir cambios que talvez no han sido aprobadas por el dueno del repositorio original mas como es un fork ya no pertenece a este, más siempre esta copia apunta a su repositorio original

Debemos entender esto como una copia del código original que cambia para ser mejor sin afectar al proyecto original. Cuando haces un fork de un repositorio público, éste será tuyo y podrás modificarlo a tu gusto

### Como hacer un fork
En este caso usaremos github para hacer nuestro primer fork, no dirigimos al repositorio al que queremos hacer fork y buscamos en la parte superior derecha el botón `fork`, haciendo click a este crearemos nuestro fork y se almacenará junto a nuestros otros repositorios. Muy fácil.

### Aportando con Pull request
Imaginemos el siguiente caso: "Encontramos un proyecto de código abierto en github, nos parece muy interesante y prometedor pero tiene un error que provoca su cierre inmediato, como piensas que vale la pena ayudar a su desarrollo haces un fork al proyecto y editar su código desde el fork que creaste de esta manera solucionar el error que provocaba el cierre inmediato, pero... ahora como le haces llegar al creador la solución a su error?". Aquí entran las pull request.<br>
Una pull request es una solicitud de cambio o edición de código, son muy útiles para colaborar con personas ajenas al proyecto pero que tienen la intención de ayudar al desarrollo de este.

Volviendo al ejemplo anterior: "Teniendo conocimiento sobre una pull request hacemos una con nuestros cambios al proyecto principal. Con esto el dueño del proyecto será avisado y podrá revisar nuestra sugerencia de cambios, y la breve descripción que le proporcionamos junto a la pull request"

Podemos hacer pull request de cualquier tipo de cambio, desde cualquier rama a otra, claro si los cambios que desarrollamos tienen conflicto este se tiene que solucionar antes de aceptar continuar la pull request. Además no es seguro que sea aceptada ya que la decisión final la tiene el dueño original o su equipo de trabajo.

### Sincronizar y poner al dia mi fork

        $ git remote add <nombre> <direccionDelRepoOriginal>

Ejemplo: 
        
        $ git remote add upstream git@github.com:Diegoo11/miniBook-aboutGit.git

Te preguntaste para qué nos servirá tener vinculados dos repositorios remotos a un solo repositorio local? Pues aqui esta la razón ya que así podemos hacer `git pull upstream main` y traer todos los cambios del repositorio original a nuestro fork y no quedarnos desactualizados.

## Flujos de trabajo en Git
En esta sección daré introducción a las maneras más eficientes de trabajar en grupo usando git mas no se debe tomar como reglas estrictas ya que cada equipo es diferente y tiene habilidades y necesidades distintas, estas estrategias se deben tomar como ayuda para encontrar la mejor manera de trabajar en conjunto.

**Importante: Esta parte estaba planeado pero me percate**
1. NO tengo la experiencia necesaria para hablar sobre este tema y cumplir con el propósito del libro, si bien se la teoría no tuve la oportunidad de ponerla en práctica
2. Esto no significa que nunca continuaré con esta sección, solo la pospondre para en algún momento culminarla de la mejor manera posible.

## Buenas practicas
### ¿Cada cuánto se debe hacer un commit?
Es una pregunta que hasta hoy me cuesta decidirme por una respuesta, podemos pensar en que cada cambio por lo más minúsculo que parezca merece un commit y no estaríamos mal ya que ese cambio puede significar un cambio en toda la estructura y su funcionamiento o solo la remoción de un comentario obsoleto. Entonces cómo sabemos cuándo hacer un commit? <br>
Desde mi punto de vista hay ciertos criterios a seguir:
- Cada vez que sentimos que damos un paso adelante para llegar a la meta. Esto quiere decir que no debemos hacer commit por gusto ya que te confunde a ti como a tu equipo, commits como 'test', '.', '...', 'nada nuevo'.
- Agrupa commits. Me costó mucho entender este punto, yo era quien si veía que en un archivo hago lo mismo que en otro en lugar de hacer un commit de los dos archivos al mismo tiempo hacia un commit para cada uno. ¿Por qué? Porque me gustaba ver en mi barra de `contributions in the last year` muchos números. Ahora entiendo que esto es muy malo ya que volvemos a los mismo que el anterior punto "commits sin sentido", siempre que puedas intenta agrupar los archivos que tienen que ver con el mismo commit.

### Cómo nombrar a mis commits
Esta parte es importante para trabajar de manera cómoda con tu equipo, definir si los nombres de los commits estarán inglés o español, si usaran etiquetas o no, que tipo de commits usaran, etc. Primero se verá cuál es la manera correcta o la más aceptada de ponerle nombre a los commits en inglés.

- Usar la manera imperativa: <br>
Normalmente cuando nombramos commits usamos verbos en pasado cómo `added`, `fixed`, `removed`, etc. Pero no es correcto ya que no estamos diciendo que la acción ya ha pasado anteriormente y recién la estamos informando, si no queremos decir lo contrario, la acción sucedió en ese commit. Esto lo logramos escribiendo de manera imperativa

        new file added                  ❌

        add new file                    ✅

- No usar punto final ni puntos suspensivos: <br>
Usar punto final es totalmente innecesario, por otro lado los puntos suspensivos o "etc" da espacio a ambigüedad e inseguridad sobre lo que hace exactamente el commit.

- Usar etiquetas: <br>
Cuando trabajamos en un proyecto bastante grande o monorepositorios donde en un solo repositorio tenemos varios proyecto es útil usar etiquetas antes de los commit para añadir más significado a estos, a este tipo de commit se le llama commits semánticos y se escriben de la siguiente manera:

        <tipo> [alcance]: "descripcion"

En tipo podemos rellenar con los siguientes prefijos:

- feat: para una nueva característica para el usuario.
- fix: para un bug que afecta al usuario.
- perf: para cambios que mejoran el rendimiento del sitio.
- build: para cambios en el sistema de build, tareas de despliegue o instalación.
- ci: para cambios en la integración continua.
- docs: para cambios en la documentación.
- refactor: para refactorización del código como cambios de nombre de variables o funciones.
- style: para cambios de formato, tabulaciones, espacios o puntos y coma, etc; no afectan al usuario.
- test: para tests o refactorización de uno ya existente.

Y en alcance rellenamos con la parte a la que afecta este cambio, puede ser como: database, web, backEnd, o algún framework en particular

### Poner un buen nombre a tus ramas
Normalmente la razón de usar ramas es la de tener un orden y no chocar con otros
trabajos de tu equipo, por esto es necesario poder darles un buen nombre que nos
diga sin tener que revisar todos lo commits, su propósito. Aca te dejo algunas pautas

- Tener regularidad: Si usamos un estilo por defecto no podemos cambiarlo o usarlo solo en ciertas ramas o inadecuadamente, tenemos que seguirlo en todo el proyecto

- Usar prefijos: Para mostrar mas informacion a simple vista podemos usar prefijos para señalar el propósito de la rama como:

    - bug: Para solucionar un bug conocido
    - feature: Agregar una nueva característica
    - experiment: Experimentos con el código que nunca llegarán a producción
    - hotfix: Solucionar pequeños errores para la versión final

## Que es el stash
¿No te ha pasado que estás escribiendo código pero te das cuenta de un error en otros archivos muy distintos?<br>
Tienes dos opciones, borras tu trabajo actual y vas a solucionar el otro problema, o envías un commmit incompleto y vas a solucionar el otro problema, esto debido a que no podemos cambiar de ramas, hacer commit sin antes tener todo guardado correctamente.<br>
¿Cuál escoges? Yo escojo la tercera opción, el `stash`, almaceno mis cambios en el stash entonces cambio entre ramas y soluciono el problema
luego vuelvo y recupero mis cambios previos del stash. Muy fácil ¿verdad?

- Comando útiles con stash:<br>
Como almacenar los cambios en el stash.

        $ git stash
        $ git stash push

Ten cuidado con los archivos recién creados y que aún no tienen un commit previo, pues al intentar almacenarlos en el stash estos se borraran, para evitar eso usamos:

        $ git stash push -u

- Listar los stash:<br>Este comando es muy útil ya que el stash tiene forma de pila, último en entrar primero en salir, nuestras cambios se almacenan con un hash(incomprensible para nosotros), para poder diferenciar entre cambios además del hash tenemos un índice y de este nos apoyaremos para indicar y especificar un cambio en especifico.

        $ git stash list

- Recuperar el último stash:<br>
Con pop recuperamos el último stash y por su naturaleza(una pila) recuperamos el que esté más arriba de la pila, al mismo tiempo que lo eliminamos

        $ git stash pop

En caso que no lo queramos eliminar y solo recuperar podemos usar

        $ git stash apply


- Crear una rama apartir de un stash:<br>
Hay veces donde los cambios son bastante grandes y no hay razón para no almacenarlos en una rama aparte, aquí podemos usar

        $ git stash branch <nombreDeRama> <i>

Donde `i` es el índice del stash desde el cual queremos nuestra rama

