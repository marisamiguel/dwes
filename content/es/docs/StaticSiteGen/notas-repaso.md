---
title: "Algunas notas de repaso"
date: 2021-09-27
weight: 99
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

- https://hugo-mini-course.netlify.app/sections/templating/singlepage/

## Sintaxis de templates

**Variables**

```go-html-template
<title>{{ .Title }}</title>
```

**Contenido md de la página**
`{{.Content}}`

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

## Tema sencillo pare test

https://github.com/zwbetz-gh/vanilla-bootstrap-hugo-theme

## Trabajando con ficheros de datos:

`data/socialmedia.json`

```json
{ ​ "accounts"​ :
  [
    {
      "name"​ : ​ "Twitter"​ ,
      "url"​ : ​ "https://twitter.com/bphogan"
    },
    {
      "name"​ : ​ "LinkedIn"​ ,
      "url"​ : ​ "https://linkedin.com/in/bphogan"
    }
  ]
}
```


```go-html-template
<h3>Social Media</h3>
<ul>
{{ range .Site.Data.socialmedia.accounts }}
<li><a href=​ "{{ .url }}"​ >{{ .name }}</a></li>
{{ end }}
</ul>
```

**Ejemplo csv remoto**
```go-html-template
<table>
    <thead>
      <tr>
      <th>Name</th>
      <th>Position</th>
      <th>Salary</th>
      </tr>
    </thead>
    <tbody>
    {{ $url := "https://example.com/finance/employee-salaries.csv" }}
    {{ $sep := "," }}
    {{ range $i, $r := getCSV $sep $url }}
      <tr>
        <td>{{ index $r 0 }}</td>
        <td>{{ index $r 1 }}</td>
        <td>{{ index $r 2 }}</td>
      </tr>
    {{ end }}
    </tbody>
  </table>
  ```