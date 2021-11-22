---
title: "Proyecto Django - Primer trimestre"
date: 2021-10-21T10:36:54+02:00
weight: 36
description: >
  Proyecto de Django primera evaluación
tags: [proyectos]
---

{{% pageinfo %}}
**Descripción**: proyecto de una web personal con altas, bajas, modificaciones y listados de datos.
{{% /pageinfo %}}

## REQUISITOS

1. El proyecto estará gestionado en un repositorio de código git con un remoto en github. Accesible por el profesor (1 punto) 
    * Habrá una gestión correcta de cambios con comentarios claros
    * Contendrá un **README.md** con la descripción del proyecto y un método de instalación
    * Un **.gitignore** con las extensiones que no queremos que se suban al repositorio

1. Gestión del proyecto (1 punto)
    * Creación de un entorno virtual con **requirements.txt** para indicar las dependencias
    * El directorio **env** no se incluirá en el repositorio.
    * Todas las funciones y clases estarán documentadas. 

1. **Models** (2 puntos)
     * Gestión correcta de datos (tipos de datos y relaciones)   
     * Al menos 3 modelos con relaciones entre ellos
     * Todos tendrán método **__str__**

1. **urls** (1 punto)
      * Urls generales y la aplicación para listados, altas, bajas y modificaciones

1. Hará uso del **Admin** al menos para listados con filtros y búsquedas. (1 punto)

1. **views** (2 punto)
    * Uso de vistas tipo función y de tipo clase
    * Gestión correcta y segura de formularios
    * Las funcionalidades que modifican los datos tienen que estar limitadas a usuarios autenticados

1. **templates** (2 punto)
    * Habrá herencia de una plantilla base
    * Habrá una barra de menús o sidebar en una plantilla aparte
    * bloques de contenido, extracss y extrajs 
    * Gestión correcta de formularios
    * Bloques **if** y **for** para mostrar correctamente los datoss
  

2. Hará una presentación de la aplicación ante los compañeros el día del examen del módulo. (1 punto)

## FECHA LIMIETE DE ENTREGA
8 de diciembre a las 20 horas. 



