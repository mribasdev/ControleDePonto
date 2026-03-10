---
title: Estagiarios e Fim de Semana
sidebar_position: 2
---

# Estagiarios e Fim de Semana

## Identificacao de estagiario

Matricula iniciando com `102`:

```javascript
const isEstagiario = matricula.trim().startsWith("102");
```

## Regras para estagiarios

- Jornada base: `4` horas.
- Fluxo sem almoco.
- Ciclo diario: `Entrada -> Saida`.
- Hora extra apenas acima de 4 horas.

## Regras para fim de semana

Trabalho em sabado e domingo e contabilizado como hora extra:

```javascript
const diaSemana = diaAtual.getDay();
const isFimDeSemana = diaSemana === 0 || diaSemana === 6;
```

Comportamento esperado no fim de semana:

- `horasFeitas = 0`
- `horasExtras = total de horas liquidas`
- Sem classificacao de "dia incompleto"

## Edicao manual e rastreabilidade

Ao editar horarios manualmente:

- Recalcular horas feitas e extras.
- Marcar `Alteracao Manual` como alterada.
- Exigir `Justificativa de Alteracao`.
- Preservar historico para auditoria.
