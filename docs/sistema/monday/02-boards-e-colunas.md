---
title: Boards e Colunas
sidebar_position: 2
---

# Boards e Colunas

## Boards obrigatórios

| Board | ID | Função |
| --- | ---: | --- |
| NÚMERO DE MATRICULA | `18401380986` | Cadastro de colaboradores |
| Registros de Ponto Diário | `18401381007` | Registros diários e cálculos |

## Board: NÚMERO DE MATRICULA

| Coluna (negócio) | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| Name | text | Sim | Nome completo do colaborador |
| Matricula | text | Sim | Identificador unico |
| Departamento/Cargo | dropdown ou text | Nao | Segmentacao interna |

## Board: Registros de Ponto Diário (item-pai)

| Coluna | Tipo | Obrigatorio | Descricao |
| --- | --- | --- | --- |
| Name | text | Sim | Nome do colaborador no grupo mensal |
| Subitems | subitems | Sim | Registros diários |

## Subitems: Registros diários

| Coluna (negócio) | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| Data | date | Sim | Data da jornada (`YYYY-MM-DD`) |
| Ação | status | Sim | Estado atual do fluxo |
| Entrada | hour | Sim | Hora de entrada |
| Saída Almoço | hour | Não | Início do intervalo |
| Volta Almoço | hour | Não | Fim do intervalo |
| Saída Expediente | hour | Sim | Fechamento do dia |
| Horas Feitas | numbers | Sim | Horas dentro da jornada base |
| Horas Extras | numbers | Não | Horas excedentes |
| Status Aprovação HE | status | Não | Pendente Aprovação / N/A |
| Alteração Manual | status | Não | Indicador de edição manual |
| Justificativa de Alteração | long-text | Não | Motivo da alteração |

## Mapeamento técnico de chaves de coluna

Algumas integrações trabalham com chaves técnicas internas. Padronize o mapeamento entre nome de negócio e chave técnica para evitar erro de `Unknown column`.

Exemplo de mapeamento padronizado:

- `matricula`
- `acao`
- `saidaAlmoco`
- `voltaAlmoco`
- `saidaExpediente`
- `statusAprovacaoHe`
- `alteracaoManual`
- `justificativaDeAlteracao`
