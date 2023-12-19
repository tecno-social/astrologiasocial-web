---
layout: page
title: Contacto
permalink: /contacto
comments: false
---

<form action="https://formspree.io/{{site.email}}" method="POST">
<p class="mb-4">Envíanos tu correo usando el siguiente formulario o escribiendo a <b><a href="mailto:hola@astroologia.social">hola@astroologia.social</a></b>. ¡Responderemos lo mas pronto posible!</p>
<div class="form-group row">
<div class="col-md-6">
<input class="form-control" type="text" name="name" placeholder="Nombre*" required>
</div>
<div class="col-md-6">
<input class="form-control" type="email" name="_replyto" placeholder="Correo Electrónico*" required>
</div>
</div>
<textarea rows="8" class="form-control mb-3" name="message" placeholder="Mensaje*" required></textarea>
<input class="btn btn-dark" type="submit" value="Enviar">
</form>
