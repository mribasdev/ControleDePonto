---
title: Pre-requisitos
sidebar_position: 1
---

# Pre-requisitos

## Requisitos técnicos

- Conta ativa no Monday.com.
- Workspace com permissão administrativa.
- Token/API com permissão de leitura e escrita.
- Acesso habilitado para criação de grupos, itens e subitens.

## Ambiente alvo

- Workspace: `CONTROLE DE PONTO - STIGMA`
- Board de colaboradores: `NÚMERO DE MATRICULA` (`18401380986`)
- Board de registros: `Registros de Ponto Diario` (`18401381007`)

## Permissões mínimas do token

- Ler itens e colunas de board.
- Criar item no board de registros.
- Criar subitem no item-pai do colaborador.
- Atualizar colunas de item e subitem.
- Criar grupo mensal quando necessário.

## Validação rápida antes de subir em produção

- Testar leitura de colaboradores.
- Testar criação de item-pai em grupo mensal.
- Testar criação e atualização de subitem diário.
- Validar que campos de hora e data retornam no formato esperado.
