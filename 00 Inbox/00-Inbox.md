# Capturar -- Inbox

## Proposito

Punto de entrada unico para toda la informacion. Sin filtrar, sin clasificar, sin pensar. Capturar en menos de 5 segundos.

---

## Reglas

- Todo entra al Inbox sin clasificar
- No pensar en la categoria en el momento de capturar
- Procesar el inbox diariamente (obligatorio)
- Las conversaciones con A.X.I.S. se capturan automaticamente

---

## Canales de captura

| Canal | Herramienta | Metodo | Tiempo estimado |
|---|---|---|---|
| **Obsidian movil** | Obsidian (Android/iOS) | Widget nota rapida sincronizado | 5 seg |
| **Notas de voz** | Obsidian movil o voz a texto | Grabar y transcribir al llegar a casa | 30 seg |
| **Share extension** | Navegador / Apps | Compartir → Obsidian → Inbox | 3 seg |
| **QuickAdd** | Obsidian plugin (cmd+Q) | Captura rapida con template Nota rapida | 5 seg |
| **Email a vault** | If This Then That / Zapier | Email → archivo .md en Inbox | Automatico |
| **Web clipper** | Obsidian Web Clipper (extension) | Clip directo a `00 Inbox/` | 5 seg |
| **Movil fotos** | Google Lens + OCR | Foto de texto → copiar a Inbox | 10 seg |
| **A.X.I.S. session** | Conversacion automatica | Extraccion structurada al finalizar | Automatico |

> **Regla de oro:** si toma mas de 10 segundos capturarlo, hacerlo igual y procesar despues. No analizar en el momento.

---

## Workflow de procesamiento GTD (Inbox -> Organizar)

### Paso 1: Revisar inbox (diario, 5-10 min)

```dataview
TASK
FROM "00 Inbox"
WHERE !completed AND !contains(tags, "procesado")
SORT created ASC
```

### Paso 2: Clasificar cada item

Para cada nota rapida o captura, aplicar esta secuencia:

| Pregunta | Accion |
|---|---|
| ¿Se puede eliminar? (sin valor futuro) | Eliminar sin culpa |
| ¿Es informacion de referencia? | Mover a `02 MOCs/[dominio]/` con enlace |
| ¿Requiere una accion de menos de 2 min? | Hacerla ahora |
| ¿Requiere una accion de mas de 2 min? | Crear tarea en proyecto o diario |
| ¿Es un proyecto (multiples pasos)? | Crear [[Proyecto]] en `03 Transformar/Proyectos/Activos/` |
| ¿Es un tema de estudio? | Crear [[Curso]] en `03 Transformar/Estudio/Cursos/` |
| ¿Es una decision o aprendizaje? | Mover a `05 eXpandir/Decisiones/` o Extracciones |

### Paso 3: Ejecutar

- [ ] Revisar notas rapidas sin procesar
- [ ] Clasificar por dominio (`#conocimiento` `#estudio` `#startup` `#axis`)
- [ ] Mover a Organizar, Transformar o eXpandir segun corresponda
- [ ] Extraer acciones y crear tareas
- [ ] Anadir tag `#procesado` al item original

### Paso 4: Cierre

- [ ] Inbox vacio al finalizar
- [ ] Crear tareas pendientes en sus proyectos correspondientes

---

## Stats

- **Items en inbox:**
- **Ultimo procesamiento:**
- **Items procesados esta semana:**
