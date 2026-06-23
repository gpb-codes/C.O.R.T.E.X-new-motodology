# MOC -- Extracciones A.X.I.S.

## Proposito

Indice de todas las extracciones de sesiones con A.X.I.S., organizadas por dominio y fecha.

---

## Estadisticas

- **Total de extracciones:**
- **Ultima sesion:**
- **Dominio mas frecuente:**

## Ultimas extracciones

```dataview
TABLE
  fecha as "Fecha",
  dominio as "Dominio",
  relevancia as "Relevancia"
FROM "05 eXpandir/Extracciones AXIS"
SORT fecha DESC
LIMIT 20
```

## Por dominio

### Conocimiento

```dataview
TABLE fecha as "Fecha"
FROM "05 eXpandir/Extracciones AXIS"
WHERE dominio = "conocimiento"
SORT fecha DESC
```

### Estudio

```dataview
TABLE fecha as "Fecha"
FROM "05 eXpandir/Extracciones AXIS"
WHERE dominio = "estudio"
SORT fecha DESC
```

### Startup

```dataview
TABLE fecha as "Fecha"
FROM "05 eXpandir/Extracciones AXIS"
WHERE dominio = "startup"
SORT fecha DESC
```

### Sistema

```dataview
TABLE fecha as "Fecha"
FROM "05 eXpandir/Extracciones AXIS"
WHERE dominio = "sistema"
SORT fecha DESC
```
