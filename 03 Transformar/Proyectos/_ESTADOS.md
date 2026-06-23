# Estados de Proyecto — C.O.R.T.E.X.

## Ciclo de vida de un proyecto

```
[Backlog] -> [Activo] -> [Review] -> [Completado] -> [Archivado]
                |                          |
                v                          v
           [En Pausa]                [Cancelado]
```

---

## Definiciones

### backlog
Idea validada que merece hacerse pero aun no tiene tiempo asignado. Se revisa semanalmente para priorizar.

- **Tags:** `#proyecto #backlog`
- **Accion:** Esperando priorizacion
- **Tiempo maximo en backlog:** Sin limite, pero se revisa cada semana

### activo
En ejecucion actual. Tiene al menos una tarea en progreso y un proximo paso definido.

- **Tags:** `#proyecto #activo`
- **Accion:** Avanzar semanalmente
- **Maximo recomendado:** 3 proyectos activos simultaneos

### en-pausa
Detenido temporalmente. Puede reanudarse cuando cambien las prioridades o se resuelva un bloqueo.

- **Tags:** `#proyecto #en-pausa`
- **Accion:** Documentar motivo de pausa y condicion de reanudacion
- **Tiempo maximo en pausa:** 90 dias (despues pasa a revisar si cancelar)

### review
Pendiente de revision, aceptacion o feedback. El trabajo esta hecho pero no cerrado.

- **Tags:** `#proyecto #review`
- **Accion:** Solicitar revision, testear, validar

### completado
Entregable terminado y aceptado. Cumple los criterios de exito definidos.

- **Tags:** `#proyecto #completado`
- **Accion:** Escribir lecciones aprendidas, archivar documentacion
- **Archivo automatico:** 90 dias sin actividad

### cancelado
Descartado por decision explicita o cambio de prioridad. No se retomara.

- **Tags:** `#proyecto #cancelado`
- **Accion:** Documentar motivo de cancelacion, archivar si aplica

---

## Dashboard de estados

### Activos

```dataview
TABLE
  fecha-fin as "Entrega",
  prioridad as "Prioridad"
FROM "03 Transformar/Proyectos/Activos"
WHERE status = "activo"
SORT prioridad ASC
```

### En pausa

```dataview
TABLE
  fecha-fin as "Entrega",
  prioridad as "Prioridad",
  fecha-inicio as "Inicio"
FROM "03 Transformar/Proyectos/En Pausa"
WHERE status = "en-pausa"
```

### Backlog

```dataview
TABLE
  prioridad as "Prioridad"
FROM "03 Transformar/Proyectos"
WHERE status = "backlog"
SORT prioridad ASC
```

### Completados recientes

```dataview
TABLE
  fecha-fin as "Completado",
  entregable as "Entregable"
FROM "03 Transformar/Proyectos/Completados"
WHERE status = "completado"
SORT fecha-fin DESC
LIMIT 10
```

---

## Reglas de transicion

| Transicion | Requisito |
|---|---|
| backlog -> activo | Tener tiempo asignado en la semana |
| activo -> en-pausa | Documentar motivo y condicion de reanudacion |
| activo -> review | Toda tarea completada, pendiente de validacion |
| review -> completado | Criterios de exito cumplidos |
| activo -> cancelado | Decision explicita documentada |
| completado -> archivado | 90 dias sin actividad (automatico) |
| en-pausa -> cancelado | 90+ dias en pausa sin senal de reanudacion |
