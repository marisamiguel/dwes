---
title: "Trabajo con datos"
date: 2021-10-02
weight: 30
description: 
  
---


{{% pageinfo %}}
Proceso de datos: en archivos locales, en archivos y directorios o remotos.

{{% /pageinfo %}}

Ejemplo en templates:

```go-html-template

{{ define "main" }}

<h1>{{ .Title }}</h1>
<p>{{ .Params.mensaje | markdownify}}</p>

{{ .Content }}

<div id="mic" class="carousel slide " data-ride="carousel">
    <div class="carousel-inner">
        {{ range $elem_index, $elem_val := .Site.Data.clients }}
        <div class="carousel-item {{ if eq $elem_index "1" }} active {{ end }}">
            <img class="d-block w-100" src="{{ .image  | relURL }}"  alt="{{ .name }}">
        </div>
        {{ end }}
    </div>
</div>

{{ $dataC := getCSV "," .Params.urldatos }}

 <table class="table table-striped" >
    {{ range $i, $r := $dataC }}
        {{ if eq $i 0 }}
            <thead>
            <tr>
            <th>{{ index $r 0 }}</th>
            <th>{{ index $r 1 }}</th>
            <th>{{ index $r 2 }}</th>
            </tr>
            </thead>
            <tbody>
        {{ else }}
            <tr>
                <td>{{ index $r 0 }}</td>
                <td>{{ index $r 1 }}</td>
                <td>{{ index $r 2 }}</td>
            </tr>
        {{ end }}
    {{ end }}
    </tbody>
  </table>



   <ul>
    {{ range  .Site.Data.tv }}
        <li>  {{ .name }}</li>
        {{ range .channels }}
            <img src="{{.logo}}" alt="{{ .name }}">
        {{ end }}
    {{ end }}
    </ul>


{{ end }}
```
