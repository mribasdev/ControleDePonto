---
title: Boas Praticas
sidebar_position: 3
---

# Boas Praticas

## Validacao antes de calcular

```javascript
if (!entrada || !saidaExpediente) {
  return { horasFeitas: 0, horasExtras: 0 };
}
```

## Tratamento de erros de integracao

```javascript
try {
  await board.item(id).update(data).execute();
} catch (err) {
  console.error("[PontoRegistro] erro de API", err);
}
```

## Logging padronizado

- Prefixar logs por contexto: `[PontoRegistro]`, `[HistoricoPontos]`, `[Dashboard]`.
- Registrar identificadores essenciais (matricula, id do item/subitem, acao).
- Nunca expor token ou credenciais.

## Governanca de schema

- Evitar renomear colunas em producao sem plano de migracao.
- Manter tabela de mapeamento negocio x chave tecnica.
- Validar periodicamente colunas obrigatorias.

## Boas praticas de operacao

- Rodar checklist de smoke test apos alteracoes de regra.
- Auditar alteracoes manuais e justificativas.
- Revisar mensalmente pendencias de aprovacao de HE.
