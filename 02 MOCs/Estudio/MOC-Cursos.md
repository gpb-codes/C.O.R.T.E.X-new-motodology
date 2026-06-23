# MOC -- Cursos y Rutas de Estudio

## Proposito

Mapa de aprendizaje: cursos activos, completados y rutas de estudio planificadas.

---

## Ruta de aprendizaje actual

```
[Objetivo de aprendizaje principal]
├── Curso 1 (en progreso)
├── Curso 2 (siguiente)
└── Curso 3 (futuro)
```

## Cursos en progreso

```dataview
TABLE
  plataforma as "Plataforma",
  progreso as "Progreso (%)",
  fecha-fin as "Fecha meta",
  horas-completadas as "Horas"
FROM "03 Transformar/Estudio/Cursos"
WHERE estado = "en-progreso"
SORT prioridad ASC, fecha-fin ASC
```

## Cursos completados

```dataview
TABLE
  plataforma as "Plataforma",
  fecha-fin as "Completado",
  certificacion as "Cert"
FROM "03 Transformar/Estudio/Cursos"
WHERE estado = "completado"
SORT fecha-fin DESC
```

## Proximos cursos

| Curso | Prioridad | Estimado | Por que |
|---|---|---|---|
|  | Alta/Media/Baja |  |  |

## Estadisticas de estudio

- **Horas totales invertidas:**
- **Cursos completados:**
- **Certificaciones obtenidas:**
