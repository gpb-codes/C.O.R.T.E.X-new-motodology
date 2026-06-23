# C.O.R.T.E.X. -- Master Dashboard

## Informacion general

- **Semana:** `= dateformat(date(today), "yyyy-ww")`
- **Ultima actualizacion:** `= dateformat(date(today), "dd/MM/yyyy")`

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

## Acceso rapido a pilares

| Pilar | Carpeta | Enlace |
|---|---|---|
| Capturar | 00 Inbox | [[00 Inbox/00-Inbox]] |
| Organizar | 01 Organizar | [[01 Organizar/01-Organizar]] |
| Relacionar | 02 MOCs | [[02 MOCs/02-MOCs]] |
| Transformar | 03 Transformar | [[03 Transformar/03-Transformar]] |
| Evaluar | 04 Evaluar | [[04 Evaluar/04-Evaluar]] |
| eXpandir | 05 eXpandir | [[05 eXpandir/05-eXpandir]] |
