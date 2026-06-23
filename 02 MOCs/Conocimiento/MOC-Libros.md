# MOC -- Libros

## Proposito

Registro de libros leidos, en progreso y en lista de espera. Cada libro tiene notas atomicas, citas destacadas y conexiones con otros temas del vault.

---

## Lectura actual

```dataview
TABLE
  autor as "Autor",
  progreso as "Progreso",
  formato as "Formato"
FROM #conocimiento/libros
WHERE status = "leyendo"
```

## Por leer (lista de espera)

```dataview
TABLE
  autor as "Autor",
  prioridad as "Prioridad",
  motivo as "Por que leerlo"
FROM #conocimiento/libros
WHERE status = "pendiente"
SORT prioridad ASC
```

## Completados

```dataview
TABLE
  autor as "Autor",
  fecha-fin as "Terminado",
  rating as "Rating"
FROM #conocimiento/libros
WHERE status = "completado"
SORT fecha-fin DESC
```

---

## Lectura transversal

| Libro | Dominio principal | Segundo dominio |
|---|---|---|
|  |  |  |

## Citas destacadas

```dataview
TABLE
  file.link as "Nota",
  cita as "Cita"
FROM #conocimiento/libros
WHERE cita
LIMIT 10
```

---

## Formato sugerido para notas de libros

```
# Libro: [Titulo]

## Metadata
- Autor:
- Ano:
- Formato: Fisico / Digital / Audio
- Paginas:
- Rating: /10

## Resumen

## Citas destacadas
> ...

## Conexiones

## Acciones derivadas
- [ ] Implementar [concepto] de este libro
