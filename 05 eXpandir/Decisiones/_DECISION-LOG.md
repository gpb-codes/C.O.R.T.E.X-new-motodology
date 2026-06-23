# Decision Log

## Proposito

Panel de control central para todas las decisiones registradas. Permite ver el estado de cada decision, su impacto y pendientes de revision.

---

## Status disponibles

| Status | Significado |
|---|---|
| `tomada` | Decision tomada, pendiente de resultados |
| `en-ejecucion` | Implementandose actualmente |
| `completada` | Resultado conocido |
| `revocada` | Revertida por nueva informacion |
| `pendiente` | Analisis hecho, aun no se decide |

---

## Decisiones activas (tomadas / en ejecucion)

```dataview
TABLE
  fecha as "Fecha",
  dominio as "Dominio",
  impacto as "Impacto",
  reversible as "Reversible"
FROM "05 eXpandir/Decisiones"
WHERE status = "tomada" OR status = "en-ejecucion"
SORT fecha DESC
```

## Decisiones pendientes de tomar

```dataview
TABLE
  fecha as "Fecha",
  dominio as "Dominio",
  impacto as "Impacto"
FROM "05 eXpandir/Decisiones"
WHERE status = "pendiente"
SORT impacto ASC, fecha ASC
```

## Decisiones completadas

```dataview
TABLE
  fecha as "Fecha",
  dominio as "Dominio",
  eleccion as "Eleccion"
FROM "05 eXpandir/Decisiones"
WHERE status = "completada"
SORT fecha DESC
LIMIT 20
```

## Decisiones revocadas

```dataview
TABLE
  fecha as "Fecha",
  dominio as "Dominio",
  eleccion as "Eleccion"
FROM "05 eXpandir/Decisiones"
WHERE status = "revocada"
SORT fecha DESC
```

---

## Revision pendiente

- [ ] Revisar decisiones con seguimiento vencido
- [ ] Actualizar status de decisiones en ejecucion
- [ ] Extraer patrones de decisiones del mes
