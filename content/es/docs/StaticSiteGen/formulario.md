---
title: "Inserción de formularios dinámicos"
date: 2017-01-05
weight: 60
description: 
  
---

{{% pageinfo %}}
**Objetivo**: Introducir un formulario con envío de correo.

* Ejemplo con formspree

{{% /pageinfo %}}


## Formularios de contacto

Hay muchos servicios. Formik, StaticKit, FormKeep, Netlify Forms, Formspree, FormPlug, Google Forms ...

* https://formspree.io
* Ejemplos: https://formspree.io/library


## Pasos:

1. Dar de alta un formulario en formspree
2. Ver `html` en **integration**

```html
<!-- modify this form HTML and place wherever you want your form -->
<form
  action="https://formspree.io/f/{form_id}"
  method="POST"
>
  <label>
    Your email:
    <input type="email" name="_replyto">
  </label>
  <label>
    Your message:
    <textarea name="message"></textarea>
  </label>
  <!-- your other form fields go here -->
  <button type="submit">Send</button>
</form>
```


```html
<form id="fs-frm" name="simple-contact-form" accept-charset="utf-8" action="https://formspree.io/f/{form_id}" method="post">
  <fieldset id="fs-frm-inputs">
    <label for="full-name">Full Name</label>
    <input type="text" name="name" id="full-name" placeholder="Nombre completo" required="">
    <label for="email-address">Email Address</label>
    <input type="email" name="_replyto" id="email-address" placeholder="email@domain.tld" required="">
    <label for="message">Message</label>
    <textarea rows="5" name="message" id="message" placeholder="Introduzca texto ..." required=""></textarea>
    <input type="hidden" name="_subject" id="email-subject" value="Contact Form Submission">
  </fieldset>
  <input type="submit" value="Submit">
</form>
```
3. Modificar etiquetas y dar formato con `css`





## Comentarios 

Inserción de comentarios dinámicos en las páginas.

https://gohugo.io/content-management/comments/

