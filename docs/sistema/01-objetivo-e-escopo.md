---
title: Objetivo e Escopo
sidebar_position: 1
---

# Objetivo e Escopo

O Sistema de Controle de Ponto Digital centraliza o registro de jornada e o cálculo de horas com integração ao Monday.com.

## Objetivo principal

- Registrar marcações diárias de ponto (entrada, almoço, saída).
- Calcular horas feitas e horas extras com regras de negócio.
- Garantir rastreabilidade para ajustes manuais.
- Disponibilizar dados operacionais para colaborador e gestão.

## Escopo funcional

### Cadastro e identificação

- Busca de colaborador por matrícula.
- Cadastro de colaborador quando matrícula não existe.
- Identificação automática de estagiário por prefixo de matrícula (`102`).

### Jornada diária

- Fluxo regular: `Registrar Entrada` -> `Saída Almoço` -> `Volta Almoço` -> `Encerrar Expediente`.
- Fluxo estagiário: `Registrar Entrada` -> `Encerrar Expediente`.
- Encerramento automático de jornadas abertas às 18:00.

### Cálculo e status

- Cálculo de horas feitas e horas extras.
- Regra de tolerância para HE inferior a 30 minutos.
- Status de aprovação de HE (`Pendente Aprovação` ou `N/A`).
- Tratamento especial de fim de semana.

### Governanca e auditoria

- Edição manual com justificativa.
- Marcação explícita de alteração manual.
- Logs de erro para análise operacional.

## Escopo técnico

- Persistência principal nos boards Monday.com.
- Integracao via Board SDK / API GraphQL.
- Regras de negócio concentradas na camada de lógica.

## Fora de escopo (versao atual)

- Folha de pagamento.
- Gestão de benefícios.
- Controle de férias e ausências formais.
- Aprovação multinível de HE por perfis hierárquicos.
