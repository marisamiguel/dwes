---
title: "Plantillas"
date: 2017-01-05
weight: 5
description: 

---

{{% pageinfo %}}
Algunas notas sobre el trabajo con las plantillas:
* Sintaxis básica de las plantillas en Hugo
* Organización de las plantillas. Directorio `layout`
* Modificación de una plantilla
* Creación de plantillas


**Documentación:**  https://gohugo.io/templates/
{{% /pageinfo %}}

## Sintaxis básica

Acceso a variables predefinidas:
```go-html-template
{{ .Title }}

{{ .Params.bar }}

{{ if or (isset .Params "alt") (isset .Params "caption") }} Caption {{ end }}

<title>{{ .Title }}</title>
``` 

## Partial 

Incluye un fragmento en una plantilla para no tener que repetirlo:

```go-html-template
{{ partial "<PATH>/<PARTIAL>.<EXTENSION>" . }}.

# Por ejemplo: layouts/partials/header.html partial

{{ partial "header.html" . }}

```

{{% alert title="Importante" color="danger" %}}
Los partials nos ayudan a reutilizar el código y a no repetir fragmentos.
{{% /alert %}}

## Plantillas base y bloques
https://gohugo.io/templates/base/

`layouts/_default/baseof.html`
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>{{ block "title" . }}
      <!-- Blocks may include default content. -->
      {{ .Site.Title }}
    {{ end }}</title>
  </head>
  <body>
    <!-- Code that all your templates share, like a header -->
    {{ block "main" . }}
      <!-- The part of the page that begins to differ between templates -->
    {{ end }}
    {{ block "footer" . }}
    <!-- More shared code, perhaps a footer but that can be overridden if need be in  -->
    {{ end }}
  </body>
</html>
```

`layouts/_default/single.html`
```go-html-template
{{ define "title" }}
  <!-- Sobreescribe el valor de  baseof.html -->
  {{ .Title }} &ndash; {{ .Site.Title }}
{{ end }}
{{ define "main" }}
  <h1>{{ .Title }}</h1>
  {{ .Content }}
{{ end }}
```

## Funciones

https://gohugo.io/templates/introduction/

## Parámetros de las páginas
https://gohugo.io/templates/introduction/#use-content-page-parameters

Podemos usar datos escritos en el **front-matter** de la página desde la plantilla:

```go-html-template
{{ if not .Params.notoc }}
<aside>
  <header>
    <a href="#{{.Title | urlize}}">
    <h3>{{.Title}}</h3>
    </a>
  </header>
  {{.TableOfContents}}
</aside>
<a href="#" id="toc-toggle"></a>
{{ end }}
```


## Uso de la configuración del sitio

https://gohugo.io/templates/introduction/#use-site-configuration-parameters

Y también datos del archivo de configuración general: 

```go-html-template
{{ if .Site.Params.copyrighthtml }}
    <footer>
        <div class="text-center">{{.Site.Params.CopyrightHTML | safeHTML}}</div>
    </footer>
{{ end }}
```

