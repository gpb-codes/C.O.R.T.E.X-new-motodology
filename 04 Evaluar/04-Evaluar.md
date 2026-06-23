# Evaluar -- Areas y Salud del Sistema

## Proposito

Mantener las responsabilidades continuas sin que se degraden. Un area no se termina -- se mantiene.

---

## Reglas

- Un area no se "termina" -- se mantiene con revision periodica
- Cada area tiene checklist semanal y mensual
- Si un area no se revisa en 60 dias, pasa a estado de alerta

---

## Estado de areas

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

## Checklist semanal general

- [ ] Salud: ejercicio + sueno + alimentacion cubiertos?
- [ ] Finanzas: gastos revisados y presupuesto OK?
- [ ] Desarrollo: avance en estudio o lectura tecnica?
- [ ] Startup: metricas revisadas y OKRs encaminados?
- [ ] A.X.I.S.: extracciones procesadas y contexto actualizado?
- [ ] Relaciones: contacto con familia o amigos?

---

## Areas configuradas

| Area | Archivo | Metrica |
|---|---|---|
| Salud | [[Salud]] | Consistencia semanal |
| Finanzas | [[Finanzas]] | Saldo vs presupuesto |
| Desarrollo | [[Desarrollo]] | Horas de aprendizaje |
| Startup | [[Startup]] | Avance de OKRs |
| A.X.I.S. | [[AXIS]] | Calidad de memoria |
| Relaciones | [[Relaciones]] | Contactos por semana |
