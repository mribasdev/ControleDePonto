---
title: Boards e Colunas
sidebar_position: 2
---

# Boards e Colunas

## Boards obrigatorios

| Board | ID | Funcao |
| --- | ---: | --- |
| NÚMERO DE MATRICULA | `18401380986` | Cadastro de colaboradores |
| Registros de Ponto Diario | `18401381007` | Registros diarios e calculos |

## Board: NÚMERO DE MATRICULA

| Coluna (negocio) | Tipo | Obrigatorio | Descricao |
| --- | --- | --- | --- |
| Name | text | Sim | Nome completo do colaborador |
| Matricula | text | Sim | Identificador unico |
| Departamento/Cargo | dropdown ou text | Nao | Segmentacao interna |

## Board: Registros de Ponto Diario (item pai)

| Coluna | Tipo | Obrigatorio | Descricao |
| --- | --- | --- | --- |
| Name | text | Sim | Nome do colaborador no grupo mensal |
| Subitems | subitems | Sim | Registros diarios |

## Subitems: Registros diarios

| Coluna (negocio) | Tipo | Obrigatorio | Descricao |
| --- | --- | --- | --- |
| Data | date | Sim | Data da jornada (`YYYY-MM-DD`) |
| Acao | status | Sim | Estado atual do fluxo |
| Entrada | hour | Sim | Hora de entrada |
| Saida Almoco | hour | Nao | Inicio do intervalo |
| Volta Almoco | hour | Nao | Fim do intervalo |
| Saida Expediente | hour | Sim | Fechamento do dia |
| Horas Feitas | numbers | Sim | Horas dentro da jornada base |
| Horas Extras | numbers | Nao | Horas excedentes |
| Status Aprovacao HE | status | Nao | Pendente Aprovacao / N/A |
| Alteracao Manual | status | Nao | Indicador de edicao manual |
| Justificativa de Alteracao | long-text | Nao | Motivo da alteracao |

## Mapeamento tecnico de chaves de coluna

Algumas integracoes trabalham com chaves tecnicas internas. No legado atual, aparecem chaves como:

- `matrcula`
- `ao`
- `sadaAlmoo`
- `voltaAlmoo`
- `sadaExpediente`
- `statusAprovaoHe`
- `alteraoManual`
- `justificativaDeAlterao`

Padronize o mapeamento entre nome de negocio e chave tecnica para evitar `Unknown column`.
