---
title: Checklists
sidebar_position: 2
---

# Checklists

## Checklist de implantacao

- [ ] Boards criados com IDs corretos
- [ ] Colunas obrigatorias configuradas
- [ ] Colaboradores cadastrados com matricula unica
- [ ] Regra de estagiario (`102`) validada
- [ ] Token/API configurado com escopo correto
- [ ] Teste completo com colaborador regular
- [ ] Teste completo com estagiario
- [ ] Teste de fechamento automatico as 18:00
- [ ] Teste de edicao manual com justificativa
- [ ] Teste de calculo de HE com e sem limiar de 30 min
- [ ] Teste de registro em fim de semana

## Checklist de manutencao

- [ ] Monitorar erros de API e autenticacao
- [ ] Auditar alteracoes manuais e justificativas
- [ ] Revisar pendencias de aprovacao de HE
- [ ] Validar consistencia de grupos mensais
- [ ] Confirmar tratamento correto de timezone
- [ ] Revisar mapeamento de colunas apos mudancas no board

## Checklist de migracao (remocao da pasta app)

- [ ] Regras de negocio extraidas para modulo dedicado
- [ ] Camada de integracao Monday isolada
- [ ] Fluxos de registro e encerramento reproduzidos
- [ ] Fluxo de estagiario reproduzido
- [ ] Fluxo de edicao manual com justificativa reproduzido
- [ ] Testes de regressao executados com sucesso
- [ ] Documentacao atualizada com novo caminho de codigo
