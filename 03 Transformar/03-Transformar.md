# Transformar -- Ejecucion y Gestion de Proyectos

## Proposito

Convertir el conocimiento en accion tangible. Este pilar cubre proyectos personales, plan de estudio y gestion de startup.

---

## Reglas

- Todo proyecto tiene fecha de entrega o no es un proyecto
- Estados posibles: activo, en pausa, completado, cancelado
- Sin progreso en 30 dias = pasa a "en pausa" automaticamente

---

## Proyectos

### Activos

```dataview
TABLE
  fecha-fin as "Entrega",
  prioridad as "Prioridad",
  entregable as "Entregable"
FROM "03 Transformar/Proyectos/Activos"
SORT prioridad ASC, fecha-fin ASC
```

### En pausa

```dataview
TABLE
  fecha-fin as "Entrega",
  prioridad as "Prioridad"
FROM "03 Transformar/Proyectos/En Pausa"
SORT prioridad ASC
```

---

## Estudio

### Cursos en progreso

```dataview
TABLE
  plataforma as "Plataforma",
  progreso as "Progreso %",
  horas-completadas as "Horas"
FROM "03 Transformar/Estudio/Cursos"
WHERE estado = "en-progreso"
SORT prioridad ASC
```

### Flashcards pendientes

```dataview
TASK
FROM "03 Transformar/Estudio/Flashcards"
WHERE !completed
SORT due ASC
```

---

## Startup

### OKRs activos

```dataview
TABLE
  objetivo as "Objetivo",
  progreso as "Progreso %",
  trimestre as "Trimestre"
FROM "03 Transformar/Startup/OKRs"
WHERE status = "activo"
SORT trimestre DESC
```

### Tareas del dia

```dataview
TASK
FROM "03 Transformar"
WHERE !completed
SORT created ASC
LIMIT 15
```
