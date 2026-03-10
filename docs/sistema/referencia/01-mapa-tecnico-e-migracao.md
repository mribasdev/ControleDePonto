---
title: Mapa Tecnico e Migracao do app
sidebar_position: 1
---

# Mapa Tecnico e Migracao do app

Esta pagina consolida o conhecimento tecnico necessario para remover a pasta `app/` sem perder regras e contexto.

## Mapa tecnico legado (origem)

| Caminho legado | Responsabilidade |
| --- | --- |
| `app/App.jsx` | Entry principal e alternancia de views |
| `app/components/PontoRegistro.jsx` | Registro diario, revisao, edicao e fechamento |
| `app/components/DashboardGeral.jsx` | Indicadores e consulta consolidada |
| `app/hooks/usePontoLogic.js` | Validacao de fluxo e calculo de horas |
| `app/hooks/useAutoClockout.js` | Encerramento automatico as 18:00 |

## Dependencias funcionais criticas

- Integracao com `NumeroDeMatriculaBoard`.
- Integracao com `RegistrosDePontoDiarioBoard`.
- Criacao dinamica de grupo mensal por GraphQL.
- Atualizacao de subitems com return de colunas chave.

## Campos tecnicos mais sensiveis

- `matrcula`
- `ao`
- `sadaAlmoo`
- `voltaAlmoo`
- `sadaExpediente`
- `statusAprovaoHe`
- `alteraoManual`
- `justificativaDeAlterao`

## Plano sugerido de migracao (apos remover app/)

1. **Mapear UI alvo**  
   Definir onde o fluxo de ponto sera executado (nova app, modulo interno ou outra camada frontend).

2. **Extrair regras de negocio**  
   Levar validacoes e calculos para modulo isolado de dominio (facil de testar e reutilizar).

3. **Encapsular integracao Monday**  
   Criar camada de servico para leitura/escrita de boards e subitems.

4. **Criar testes de regressao**  
   Cobrir: estagiario, fim de semana, corte de 30 minutos HE, timezone e fechamento automatico.

5. **Executar checklist de homologacao**  
   Validar em ambiente controlado antes da remocao definitiva do legado.

## Criterio minimo para remocao segura do app

- Todos os fluxos operacionais funcionando no novo destino.
- Regras de negocio cobrertas por teste.
- Mapeamento de colunas validado em producao.
- Logs de erro e auditoria manual ativos.
