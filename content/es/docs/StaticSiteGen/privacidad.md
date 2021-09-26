---
title: "Configuración GDPR"
date: 2017-01-05
weight: 100
description: 

---
{{% pageinfo %}}
Configurar Hugo para General Data Protection Regulation (GDPR)

https://gohugo.io/about/hugo-and-gdpr/
{{% /pageinfo %}}

Por defecto:

```yaml
privacy:
  disqus:
    disable: false
  googleAnalytics:
    anonymizeIP: false
    disable: false
    respectDoNotTrack: false
    useSessionStorage: false
  instagram:
    disable: false
    simple: false
  twitter:
    disable: false
    enableDNT: false
    simple: false
  vimeo:
    disable: false
    enableDNT: false
    simple: false
  youtube:
    disable: false
    privacyEnhanced: false
```

Para deshabilitar servicios:
```yaml
privacy:
  disqus:
    disable: true
  googleAnalytics:
    disable: true
  instagram:
    disable: true
  twitter:
    disable: true
  vimeo:
    disable: true
  youtube:
    disable: true
    ```