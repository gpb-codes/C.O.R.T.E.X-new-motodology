# MOC -- Herramientas

## Proposito

Catalogo de herramientas, software, servicios y utilities que uso o he evaluado. Cada entrada incluye contexto de uso, alternativas y decision de adopcion.

---

## Por categoria

### Desarrollo

| Herramienta | Uso | Status |
|---|---|---|
|  |  | Activa / Evaluando / Descartada |

### Productividad

| Herramienta | Uso | Status |
|---|---|---|
| Obsidian | PKM / Vault CORTEX | Activa |

### Diseno

| Herramienta | Uso | Status |
|---|---|---|
|  |  |  |

### Infra / DevOps

| Herramienta | Uso | Status |
|---|---|---|
|  |  |  |

---

## Herramientas activas

```dataview
TABLE
  uso as "Uso",
  fecha-adopcion as "Desde"
FROM #conocimiento/herramientas
WHERE status = "activa"
SORT uso ASC
```

## Herramientas evaluadas

```dataview
TABLE
  uso as "Uso",
  alternativa-elegida as "Elegida"
FROM #conocimiento/herramientas
WHERE status = "evaluando" OR status = "descartada"
SORT status ASC
```

---

## Principios de seleccion

- Preferir herramientas con exportacion abierta (Markdown, JSON, CSV)
- Evitar vendor lock-in siempre que sea posible
- Una herramienta por categoria, salvo que la suplemente
- Documentar por que se eligio cada herramienta
