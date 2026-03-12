---
title: Checklists
sidebar_position: 2
---

# Checklists

## Checklist de implantação

- [ ] Boards criados com IDs corretos
- [ ] Colunas obrigatórias configuradas
- [ ] Colaboradores cadastrados com matrícula única
- [ ] Regra de estagiário (`102`) validada
- [ ] Token/API configurado com escopo correto
- [ ] Teste completo com colaborador regular
- [ ] Teste completo com estagiário
- [ ] Teste de fechamento automático às 18:00
- [ ] Teste de edição manual com justificativa
- [ ] Teste de cálculo de HE com e sem limiar de 30 min
- [ ] Teste de registro em fim de semana

## Checklist de manutenção

- [ ] Monitorar erros de API e autenticação
- [ ] Auditar alterações manuais e justificativas
- [ ] Revisar pendências de aprovação de HE
- [ ] Validar consistência de grupos mensais
- [ ] Confirmar tratamento correto de timezone
- [ ] Revisar mapeamento de colunas após mudanças no board

## Checklist de migração (remoção da pasta app)

- [ ] Regras de negócio extraídas para módulo dedicado
- [ ] Camada de integração Monday isolada
- [ ] Fluxos de registro e encerramento reproduzidos
- [ ] Fluxo de estagiário reproduzido
- [ ] Fluxo de edição manual com justificativa reproduzido
- [ ] Testes de regressão executados com sucesso
- [ ] Documentação atualizada com novo caminho de código
