# Relacionar -- Mapas de Contenido (MOCs)

## Proposito

Conectar el conocimiento para hacerlo navegable y descubrible. Cada nota debe estar enlazada al menos a un MOC para evitar conocimiento aislado.

---

## MOCs por dominio

### Conocimiento

| MOC | Descripcion | Estado |
|---|---|---|
| [[MOC-Arquitectura]] | Patrones de diseno, estilos arquitectonicos, cloud | Activo |
| [[MOC-Ciberseguridad]] | OWASP, secure coding, pentesting, criptografia | Activo |

### Estudio

| MOC | Descripcion | Estado |
|---|---|---|
| [[MOC-Cursos]] | Cursos activos, completados y rutas de aprendizaje | Activo |

### Startup

| MOC | Descripcion | Estado |
|---|---|---|
| [[MOC-Producto]] | Vision, roadmap, features, metricas | Activo |
| [[MOC-Clientes]] | Segmentos, funnel, competencia, pricing | Activo |

### A.X.I.S.

| MOC | Descripcion | Estado |
|---|---|---|
| [[MOC-Decisiones]] | Registro de decisiones y patrones detectados | Activo |
| [[MOC-Extracciones]] | Indice de extracciones por dominio | Activo |

### Transversales (multi-dominio)

| MOC | Descripcion | Estado |
|---|---|---|
| [[MOC-Herramientas]] | Catalogo de software, servicios y herramientas | Activo |
| [[MOC-Libros]] | Registro de lecturas y lista de espera | Activo |
| [[MOC-Principios]] | Heuristicas fundamentales de diseno y decision | Activo |
| [[MOC-Repaso]] | Sistema de repaso espaciado | Activo |

---

## Reglas

- Cada nota debe enlazarse al menos a un MOC
- Los enlaces son bidireccionales: si A enlaza a B, B deberia enlazar a A
- Un MOC sin notas enlazadas es un indice falso
- Usar el grafo de conocimiento para detectar notas huerfanas

---

## Estadisticas de conexion

```dataview
TABLE
  length(rows) as "Notas enlazadas"
FROM "02 MOCs"
WHERE contains(file.tags, "moc") OR contains(file.name, "MOC-")
SORT length(rows) DESC
```

---

## Notas huerfanas

Notas sin enlaces entrantes ni salientes (excluyendo MOCs y README):

```dataview
LIST
FROM -"02 MOCs"
WHERE file.outlinks = 0 AND file.inlinks = 0 AND file.name != "README"
LIMIT 10
```
