---
title: Configuracao Inicial
sidebar_position: 3
---

# Configuracao Inicial

## 1) Validar estrutura dos boards

- Confirmar existencia dos dois boards obrigatorios.
- Confirmar IDs corretos.
- Confirmar colunas com nomes e tipos esperados.

## 2) Cadastrar colaboradores

Cada colaborador deve possuir:

- Nome completo.
- Matricula unica.
- Campo complementar (departamento/cargo), se aplicavel.

## 3) Preparar grupos mensais

Padrao esperado:

- `Janeiro-2026`
- `Fevereiro-2026`
- `Marco-2026`

O fluxo recomendado cria grupo automaticamente quando necessario.

## 4) Teste tecnico de ponta a ponta

1. Buscar colaborador por matricula.
2. Criar item pai no grupo mensal.
3. Criar subitem com `Entrada`.
4. Atualizar subitem com `Encerrar Expediente`.
5. Validar preenchimento de `Horas Feitas`, `Horas Extras` e `Status Aprovacao HE`.

## 5) Criterios de aceite minimos

- Sem erro de coluna desconhecida.
- Sem deslocamento de data por timezone.
- Sem quebra do fluxo de estagiario.
- Encerramento automatico funcional as 18:00.
