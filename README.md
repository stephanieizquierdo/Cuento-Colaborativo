# Cuento Colaborativo :book:

Guía básica de git en la cual cada usuario escribe frases y se va formando así un cuento.

### Creación de cuenta

Para empezar, lo más sencillo es crearse una cuenta mediante github.

Si sos de la FIUBA podes adquirir una **cuenta pro gratis** con tu mail  @fi.uba.ar : [ACA](https://education.github.com/pack) (Si ya tenes una cuenta podes cambiar de mail y luego pedir el beneficio)


### Instalación:
#### Linux:
Desde la terminal ingresar lo siguiente:

```console
sudo apt install git
git config --global user.name "nombre"
git config --global user.email "mail"
```

#### Para otros sistemas operativos ingresar [aca](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## Colaborar con el cuento :pencil:

### Fork

Para comenzar primero se debe "forkear" este repositorio desde github. Esto se hace clickeando en el boton `fork` que aparece arriba a la derecha.

Cuando se hace un fork de un repositorio, se crea un nuevo repositorio en tu cuenta, con una URL diferente (fork). Acto seguido tenes que hacer un clon de esa copia para que hagas tus cambios. Mientras tanto el repositorio original sigue intacto.

### Clone

Una vez creado el fork, podemos hacer una copia del repositorio en nuestra PC para editarlo.

En la terminal debemos poner:

```console
git clone ACA-VA-EL-LINK-DEL-REPO-A-CLONEAR
```
En este caso:

```console
git clone https://github.com/TUUSUARIO/Cuento-Colaborativo.git
```
Esto nos crea un repositorio local desde el fork de github.


### Add y Commits

Ahora que ya tenes los archivos, podes modificarlos a gusto!!

La idea de este repo es que te dirijas a la parte de cuento.md y agregues una frase, no hace falta que te leas toda la historia, la idea es ver que surge de la espontaneidad. _Subir cosas familyfriendly_ :eyes:

Luego de que hayas hecho tus cambios debes agregarlos y commitearlos para ir guardandolos localmente en tu repositorio.

```console
git add cuento.md
git commit -m "DESCRIPCION DE LOS CAMBIOS"
```

Con el comando -m agregamos un mensaje a nuestro commit, recorda que debe ser descriptivo y consiso. Estos mensajes sirve mucho para informar nuestros cambios sin necesidad de ver los archivos modificados.

### Actualizar el Fork

Al ser el repositorio original público, más personas pueden estar haciendo cambios como vos y el repo original se va actualizando con estos. Para asegurarnos que tenemos la última ultisima versión y tenemos los archivos actualizados, podemos crearnos un repositorio remoto "upstream" que apunte al repositorio original:

```console
git remote add upstream https://github.com/stephanieizquierdo/Cuento-Colaborativo.git
```
Luego debemos bajarnos los cambios del repositorio original con un **pull**:

```console
git pull upstream master
```

Y por último mergeamos los cambios desde el original a nuestro fork.

```console
git merge upstream/master
```

### Push

Ahora para subir nuestros cambios locales al repositorio online, hay que "pushear" nuestros commits. El repositorio online es conocido por git como `origin`. Y la rama a la cual queremos pushear es a la principal, `master`. **Acordate de pullearte los cambios antes!**

```console
git push origin master
```

#### En caso de confilctos:
Los conflictos aparecen cuando se escribió sobre una versión antigua de lo que se editó. Para esto, luego de que salga el mensaje de conflicto, debes ir a los archivos afectados, en este caso seria cuentos.md y veras ago como `<<<<<<<<HEAD` y luego un  `<<<<<<<<<<< @4324324` donde head es lo que estaba subido al repo original antes de tus cambios y la segunda parte son tus cambios en la version anterior. Deberas solucionar esto dejando como quedaria el archivo con lo ultimo subido al original y tus cambios (sin los <<<), guardarlo y luego hacer un 

```console
git rebase --continue
```
luego de eso, podes efectivamente hacer el push.

Nota: en este caso al tener solo una rama, el git rebase es muy parecido al merge. En caso de tener mas ramas es preferible usar un merge.

### Pull Request

Para finalizar solo queda hacer una Pull Request que es informarle al autor original que querés hacerle cambios a su repositorio, esta debe realizarse desde el repositorio del autor del repo en github.

Para esto debes clickear en el botón `new pull request` y decirle que queremos mergear desde un fork, hasta la rama master del repositorio original.

Si el autor original acepta los cambios, se hace el merge y pasan todos los commits de tu fork al repo original.

Después de eso ya se puede borrar el fork y los cambios deberían reflejarse en el repo original.
