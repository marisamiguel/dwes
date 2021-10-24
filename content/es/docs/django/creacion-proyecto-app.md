---
title: "Creación de un proyecto y una app"
date: 2021-10-21T10:36:54+02:00
weight: 6
description: >
  Creación de un proyecto y una app
tags: [django]
---

{{% pageinfo %}}
Documentación
* https://docs.djangoproject.com/es/3.2/intro/tutorial01/
{{% /pageinfo %}}

## Creación de proyecto
```bash
$ django-admin startproject bookr
```

```
bookr/
    manage.py
    bookr/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
```

```bash
$ python3 manage.py runserver
```

Parar con `Ctrl+C`

## Creación aplicación
```bash
$ python3 manage.py startapp reviews
```

## Modelo Vista Template
Diseño común: patrón Modelo Vista Controlador (**MVC**)
Django usa: **MVT**: Permite que las templates puedan desarrollarse en cualquier lenguaje:
* Modelos y Vistas se escriben en **Python**
* Templates se escriben en **html**