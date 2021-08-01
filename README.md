# Cuento Colaborativo :book:

Guia basica de git en la cual cada usuario escribe frases y se va formando asi un cuento.

## Instalacion de git y creaccion de cuenta

Para empezar, lo más sencillo es crearse una cuenta mediante github.

Si sos de la FIUBA podes tener **cuenta pro gratis** con tu mail  @fi.uba.ar : [CuentaPRO](https://education.github.com/pack) (Si ya tenes una cuenta podes cambiar de mail y luego pedir el beneficio.)


### Instalacion:
#### Linux, distribucion basada en Debian:
Desde la terminal ingresar lo siguiente:

```console
sudo apt install git
git config --global user.name "Mi nombre"
git config --global user.email "Mi mail"
```

#### Para otros sistemas operativos ingresar [aca](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## Colaborar con el cuento :pencil:

<p align="center">
<img src="https://www.earthdatascience.org/images/earth-analytics/git-version-control/git-fork-clone-flow.png"
     alt="git fork clone flow"
    /
    >                                                                                         
</p>        
### Fork

Para comenzar primero se debe "forkear" este repositorio desde github. Esto se hace haciendo click en el boton `fork` que aparece arriba a la derecha.

### Clone

Una vez creado el forkear, podemos hacer una copia del repositorio en nuestro PC para editarlo. En la terminal debemos poner:
```comand
git clone https://github.com/TUUSUARIO/Cuento-Colaborativo.git
```
Esto nos crea un repositorio local desde el fork de github.

### Commits

Ahora que ya tenes los archivos, podes modificarlos a gusto!!

La idea de este repo es que te dirijas a la parte de cuento.md y agregues una frase, no hace falta que te leas toda la historia la idea es ver que surge de la espontaneidad. _Subir cosas familyfriendly_ :eyes:

Luego de que hayas hecho tu cambio debes commitearlo, esto te va guardando localmente en el repositorio los cambios que hiciste.

```comand
git commit -m "DESCRIPCION DE LOS CAMBIOS"
```

Con el comando -m agregamos un mensaje a nuestro commit, recorda que debe ser descriptivo y consiso. Estos mensajes sirve mucho para informar nuestros cambios sin necesidad de ver el codigo.

## Actualizar el Fork

Al ser un repo publico, mas personas pueden estar haciendo cambios como vos y el repo original se va actualizando con estos. Para asegurarnos que tenemos la ultima ultisima version y estamos actualizados podemos añadir un repo remoto "upstream" que apunte al repositorio original:
```comand
git remote add upstream https://github.com/stephanieizquierdo/Cuento-Colaborativo.git
```
Luego debemos bajarnos los cambios del repositorio original con un **pull**

```comand
git pull upstream
```
Procedemos volviendo a la rama principal de nuestro fork

```comand
git checkout master
```

Y por ultimo mergeamos los cambios desde el original a nuestro fork

```comand
git merge upstream/master
```

## Push

Ahora para subir nuestros cambios locales al repositorio online, hay que "pushear" nuestros commits. El ropositorio Online es conocido por git como `origin`. Y la rama a la cual queremos pushear es a la principal.

```comand
git push origin master
```

## PullRequest

Por ultimo solo queda hacer una Pull Request que es informarle al autor original que querés hacerle cambios a su repositorio, esta debe realizarse desde github.
Para esto debes ir a tu fork y clickear en el botón `new pull request` y decirle que queremos mergear desde un fork, hasta la rama master del repositorio original.

Si al autor original acepta los cambios, se hace el merge y pasan todos los commits de tu fork al repo original.

Después de eso ya se puede borrar el fork y los cambios deberían reflejarse en el repo original.
