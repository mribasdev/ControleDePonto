---
title: Fluxos Operacionais
sidebar_position: 1
---

# Fluxos Operacionais

## Fluxo diário - colaborador regular

1. Informa matrícula.
2. Sistema localiza colaborador.
3. Registra `Entrada`.
4. Registra `Saída Almoço`.
5. Registra `Volta Almoço`.
6. Registra `Encerrar Expediente`.
7. Sistema calcula e grava horas e status de HE.

## Fluxo diário - estagiário

1. Informa matrícula com prefixo `102`.
2. Registra `Entrada`.
3. Registra `Encerrar Expediente`.
4. Sistema calcula com jornada base de 4 horas.

## Fluxo de novo colaborador

1. Matrícula não encontrada.
2. Sistema solicita dados mínimos (nome e campo complementar).
3. Cria colaborador no board de matriculas.
4. Continua fluxo normal de registro.

## Fluxo de encerramento automático

1. Jornada aberta detectada no horário de corte.
2. Sistema encerra em `18:00`.
3. Recalcula horas e status.
4. Disponibiliza opção de hora extra, quando aplicável.

## Fluxo de hora extra pós-encerramento

1. Colaborador opta por continuar em HE.
2. Sistema mantem jornada ativa para nova saida.
3. Ao registrar saida final, recalcula total e HE.

## Fluxo de revisão e edição

1. Colaborador/gestor abre revisão.
2. Sistema permite ajustes de horário.
3. Solicita justificativa.
4. Atualiza registro com marca de alteração manual.
