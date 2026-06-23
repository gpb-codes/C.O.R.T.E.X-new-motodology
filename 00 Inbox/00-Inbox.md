# Capturar -- Inbox

## Proposito

Punto de entrada unico para toda la informacion. Sin filtrar, sin clasificar, sin pensar. Capturar en menos de 5 segundos.

---

## Reglas

- Todo entra al Inbox sin clasificar
- No pensar en la categoria en el momento de capturar
- Procesar el inbox diaria o semanalmente
- Las conversaciones con A.X.I.S. se capturan automaticamente

---

## Pendientes de procesar

```dataview
TASK
FROM "00 Inbox"
WHERE !completed AND !contains(tags, "procesado")
SORT created ASC
```

---

## Procesar ahora

### Clasificar items pendientes

- [ ] Revisar notas rapidas sin procesar
- [ ] Clasificar por dominio (`#conocimiento` `#estudio` `#startup` `#axis`)
- [ ] Mover a Organizar o Transformar segun corresponda
- [ ] Extraer acciones y crear tareas

### Fuentes de captura

| Fuente | Descripcion | Frecuencia |
|---|---|---|
| Notas rapidas | Ideas, apuntes, capturas del momento | Continuo |
| Correos | Emails con informacion relevante | Diario |
| Links | Articulos, videos, recursos web | Diario |
| Extracciones AXIS | Destilados de sesiones con A.X.I.S. | Cada sesion |
| Movil | Notas de voz, fotos, capturas | Diario |

---

## Stats

- **Items en inbox:**
- **Ultimo procesamiento:**
