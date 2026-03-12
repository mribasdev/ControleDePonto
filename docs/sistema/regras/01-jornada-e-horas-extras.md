---
title: Jornada e Horas Extras
sidebar_position: 1
---

# Jornada e Horas Extras

## Jornada base

- Colaborador regular: `8` horas.
- Estagiário: `4` horas.

## Jornada completa

Um dia é considerado completo com **7h40m ou mais**.

```javascript
const JORNADA_MINIMA_COMPLETA = 7.67;
```

| Horas do dia | Resultado |
| --- | --- |
| `>= 7h40` | Dia completo |
| `< 7h40` | Dia incompleto |

> Em fim de semana, o dia não deve ser classificado como incompleto.

## Cálculo de horas feitas e extras

### Dias de semana (regra geral)

- Converte horário para minutos.
- Calcula diferença entre entrada e saída.
- Para não estagiário, desconta almoço fixo de 60 minutos.
- Horas feitas limitadas ao máximo da jornada base.
- Horas extras são somente o excedente da jornada base.

### Tolerância de horas extras

Horas extras menores que 30 minutos não contabilizam:

```javascript
let horasExtras = Math.max(0, horasLiquidas - JORNADA_PADRAO);
if (horasExtras < 0.5) {
  horasExtras = 0;
}
```

## Status de aprovação de HE

- `horasExtras >= 0.5`: `Pendente Aprovação`
- `horasExtras < 0.5`: `N/A`

## Encerramento automático

- Jornadas abertas podem ser encerradas automaticamente às 18:00.
- O fechamento automático deve recalcular horas e status de HE.
