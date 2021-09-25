---
title: "Segunda tarea"
date: 2017-01-05
weight: 4
description: 
  
---

{{% pageinfo %}}
**Objetivo:** Construcción de un primer sitio sencillo con un tema simple.

**Recursos externos:** Tema de hugo https://github.com/EmielH/tale-hugo
{{% /pageinfo %}}

## Creación del sitio

``` bash
$ hugo new site primeros-pasos

Congratulations! Your new Hugo site is created in /home/lm/proyectos/cpilosenlaces/primeros-pasos.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.

```

Estructura creada:

``` bash
archetypes
config.toml
content
data
layouts
static
themes
```

## Instalar tema

> https://github.com/EmielH/tale-hugo

* Descargar a la carpeta themes. Renombrar la carpeta del tema a `tale`

* Modificar `config.toml`

  ```
   theme = "tale"
  ```

## Añadir contenido
(3 páginas)

``` hugo new contacto.md ```

## Añadir 3 posts
``` $ hugo new posts/esto-es-hugo.md ```

Editar markdown. Una imagen por post por lo menos.

### Añadir un menú

```toml
[menu]
  [[menu.main]]
	identifier = "contacto"
	name = "Contacto"
	title = "Contacto"
	url = "/contacto/"
	weight = 2
  [[menu.main]]
	identifier = "posts"
	name = "Posts"
	title = "Posts"
	url = "/posts/"
	weight = 3
  ```

## Publicar

  ```
  hugo 
  ```

## gh pages

  `hugo -d docs`

Modificar *config.toml*

  ```
  baseURL = "https://xxxxxxx.github.io/primeros-pasos"
  ```

* Crear un repositorio en GitHub
* Hacer el commit, para confirmar los cambios del sitio web en tu repositorio local
* Asociar el repositorio local con el repositorio remoto que has creado en Github
* Sincronizar el contenido del repositorio local hacia remoto
