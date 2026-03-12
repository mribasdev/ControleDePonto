---
title: Estagiários e Fim de Semana
sidebar_position: 2
---

# Estagiários e Fim de Semana

## Identificação de estagiário

Matrícula iniciando com `102`:

```javascript
const isEstagiario = matricula.trim().startsWith("102");
```

## Regras para estagiários

- Jornada base: `4` horas.
- Fluxo sem almoço.
- Ciclo diário: `Entrada -> Saída`.
- Hora extra apenas acima de 4 horas.

## Regras para fim de semana

Trabalho em sábado e domingo é contabilizado como hora extra:

```javascript
const diaSemana = diaAtual.getDay();
const isFimDeSemana = diaSemana === 0 || diaSemana === 6;
```

Comportamento esperado no fim de semana:

- `horasFeitas = 0`
- `horasExtras = total de horas líquidas`
- Sem classificação de "dia incompleto"

## Edição manual e rastreabilidade

Ao editar horários manualmente:

- Recalcular horas feitas e extras.
- Marcar `Alteração Manual` como alterada.
- Exigir `Justificativa de Alteração`.
- Preservar histórico para auditoria.
