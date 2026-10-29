# Mercado de MADRE · módulos de la comunidad

Aquí llegan los módulos que cualquier persona hace con el SDK de MADRE para publicarlos en el
Mercado (madre.run/mercado). Ya publicado, aparece en el Mercado de todas las MADRE con la etiqueta
«Comunidad» y tu nombre, y se actualiza solo cuando publicas una versión nueva, sin npm.

**Es curado.** El autor de MADRE lee cada módulo y cada versión nueva antes de firmarla. Un módulo
corre dentro de MADRE con los permisos de quien la abre, y los del Mercado se actualizan solos; por
eso nada se publica sin que una persona lo lea.

## Cómo mandar el tuyo

1. **Hazlo y pruébalo** en tu MADRE: con «Crea tu módulo» o a mano (`docs/SDK.md` en el repo de
   MADRE).
2. **Mándalo.** En la ficha de tu módulo, «Enviar al Mercado» lo revisa, deja los dos archivos en una
   carpeta y abre la página de GitHub para subirlos a `modulos/<id>/`: arrastras los dos y pulsas
   *Propose changes*; GitHub hace el fork y el pull request por ti, sin terminal. A mano:
   - haz un fork de este repo;
   - agrega `modulos/<id>/<id>.module.mjs` y `modulos/<id>/entrada.json`;
   - revisa con `npx @jossuealcala/madre check-module --file modulos/<id>/<id>.module.mjs --entry modulos/<id>/entrada.json`;
   - abre el pull request.
3. **La revisión automática** carga tu módulo, revisa la entrada y deja en el resumen del job lo que
   declara y lo que usa su código.
4. **La revisión humana:** se acepta o se te piden cambios en el mismo pull request.
5. **Se firma y se publica** en madre.run. Tú nunca necesitas una llave.

Para una versión nueva, abre otro pull request con `version` mayor y `changes`.

## `entrada.json`

```json
{
  "id": "mi-modulo",
  "version": "1.0.0",
  "minMadre": "1.0.6",
  "shelf": "create",
  "price": 0,
  "name": { "es": "Mi módulo", "en": "My module" },
  "line": { "es": "Qué hace, en una línea", "en": "What it does, in a line" },
  "summary": { "es": "Qué hace y cuándo usarlo.", "en": "What it does and when to use it." },
  "changes": { "es": "Qué cambió en esta versión", "en": "What changed in this version" },
  "author": { "name": "Tu nombre", "github": "tu-usuario" },
  "spdx": "MIT",
  "hue": ["#60a5fa", "#1d4ed8"],
  "icon": "<path d=\"…\"/>"
}
```

- `id` y `version` deben ser los mismos que dice el módulo.
- `shelf`: `no-terminal`, `create`, `local-ai` o `connect`.
- `price`: por ahora solo gratuitos (0).
- `spdx`: la licencia de tu código. Hoy: AGPL-3.0, GPL-3.0, MIT, Apache-2.0, BSD-2/3-Clause, ISC o
  MPL-2.0.
- `icon` (opcional): las figuras de un dibujo de 20×20 con `currentColor`, sin scripts ni enlaces.
  Si no lo pones, el Mercado muestra una pieza de rompecabezas.

Al mandar un módulo aceptas `TERMINOS.md`.
