# MOC -- Principios

## Proposito

Principios fundamentales que guian decisiones, diseno, arquitectura y forma de trabajar. No son reglas rigidas, sino heuristicas que se refinan con la experiencia.

---

## Categorias

### Ingenieria y diseno

| Principio | Resumen | Referencia |
|---|---|---|
| KISS | Keep It Simple, Stupid |  |
| YAGNI | You Aren't Gonna Need It |  |
| DRY | Don't Repeat Yourself |  |
| SOLID | Principios de diseno OOP |  |
| Law of Demeter | Minimo conocimiento entre modulos |  |
| Separation of Concerns | Separar por responsabilidad |  |

### Producto y negocio

| Principio | Resumen | Referencia |
|---|---|---|
| Lean Startup | Build-Measure-Learn |  |
| Pareto (80/20) | 80% del valor viene del 20% del esfuerzo |  |
| First Principles | Descomponer hasta lo fundamental |  |
| Occam's Razor | La explicacion mas simple suele ser la correcta |  |

### Personales

| Principio | Resumen | Referencia |
|---|---|---|
|  |  |  |

---

## Principios activos

```dataview
TABLE
  categoria as "Categoria",
  resumen as "Resumen"
FROM #conocimiento/principios
WHERE status = "activo"
SORT categoria ASC
```

## Principios aplicados recientemente

```dataview
TABLE
  file.cday as "Aplicado",
  decision as "Decision donde se aplico"
FROM #conocimiento/principios
WHERE aplicado-el
SORT aplicado-el DESC
LIMIT 10
```

---

## Como usar este MOC

1. Al tomar una decision, revisar si aplica algun principio
2. Documentar en la decision que principio(s) se usaron
3. Si un principio se viola deliberadamente, documentar el motivo
4. Los principios se anaden, modifican o eliminan por experiencia, no por teoria
