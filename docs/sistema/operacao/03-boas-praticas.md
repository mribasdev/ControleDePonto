---
title: Boas Práticas
sidebar_position: 3
---

# Boas Práticas

## Validação antes de calcular

```javascript
if (!entrada || !saidaExpediente) {
  return { horasFeitas: 0, horasExtras: 0 };
}
```

## Tratamento de erros de integração

```javascript
try {
  await board.item(id).update(data).execute();
} catch (err) {
  console.error("[PontoRegistro] erro de API", err);
}
```

## Logging padronizado

- Prefixar logs por contexto: `[PontoRegistro]`, `[HistoricoPontos]`, `[Dashboard]`.
- Registrar identificadores essenciais (matrícula, id do item/subitem, ação).
- Nunca expor token ou credenciais.

## Governança de schema

- Evitar renomear colunas em produção sem plano de migração.
- Manter tabela de mapeamento negócio x chave técnica.
- Validar periodicamente colunas obrigatórias.

## Boas práticas de operação

- Rodar checklist de smoke test após alterações de regra.
- Auditar alterações manuais e justificativas.
- Revisar mensalmente pendências de aprovação de HE.
