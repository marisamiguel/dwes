---
title: "Cómo añadir contenido"
date: 2017-01-05
weight: 12
description: 
  
---

{{% pageinfo %}}
**Objetivo**: Estructurar contenido para mejorar la visualización del sitio.

**Documentación:**
* https://gohugo.io/content-management/organization/
* 
{{% /pageinfo %}}


## ¿Qué estructura tiene el contenido de las páginas?
* Tipos de páginas de contenido. Agrupar las páginas por tipos.
* En Hugo el contenido se organiza como luego se va a ver en la web. Anidamos el contenido en subdirectorios (**secciones**): `content/<directorios>`
* Pensar en **front-matter** - **archetypes**
* Plantillas específicas para cada modelo


## Secciones

Se pueden anidar todas las secciones que sean necesarias.

```
content
└── blog        <-- Sección, porque es el primer nivel bajo content/    ├── funny-cats
    │   ├── mypost.md
    │   └── kittens         <-- Sección porque contiene _index.md
    │       └── _index.md
    └── tech                <-- Sección porque contiene _index.md
        └── _index.md

```

Por defecto Hugo asume que las páginas pertenecen al **Content Type** de la sección inicial, es decir que `posts/post-1.md` es de tipo `posts`. Si existe un **archetype** para la  sección **posts**, hugo generará un **frontmatter** específico. Ver [archetypes](https://gohugo.io/content-management/archetypes/)


## Páginas `_index.md`

* Añaden **front-matter** y contenido a las **list templates**
* La función `.Site.GetPage` da acceso a contenido y metadatos.


```
          url
        ⊢  ^ ⊣
        path    slug
        ⊢--^-⊣⊢---^---⊣
           filepath
        ⊢------^------⊣
content/posts/_index.md
```

## Páginas normales en secciones

* Se muestran conlas **single page templates**

## Explicación de las rutas

* filename
* slug
* section
* type
* url


Se pueden modificar en el **frontmatter**: `slug, type y url`

## Front Matter

* Lo que precede al contenido
* Sintaxis especial
* Hay unas variables predefinidas pero el usuario puede crear nuevas.
* Se genera según el **archetype** de la sección. Por defecto *_default.md*
* Se pueden pasar valores por defecto a las páginas que descienden de una sección.

Por ejemplo si ponemos en `content/blog/_index.md`
```toml 
title = 'Blog'
[cascade]
  banner = 'images/typewriter.jpg'
```
Esta página y todas las que descienden de la sección `blog` devuelven `images/typewriter.jpg` en `.Params.banner` a no ser que tengan su propio banner o un ancestro más cercano lo modifique.


### Documentación relacionada:
* https://gohugo.io/content-management/front-matter/
* https://gohugo.io/variables/page/

## Taxonomías
Una taxonomía es una categorización que nos permite clasificar contenido.

Por ejemplo, en una web de Películas podríamos tener actores, directores, estudios, géneros, años, premios ...