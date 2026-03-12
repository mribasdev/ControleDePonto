---
title: Mapa Técnico e Migração do app
sidebar_position: 1
---

# Mapa Técnico e Migração do app

Esta página consolida o conhecimento técnico necessário para remover a pasta `app/` sem perder regras e contexto.

## Mapa técnico legado (origem)

| Caminho legado | Responsabilidade |
| --- | --- |
| `app/App.jsx` | Entry principal e alternância de views |
| `app/components/PontoRegistro.jsx` | Registro diário, revisão, edição e fechamento |
| `app/components/DashboardGeral.jsx` | Indicadores e consulta consolidada |
| `app/hooks/usePontoLogic.js` | Validação de fluxo e cálculo de horas |
| `app/hooks/useAutoClockout.js` | Encerramento automático às 18:00 |

## Dependências funcionais críticas

- Integracao com `NumeroDeMatriculaBoard`.
- Integracao com `RegistrosDePontoDiarioBoard`.
- Criação dinâmica de grupo mensal por GraphQL.
- Atualização de subitems com return de colunas-chave.

## Campos técnicos mais sensíveis

- `matricula`
- `acao`
- `saidaAlmoco`
- `voltaAlmoco`
- `saidaExpediente`
- `statusAprovacaoHe`
- `alteracaoManual`
- `justificativaDeAlteracao`

## Plano sugerido de migração (após remover app/)

1. **Mapear UI alvo**  
   Definir onde o fluxo de ponto será executado (nova app, módulo interno ou outra camada frontend).

2. **Extrair regras de negócio**  
   Levar validações e cálculos para módulo isolado de domínio (fácil de testar e reutilizar).

3. **Encapsular integração Monday**  
   Criar camada de serviço para leitura/escrita de boards e subitems.

4. **Criar testes de regressão**  
   Cobrir: estagiário, fim de semana, corte de 30 minutos HE, timezone e fechamento automático.

5. **Executar checklist de homologação**  
   Validar em ambiente controlado antes da remoção definitiva do legado.

## Critério mínimo para remoção segura do app

- Todos os fluxos operacionais funcionando no novo destino.
- Regras de negócio cobertas por teste.
- Mapeamento de colunas validado em produção.
- Logs de erro e auditoria manual ativos.
