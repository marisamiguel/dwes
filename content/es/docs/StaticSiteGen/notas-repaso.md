---
title: "Estructura proyecto"
date: 2021-09-27
weight: 40
description: 

---

## Estructura del sitio

```
misitio
├── archetypes
|   └── default.md
├── content
├── data
├── layouts
|   ├── _default
|   |   └── baseof.html
|   └── index.html
├── static
├── themes
└── config.toml
```

## Un tutorial 
* https://hugo-mini-course.netlify.app/sections/templating/singlepage/


## Sintaxis de templates

**Variables**
```go-html-template
<title>{{ .Title }}</title>
```
**Contenido md de la página**
 ```{{.Content}}```

**Bucles**
```go-html-template
{{ range .Pages.ByWeight }}
        <li>
            <a href="{{.Permalink}}">{{.Date.Format "2006-01-02"}} | {{.Title}}</a>
        </li>
{{ end }}

```

## Proceso de imágenes

https://gohugo.io/content-management/image-processing/

```go
{{ $asset := resources.Get "/duck.png" }}
{{ $img := $asset.Fit "600x400" }}
<figure class="image is-3by2">
  <img alt="Yellow Duck" src="{{ $img.RelPermalink }}" />
</figure>
```