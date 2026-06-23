# Taxonomía de Tags — C.O.R.T.E.X.

Toda nota debe tener al menos un tag de **dominio** y uno de **tipo**.

---

## Por dominio

| Tag | Uso |
|---|---|
| `#conocimiento` | Conocimiento técnico general |
| `#estudio` | Cursos, rutas, aprendizaje formal |
| `#startup` | Negocio, producto, clientes, OKRs |
| `#axis` | Memoria del asistente A.X.I.S. |

## Subtags de dominio

```
#conocimiento/arquitectura
#conocimiento/ciberseguridad
#conocimiento/programacion
#conocimiento/herramientas
#conocimiento/libros
#conocimiento/principios

#estudio/curso
#estudio/ruta
#estudio/repaso
#estudio/flashcard

#startup/producto
#startup/clientes
#startup/metricas
#startup/okr
#startup/funnel
#startup/roadmap

#axis/decision
#axis/contexto
#axis/aprendizaje
#axis/sesion
```

## Por tipo

| Tag | Uso |
|---|---|
| `#proyecto` | Proyecto con inicio, fin, entregable |
| `#area` | Área de responsabilidad continua |
| `#tarea` | Tarea atómica accionable |
| `#decision` | Decisión registrada |
| `#diario` | Nota diaria |
| `#revision` | Revisión semanal o mensual |
| `#extraccion` | Extracción de sesión A.X.I.S. |
| `#nota-rapida` | Captura sin procesar |
| `#moc` | Mapa de Contenido |
| `#okr` | OKR de startup |

## Por estado

| Tag | Uso |
|---|---|
| `#activo` | En curso actualmente |
| `#en-pausa` | Temporalmente detenido |
| `#completado` | Finalizado |
| `#cancelado` | Descartado |
| `#pendiente` | Esperando acción externa |
| `#archivado` | Movido a archivo histórico |

## Por prioridad

| Tag | Uso |
|---|---|
| `#urgente` | Requiere atención inmediata |
| `#alta` | Alta prioridad |
| `#media` | Prioridad normal |
| `#baja` | Baja prioridad / cuando se pueda |

## Tags compuestos (combinaciones comunes)

| Combinación | Para qué sirve |
|---|---|
| `#proyecto #activo #startup` | Proyecto activo de startup |
| `#area #en-pausa #salud` | Área de salud en mantenimiento mínimo |
| `#decision #tomada #startup` | Decisión tomada para startup |
| `#nota-rapida #pendiente #conocimiento` | Captura pendiente de procesar |
| `#revision #completado` | Revisión del período ya hecha |

---

## Reglas

1. Toda nota lleva **mínimo un tag de dominio + un tag de tipo**
2. Los tags de estado son opcionales pero recomendados para filtros Dataview
3. No inventar tags nuevos sin registrarlos primero aquí
4. Preferir subtags (`#dominio/subtipo`) sobre tags planos
5. Tags van siempre en el frontmatter YAML (`tags: [...]`)
