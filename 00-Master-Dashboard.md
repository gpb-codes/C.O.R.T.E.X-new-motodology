# C.O.R.T.E.X. -- Master Dashboard

## Informacion general

- **Semana:** `= dateformat(date(today), "yyyy-ww")`
- **Ultima actualizacion:** `= dateformat(date(today), "dd/MM/yyyy")`
- **Proxima revision:** [[_META-CORTEX]] | [[_ONBOARDING]]

---

## Metricas rapidas

```dataview
TABLE WITHOUT ID
  "Proyectos activos" as "Metrica",
  length(rows) as "Valor"
FROM "03 Transformar/Proyectos/Activos"
WHERE status = "activo"
FLATTEN length(rows)
LIMIT 1
```

```dataview
TABLE WITHOUT ID
  "Repasos vencidos" as "Metrica",
  length(rows) as "Valor"
FROM "05 eXpandir/Repaso"
WHERE proximo-repaso <= date(today)
FLATTEN length(rows)
LIMIT 1
```

```dataview
TABLE WITHOUT ID
  "Decisiones pendientes" as "Metrica",
  length(rows) as "Valor"
FROM "05 eXpandir/Decisiones"
WHERE status = "pendiente" OR status = "tomada"
FLATTEN length(rows)
LIMIT 1
```

---

## Charts de progreso (requiere Obsidian Charts plugin)

```chart
type: bar
labels: [Proyectos, Estudio, Startup, Areas]
series:
  - title: Progreso %
    data: [0, 0, 0, 0]
```

```chart
type: line
labels: [Sem1, Sem2, Sem3, Sem4]
series:
  - title: Horas de estudio
    data: [0, 0, 0, 0]
  - title: Tareas completadas
    data: [0, 0, 0, 0]
```

---

## Enfoque de la semana

| Prioridad | Objetivo | Estado |
|---|---|---|
| 1 |  | Pendiente |
| 2 |  | Pendiente |
| 3 |  | Pendiente |

---

## Proyectos activos

```dataview
TABLE
  fecha-fin as "Entrega",
  status as "Estado",
  prioridad as "Prioridad"
FROM "03 Transformar/Proyectos/Activos"
WHERE status = "activo"
SORT prioridad ASC, fecha-fin ASC
```

---

## Estudio en progreso

```dataview
TABLE
  progreso as "Progreso %",
  fecha-fin as "Fecha meta",
  estado as "Estado"
FROM "03 Transformar/Estudio"
WHERE estado = "en-progreso"
SORT fecha-fin ASC
```

---

## Startup -- OKRs activos

```dataview
TABLE
  objetivo as "Objetivo",
  progreso as "Progreso %",
  trimestre as "Trimestre"
FROM "03 Transformar/Startup/OKRs"
WHERE status = "activo"
SORT trimestre DESC
```

---

## Salud de areas

```dataview
TABLE
  metricas as "Metrica principal",
  estado as "Estado",
  ultima-revision as "Ultima revision",
  nivel-deseado as "Nivel deseado"
FROM "04 Evaluar"
WHERE tipo = "area"
SORT ultima-revision ASC
```

---

## Diario -- ultimas entradas

```dataview
TABLE
  humor as "Humor",
  energia as "Energia"
FROM "05 eXpandir/Diario"
SORT file.day DESC
LIMIT 5
```

---

## Extracciones A.X.I.S. recientes

```dataview
TABLE
  fecha as "Fecha",
  dominio as "Dominio"
FROM "05 eXpandir/Extracciones AXIS"
SORT fecha DESC
LIMIT 5
```

---

## Proyectos en pausa

```dataview
TABLE
  prioridad as "Prioridad",
  fecha-inicio as "Inicio"
FROM "03 Transformar/Proyectos/En Pausa"
WHERE status = "en-pausa"
SORT prioridad ASC
```

---

## Repaso vencido

```dataview
TABLE
  fecha-repaso as "Ultimo repaso",
  dificultad as "Dificultad",
  proximo-repaso as "Vencido desde"
FROM "05 eXpandir/Repaso"
WHERE proximo-repaso <= date(today)
SORT proximo-repaso ASC
```

---

## Decisiones activas

```dataview
TABLE
  fecha as "Fecha",
  dominio as "Dominio",
  impacto as "Impacto"
FROM "05 eXpandir/Decisiones"
WHERE status = "tomada" OR status = "en-ejecucion"
SORT fecha DESC
LIMIT 5
```

---

## Acceso rapido a pilares

| Pilar | Carpeta | Enlace |
|---|---|---|
| Capturar | 00 Inbox | [[00 Inbox/00-Inbox]] |
| Organizar | 01 Organizar | [[01 Organizar/01-Organizar]] |
| Relacionar | 02 MOCs | [[02 MOCs/02-MOCs]] |
| Transformar | 03 Transformar | [[03 Transformar/03-Transformar]] |
| Evaluar | 04 Evaluar | [[04 Evaluar/04-Evaluar]] |
| eXpandir | 05 eXpandir | [[05 eXpandir/05-eXpandir]] |
