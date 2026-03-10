---
title: Jornada e Horas Extras
sidebar_position: 1
---

# Jornada e Horas Extras

## Jornada base

- Colaborador regular: `8` horas.
- Estagiario: `4` horas.

## Jornada completa

Um dia e considerado completo com **7h40m ou mais**.

```javascript
const JORNADA_MINIMA_COMPLETA = 7.67;
```

| Horas do dia | Resultado |
| --- | --- |
| `>= 7h40` | Dia completo |
| `< 7h40` | Dia incompleto |

> Em fim de semana, o dia nao deve ser classificado como incompleto.

## Calculo de horas feitas e extras

### Dias de semana (regra geral)

- Converte horario para minutos.
- Calcula diferenca entre entrada e saida.
- Para nao estagiario, desconta almoco fixo de 60 minutos.
- Horas feitas limitadas ao maximo da jornada base.
- Horas extras sao somente o excedente da jornada base.

### Tolerancia de horas extras

Horas extras menores que 30 minutos nao contabilizam:

```javascript
let horasExtras = Math.max(0, horasLiquidas - JORNADA_PADRAO);
if (horasExtras < 0.5) {
  horasExtras = 0;
}
```

## Status de aprovacao de HE

- `horasExtras >= 0.5`: `Pendente Aprovacao`
- `horasExtras < 0.5`: `N/A`

## Encerramento automatico

- Jornadas abertas podem ser encerradas automaticamente as 18:00.
- O fechamento automatico deve recalcular horas e status de HE.
