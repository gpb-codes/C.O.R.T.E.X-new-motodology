# Archivo — Preservacion con Metadatos

## Proposito

El archivo no es un cementerio de notas. Es una biblioteca de conocimiento consolidado con metadatos que permiten recuperarlo cuando sea relevante.

---

## Reglas de archivo

| Situacion | Accion | Metadatos requeridos |
|---|---|---|
| Proyecto completado + 90 dias inactivo | Mover a `Archivo/` | `archivado: true`, `archivar-el: fecha`, `tags: [archivado]` |
| Proyecto cancelado | Mover a `Archivo/` | Motivo de cancelacion en notas |
| Area descontinuada | Mover a `Archivo/` | Fecha de descontinuacion |
| Curso completado hace > 6 meses sin repaso | Mover a `Archivo/` | Certificado o nota final |
| Nota duplicada o fusionada | Archivar la version vieja | Enlace a la nota que la reemplaza |
| Extraccion AXIS de baja relevancia (>6 meses) | Archivar con tag `#axis/archivado` | Resumen de 1 linea |

---

## Que NO se archiva

- Notas atomicas que aun conectan con MOCs activos
- Recursos de referencia activa
- Templates
- MOCs

---

## Como archivar

1. Agregar al frontmatter: `archivado: true`, `archivar-el: YYYY-MM-DD`
2. Cambiar tags: anadir `#archivado`, remover `#activo`
3. Si aplica, enlazar a la nota que reemplaza o al MOC de archivo
4. Mover el archivo fisicamente a `05 eXpandir/Archivo/`
5. Verificar que los enlaces entrantes sigan siendo utiles

---

## Archivos recientes

```dataview
TABLE
  archivar-el as "Archivado el",
  tipo as "Tipo"
FROM "05 eXpandir/Archivo"
WHERE archivado = true
SORT archivar-el DESC
LIMIT 20
```

## Proximo a archivar

```dataview
TABLE
  fecha-fin as "Completado",
  status as "Status"
FROM "03 Transformar/Proyectos/Completados"
WHERE status = "completado" AND (date(today) - fecha-fin) > 90
SORT fecha-fin ASC
```

---

## Regla de caducidad

- Proyectos completados se archivan **automaticamente** tras 90 dias sin modificacion
- Cursos completados se archivan tras 6 meses sin repaso
- Extracciones AXIS con `relevancia < 3` se archivan tras 6 meses
- El archivo se revisa anualmente para purgar contenido obsoleto
