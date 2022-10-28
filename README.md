Introducción
------------

Proyecto con las especificaciones PUSH de la API **Stockist-Phoenix-v2** de publicación de tarifas e inventario de hotel y recuperación de reservas

Web creada con el generador de documentación para API's [slate](https://github.com/lord/slate).

¿Cómo utilizar?
------------------------------

### Requerimientos

Se necesita:

 - **Linux or Windows X** — Windows may work, but is unsupported.
 - **Ruby, version 2.2.5 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal

### Arrancar el proyecto en local

1. Clonar *este repositorio*
2. Inicializar y arrancar:

```shell
bundle install
bundle exec middleman server
```

*NOTA*: Si se producen errores al ejecutar bundle install, seguir las instrucciones al pie de la letra de esta [respuesta stackoverflow](http://stackoverflow.com/questions/8100891/the-json-native-gem-requires-installed-build-tools/8463500#8463500)

Abrir **http://localhost:4567** y Whoa!!

### Deploy cambios
Slate tiene soporte para publicar directamente los cambios en github pages. Información detallada [aquí](https://github.com/lord/slate/wiki/Deploying-Slate)

Pasos a seguir:

1. Commit and push de los cambios: `git commit, git push`
2. Ejecutar `./deploy.sh` (si se ejecuta en linux puede ser necesario convertir el fichero a EOL-LF: se puede hacer con el Notepad++ por ejemplo -> Edit/EOL Conversion/Unix )

Los cambios deberían haberse publicado en http://githubusername.github.io/githubprojectname. Ej: http://dome-consulting.github.io/supplier-phoenix-specs