# MOC -- Repaso Espaciado

## Proposito

Sistema de repaso espaciado para consolidar conocimiento a largo plazo. Cada nota de repaso se revisa en intervalos crecientes hasta que el concepto se fija.

---

## Proximos repasos

```dataview
TABLE
  fecha-repaso as "Ultimo repaso",
  proximo-repaso as "Proximo",
  dificultad as "Dificultad",
  intervalo as "Intervalo (dias)"
FROM "05 eXpandir/Repaso"
WHERE proximo-repaso <= date(today) OR proximo-repaso = date(today)
SORT proximo-repaso ASC
```

## Repasos futuros

```dataview
TABLE
  fecha-repaso as "Ultimo repaso",
  proximo-repaso as "Proximo",
  dificultad as "Dificultad"
FROM "05 eXpandir/Repaso"
WHERE proximo-repaso > date(today)
SORT proximo-repaso ASC
```

---

## Reglas del sistema

| Si la dificultad es | Accion sobre intervalo |
|---|---|
| 1 (facil) | Duplicar intervalo |
| 2-3 (medio) | Mantener intervalo |
| 4-5 (dificil) | Reducir intervalo a la mitad |

## Intervalos base por ronda

| Ronda | Intervalo |
|---|---|
| 1 | 1 dia |
| 2 | 3 dias |
| 3 | 7 dias |
| 4 | 14 dias |
| 5 | 30 dias |
| 6 | 60 dias |
| 7+ | 120 dias |

---

## Notas de repaso por dominio

```dataview
TABLE
  dominio as "Dominio",
  dificultad as "Dificultad"
FROM "05 eXpandir/Repaso"
SORT dominio ASC
```

## Pendientes del sistema

- [ ] Revisar repasos vencidos
- [ ] Actualizar intervalos post-repaso
