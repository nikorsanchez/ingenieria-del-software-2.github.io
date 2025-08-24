---

date: "2025-08-24T13:00:00Z"
subtitle: "Enunciado del 2do Cuatrimestre 2025"
title: "Ajustes en el contrato de actualización (PUT vs PATCH) del TP2C 2025"
tags:
- trabajos-practicos
- 2025-2C
---

Detectamos una inconsistencia en la especificación OpenAPI del enunciado original para actualizar canciones (`PUT /songs/{id}`). El contrato permitía **cuerpos parciales** (ninguna propiedad `required`), lo que **contradice la semántica estándar de HTTP**: **PUT** reemplaza la representación **completa** del recurso y es **idempotente**; no es _safe_. ([RFC Editor][1], [IETF Datatracker][2])

### 📌 **¿Qué cambiamos?**

- **Antes**: `UpdateSongRequest` **no** exigía campos obligatorios, habilitando un “PUT parcial”.

  ```yaml
  components:
    schemas:
      UpdateSongRequest:
        type: object
        properties:
          title: { type: string }
          artist: { type: string }
  ```

- **Ahora**: `PUT /songs/{id}` vuelve a ser **reemplazo completo** e **idempotente**. Por eso, `UpdateSongRequest` **exige ambos campos**.

  ```yaml
  components:
    schemas:
      UpdateSongRequest:
        type: object
        required:
            - title
            - artist
        properties:
          title: { type: string }
          artist: { type: string }
  ```

_Nota OpenAPI_: `requestBody.required: true` solo marca que **hay** cuerpo; los **campos obligatorios** se definen en el **Schema** mediante `required: [...]`. ([Swagger][3], [OpenAPI Initiative Publications][4])

### **Ejemplo de uso (PUT = reemplazo completo)**

```json
{
  "title": "Bohemian Rhapsody",
  "artist": "Queen"
}
```

### 🔍 **Recordatorio rápido de semántica HTTP (safe / idempotent)**

- **GET** → _safe_ e _idempotent_.
- **POST** → no _safe_, no _idempotent_ por defecto.
- **PUT** → no _safe_, **sí idempotent** (reemplaza por completo).
- **PATCH** → no _safe_, **no idempotent** por defecto (puede diseñarse idempotente). ([RFC Editor][1], [MDN Web Docs][5], [IETF Datatracker][6])

_Safe_: métodos cuya semántica es solo lectura y no piden cambios de estado en el servidor.

_No safe_: métodos que sí pueden modificar el estado o producir efectos secundarios.

_Idempotente_: en HTTP, repetir la misma solicitud varias veces deja el recurso/servidor en el mismo estado que si se hiciera una sola vez (aunque el código/respuesta pueda variar).

- _“A request method is considered **‘idempotent’** if the intended effect on the server of multiple identical requests with that method is the same as the effect for a single such request.”_
RFC 9110 §9.2.2 — [https://www.rfc-editor.org/rfc/rfc9110.html#name-idempotent-methods](https://www.rfc-editor.org/rfc/rfc9110.html#name-idempotent-methods) ([RFC Editor][1])

- _“It knows that repeating the request will have the same intended effect, **even if the original request succeeded, though the response might differ**.”
RFC 9110 §9.2.2 — [https://www.rfc-editor.org/rfc/rfc9110.html#name-idempotent-methods](https://www.rfc-editor.org/rfc/rfc9110.html#name-idempotent-methods) ([RFC Editor][1])_


### **¿Qué significa este cambio para vos?**

- Si tu implementación hacía que **PUT** aceptara parciales, ajustala para que **requiera** `title` y `artist` (reemplazo completo).
- Si ya tenías **PUT** como reemplazo total, no necesitás cambios.
- El formato de respuestas **no cambia**.

---

### Fuentes

- RFC 9110 — HTTP Semantics (definiciones de _safe_ e _idempotent_; PUT/DELETE idempotentes):
  [https://www.rfc-editor.org/rfc/rfc9110.html](https://www.rfc-editor.org/rfc/rfc9110.html) ([RFC Editor][1])
- MDN — Métodos HTTP (tabla de safe/idempotent):
  [https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods) ([MDN Web Docs][5])
- RFC 5789 — Método PATCH (no es seguro ni idempotente por defecto):
  [https://datatracker.ietf.org/doc/rfc5789/](https://datatracker.ietf.org/doc/rfc5789/) ([IETF Datatracker][6])
- OpenAPI 3.0 — `requestBody.required` (cuerpo requerido):
  [https://swagger.io/docs/specification/v3_0/describing-request-body/describing-request-body/](https://swagger.io/docs/specification/v3_0/describing-request-body/describing-request-body/) ([Swagger][3])
- OpenAPI 3.0.3 — Especificación oficial:
  [https://spec.openapis.org/oas/v3.0.3.html](https://spec.openapis.org/oas/v3.0.3.html) ([OpenAPI Initiative Publications][4])

---

[1]: https://www.rfc-editor.org/rfc/rfc9110.html "RFC 9110: HTTP Semantics"
[2]: https://datatracker.ietf.org/doc/html/rfc9110 "RFC 9110 - HTTP Semantics"
[3]: https://swagger.io/docs/specification/v3_0/describing-request-body/describing-request-body/ "Describing Request Body"
[4]: https://spec.openapis.org/oas/v3.0.3.html "OpenAPI Specification v3.0.3"
[5]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods "HTTP request methods - MDN - Mozilla"
[6]: https://datatracker.ietf.org/doc/rfc5789/ "RFC 5789 - PATCH Method for HTTP"
