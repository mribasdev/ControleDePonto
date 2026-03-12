---
title: Configuração Inicial
sidebar_position: 3
---

# Configuração Inicial

## 1) Validar estrutura dos boards

- Confirmar existência dos dois boards obrigatórios.
- Confirmar IDs corretos.
- Confirmar colunas com nomes e tipos esperados.

## 2) Cadastrar colaboradores

Cada colaborador deve possuir:

- Nome completo.
- Matrícula única.
- Campo complementar (departamento/cargo), se aplicável.

## 3) Preparar grupos mensais

Padrão esperado:

- `Janeiro-2026`
- `Fevereiro-2026`
- `Março-2026`

O fluxo recomendado cria grupo automaticamente quando necessário.

## 4) Teste técnico de ponta a ponta

1. Buscar colaborador por matrícula.
2. Criar item pai no grupo mensal.
3. Criar subitem com `Entrada`.
4. Atualizar subitem com `Encerrar Expediente`.
5. Validar preenchimento de `Horas Feitas`, `Horas Extras` e `Status Aprovacao HE`.

## 5) Critérios de aceite mínimos

- Sem erro de coluna desconhecida.
- Sem deslocamento de data por timezone.
- Sem quebra do fluxo de estagiário.
- Encerramento automático funcional às 18:00.
