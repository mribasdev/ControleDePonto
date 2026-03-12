---
title: Arquitetura e Fluxo de Dados
sidebar_position: 2
---

# Arquitetura e Fluxo de Dados

## Visão de arquitetura

- **Interface de usuário**: fluxo de registro diário e consulta.
- **Camada de lógica**: validações, próxima ação e cálculo de horas.
- **Camada de integração**: chamadas ao Monday para leitura/escrita.
- **Persistência**: boards e subitens no Monday.com.

## Componentes funcionais

- **Registro de ponto**: executa o ciclo de marcações do dia.
- **Autoencerramento**: fecha jornada aberta às 18:00.
- **Dashboard operacional**: visão consolidada de colaboradores e registros.
- **Histórico e edição**: consulta e ajuste manual com justificativa.

## Modelo de dados (alto nível)

- `NÚMERO DE MATRICULA`:
  - cadastro-mestre de colaboradores.
- `Registros de Ponto Diario`:
  - item pai por colaborador dentro de grupo mensal.
- `Subitems`:
  - registro diário de jornada por data.

## Sequência de operação (resumo)

1. Usuário informa matrícula.
2. Sistema busca colaborador no board de matriculas.
3. Sistema garante existência de grupo mensal.
4. Sistema garante item pai do colaborador no grupo.
5. Sistema cria ou atualiza subitem diario.
6. Ao encerrar, sistema recalcula horas e status de HE.

## Lógica de grupo mensal

- Nome no formato `Mês-Ano` (exemplo: `Março-2026`).
- Se existir, reutiliza.
- Se não existir, cria por mutação GraphQL.

## Ponto de atenção técnico

- Campos de subitem devem ser atualizados via `item(...).subitem(...).update(...)`.
- Datas devem ser tratadas em timezone local para evitar deslocamento de dia.
- Chaves técnicas de coluna devem ser estáveis e alinhadas ao board.
