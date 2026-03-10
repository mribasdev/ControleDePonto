---
title: Fluxos Operacionais
sidebar_position: 1
---

# Fluxos Operacionais

## Fluxo diario - colaborador regular

1. Informa matricula.
2. Sistema localiza colaborador.
3. Registra `Entrada`.
4. Registra `Saida Almoco`.
5. Registra `Volta Almoco`.
6. Registra `Encerrar Expediente`.
7. Sistema calcula e grava horas e status de HE.

## Fluxo diario - estagiario

1. Informa matricula com prefixo `102`.
2. Registra `Entrada`.
3. Registra `Encerrar Expediente`.
4. Sistema calcula com jornada base de 4 horas.

## Fluxo de novo colaborador

1. Matricula nao encontrada.
2. Sistema solicita dados minimos (nome e campo complementar).
3. Cria colaborador no board de matriculas.
4. Continua fluxo normal de registro.

## Fluxo de encerramento automatico

1. Jornada aberta detectada no horario de corte.
2. Sistema encerra em `18:00`.
3. Recalcula horas e status.
4. Disponibiliza opcao de hora extra, quando aplicavel.

## Fluxo de hora extra pos-encerramento

1. Colaborador opta por continuar em HE.
2. Sistema mantem jornada ativa para nova saida.
3. Ao registrar saida final, recalcula total e HE.

## Fluxo de revisao e edicao

1. Colaborador/gestor abre revisao.
2. Sistema permite ajustes de horario.
3. Solicita justificativa.
4. Atualiza registro com marca de alteracao manual.
