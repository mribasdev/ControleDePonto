---
title: Arquitetura e Fluxo de Dados
sidebar_position: 2
---

# Arquitetura e Fluxo de Dados

## Visao de arquitetura

- **Interface de usuario**: fluxo de registro diario e consulta.
- **Camada de logica**: validacoes, proxima acao e calculo de horas.
- **Camada de integracao**: chamadas ao Monday para leitura/escrita.
- **Persistencia**: boards e subitems no Monday.com.

## Componentes funcionais

- **Registro de ponto**: executa o ciclo de marcacoes do dia.
- **Auto encerramento**: fecha jornada aberta as 18:00.
- **Dashboard operacional**: visao consolidada de colaboradores e registros.
- **Historico e edicao**: consulta e ajuste manual com justificativa.

## Modelo de dados (alto nivel)

- `NÚMERO DE MATRICULA`:
  - cadastro mestre de colaboradores.
- `Registros de Ponto Diario`:
  - item pai por colaborador dentro de grupo mensal.
- `Subitems`:
  - registro diario de jornada por data.

## Sequencia de operacao (resumo)

1. Usuario informa matricula.
2. Sistema busca colaborador no board de matriculas.
3. Sistema garante existencia de grupo mensal.
4. Sistema garante item pai do colaborador no grupo.
5. Sistema cria ou atualiza subitem diario.
6. Ao encerrar, sistema recalcula horas e status de HE.

## Logica de grupo mensal

- Nome no formato `Mes-Ano` (exemplo: `Marco-2026`).
- Se existir, reutiliza.
- Se nao existir, cria por mutacao GraphQL.

## Ponto de atencao tecnico

- Campos de subitem devem ser atualizados via `item(...).subitem(...).update(...)`.
- Datas devem ser tratadas em timezone local para evitar deslocamento de dia.
- Chaves tecnicas de coluna devem ser estaveis e alinhadas ao board.
