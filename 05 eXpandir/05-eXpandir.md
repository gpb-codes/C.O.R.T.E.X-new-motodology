# eXpandir -- Reflexion y Memoria Persistente

## Proposito

Extraer valor de la experiencia. Sin reflexion, el conocimiento no se consolida. Aqui se construye la memoria persistente de A.X.I.S. y se cultiva el aprendizaje continuo.

---

## Reglas

- Cada extraccion de A.X.I.S. debe tener: contexto + decision + aprendizaje + accion
- El diario no debe tomar mas de 5 minutos
- La revision semanal es obligatoria -- sin ella el sistema se degrada
- Archivar no es borrar -- es preservar con metadatos de cierre

---

## Extracciones A.X.I.S. recientes

```dataview
TABLE
  fecha as "Fecha",
  dominio as "Dominio",
  relevancia as "Relevancia"
FROM "05 eXpandir/Extracciones AXIS"
SORT fecha DESC
LIMIT 10
```

---

## Decisiones recientes

```dataview
TABLE
  fecha as "Fecha",
  eleccion as "Eleccion",
  impacto as "Impacto",
  status as "Status"
FROM "05 eXpandir/Decisiones"
SORT fecha DESC
LIMIT 10
```

---

## Diario -- ultimos 7 dias

```dataview
TABLE
  humor as "Humor",
  energia as "Energia",
  productividad as "Productividad"
FROM "05 eXpandir/Diario"
SORT file.day DESC
LIMIT 7
```

---

## Repaso pendiente (spaced repetition)

```dataview
TASK
FROM "05 eXpandir/Repaso"
WHERE !completed
SORT due ASC
```

---

## Revisiones

```dataview
TABLE
  periodo as "Periodo",
  fecha as "Fecha"
FROM "05 eXpandir/Revisiones"
SORT fecha DESC
```

---

## Decision Log

Ver [[_DECISION-LOG]] para el panel central de decisiones con status, impacto y seguimiento.

---

## Archivo

Ver [[_ARCHIVO]] para reglas de archivado por tipo de contenido y dashboard de proximo a archivar.

---

## Acciones pendientes

- [ ] Realizar revision semanal
- [ ] Consolidar extracciones AXIS de la semana
- [ ] Actualizar contexto recurrente de A.X.I.S.
- [ ] Revisar repasos vencidos (ver [[MOC-Repaso]])
- [ ] Revisar decisiones pendientes (ver [[_DECISION-LOG]])
