---
title: Pre-requisitos
sidebar_position: 1
---

# Pre-requisitos

## Requisitos tecnicos

- Conta ativa no Monday.com.
- Workspace com permissao administrativa.
- Token/API com permissao de leitura e escrita.
- Acesso habilitado para criacao de grupos, itens e subitems.

## Ambiente alvo

- Workspace: `CONTROLE DE PONTO - STIGMA`
- Board de colaboradores: `NÚMERO DE MATRICULA` (`18401380986`)
- Board de registros: `Registros de Ponto Diario` (`18401381007`)

## Permissoes minimas do token

- Ler itens e colunas de board.
- Criar item no board de registros.
- Criar subitem no item pai do colaborador.
- Atualizar colunas de item e subitem.
- Criar grupo mensal quando necessario.

## Validacao rapida antes de subir em producao

- Testar leitura de colaboradores.
- Testar criacao de item pai em grupo mensal.
- Testar criacao e atualizacao de subitem diario.
- Validar que campos de hora e data retornam no formato esperado.
