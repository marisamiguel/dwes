---
title: "Vistas genéricas: listados y detalle"
date: 2021-10-21T10:36:54+02:00
weight: 15
description: >
  Vistas genéricas son una forma de crear vistas que se pueden reutilizar en
  diferentes proyectos.
tags: [Vistas genéricas]
---

{{% pageinfo %}}
Documentación: 
* https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Generic_views
* https://docs.djangoproject.com/en/3.2/intro/
{{% /pageinfo %}}


## URL mapping

```python
urlpatterns = [
    path('', views.index, name='index'),
    path('books/', views.BookListView.as_view(), name='books'),
]
```

# Redirección incial
```python
from django.views.generic import RedirectView
from django.urls import include, path
from django.contrib import admin
from django.conf.urls.static import static


urlpatterns = [
    path('admin/', admin.site.urls),
    path('catalog/', include('catalog.urls')),
    path('/', RedirectView.as_view(url='/catalog/', permanent=True)),
] + static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)

# Este static es solo para DEBUG = True
```
