---
title: "Archivos estáticos"
date: 2021-10-21T10:36:54+02:00
weight: 34
description: >
  Subida de archivos
tags: [Estáticos]
---

{{% pageinfo %}}
Documentación:
* https://docs.djangoproject.com/en/3.2/howto/static-files/ 
{{% /pageinfo %}}

## Configurar
Incluir **django.contrib.staticfiles** en ** is included in your **INSTALLED_APPS**.

En el archivo **settings.py**, incluir la siguiente línea:

```STATIC_URL = '/static/'```

En las plantillas:

```html
{% load static %}
<img src="{% static 'my_app/example.jpg' %}" alt="My image">
```

Los archivos van en una carptea **static** en las apps

## Servir los archivos estáticos

### Desarrollo
```python
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    # ... the rest of your URLconf goes here ...
] + static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
```

### Despliegue
* https://docs.djangoproject.com/en/3.2/howto/static-files/deployment/
  