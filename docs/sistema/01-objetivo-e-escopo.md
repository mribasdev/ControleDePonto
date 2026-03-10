---
title: Objetivo e Escopo
sidebar_position: 1
---

# Objetivo e Escopo

O Sistema de Controle de Ponto Digital centraliza o registro de jornada e o calculo de horas com integracao ao Monday.com.

## Objetivo principal

- Registrar marcacoes diarias de ponto (entrada, almoco, saida).
- Calcular horas feitas e horas extras com regras de negocio.
- Garantir rastreabilidade para ajustes manuais.
- Disponibilizar dados operacionais para colaborador e gestao.

## Escopo funcional

### Cadastro e identificacao

- Busca de colaborador por matricula.
- Cadastro de colaborador quando matricula nao existe.
- Identificacao automatica de estagiario por prefixo de matricula (`102`).

### Jornada diaria

- Fluxo regular: `Registrar Entrada` -> `Saida Almoco` -> `Volta Almoco` -> `Encerrar Expediente`.
- Fluxo estagiario: `Registrar Entrada` -> `Encerrar Expediente`.
- Encerramento automatico de jornadas abertas as 18:00.

### Calculo e status

- Calculo de horas feitas e horas extras.
- Regra de tolerancia para HE inferior a 30 minutos.
- Status de aprovacao de HE (`Pendente Aprovacao` ou `N/A`).
- Tratamento especial de fim de semana.

### Governanca e auditoria

- Edicao manual com justificativa.
- Marcacao explicita de alteracao manual.
- Logs de erro para analise operacional.

## Escopo tecnico

- Persistencia principal nos boards Monday.com.
- Integracao via Board SDK / API GraphQL.
- Regras de negocio concentradas na camada de logica.

## Fora de escopo (versao atual)

- Folha de pagamento.
- Gestao de beneficios.
- Controle de ferias e ausencias formais.
- Aprovação multinivel de HE por perfis hierarquicos.
