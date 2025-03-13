---
date: "2025-03-13T17:10:00Z"
subtitle: Enunciado del 1er Cuatrimestre 2025
tags:
- trabajos-practicos
- 2025-1C
title: Ajustes en el contrato del enunciado del TP1C 2025
---

Detectamos una inconsistencia en la especificación OpenAPI del enunciado original para la creación de cursos (`POST /courses`). Inicialmente, el contrato requería que el `id` fuera un UUID, cuando en realidad **solo los extras evaluaban su uso**. Para alinearlo con los requisitos base, **se corrigió el contrato para que el identificador sea un número entero en la versión estándar**.

### 📌 **¿Qué cambiamos?**

- **Antes**: Se exigía que el `id` fuera un `string` con formato UUID.
  ```json
  {
    "data": {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "title": "Curso de prueba",
      "description": "Descripción del curso"
    }
  }
  ```
  
- **Ahora**: El `id` vuelve a ser un `integer` en la versión base del enunciado.
  ```json
  {
    "data": {
      "id": 1,
      "title": "Curso de prueba",
      "description": "Descripción del curso"
    }
  }
  ```

### 🔍 **¿Qué significa este cambio?**
- En la versión estándar, el `id` de los cursos será numérico (`integer`).
- **Solo si se implementa el extra de UUID**, el `id` pasará a ser un `string` con formato UUID.
- La especificación OpenAPI fue actualizada para reflejar esto correctamente.

⚠️ **¡IMPORTANTE!**  
Si ya empezaste tu implementación con UUID v4, **no es necesario cambiar nada**, ya que **era parte del extra** y sigue siendo una solución válida. 🚀

Gracias por el feedback y las preguntas, seguimos mejorando el enunciado para mayor claridad. 🚀