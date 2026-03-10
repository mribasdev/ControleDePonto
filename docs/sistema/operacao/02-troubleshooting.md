---
title: Troubleshooting
sidebar_position: 2
---

# Troubleshooting

## Erro: Unknown column

### Sintoma

Erro ao criar/atualizar registro:

`Error: Unknown column: "data"`

### Causa comum

Atualizacao de coluna de subitem feita no item pai.

### Correcao

```javascript
// ERRADO
await board.item(registroId).update({ data: "2025-03-10" });

// CORRETO
await board.item(itemPaiId)
  .subitem(registroId)
  .update({ data: "2025-03-10" });
```

## Problema: data aparece um dia antes

### Causa

`new Date("YYYY-MM-DD")` interpreta em UTC.

### Solucao

```javascript
const [ano, mes, dia] = dataString.split("-").map(Number);
const date = new Date(ano, mes - 1, dia);
```

Evitar:

```javascript
new Date("YYYY-MM-DD");
```

## Erro: data.split is not a function

### Causa

A funcao recebeu `Date` em vez de `string`.

### Solucao

```javascript
let diaAtual;
if (data instanceof Date) {
  diaAtual = data;
} else {
  const [ano, mes, dia] = data.split("-").map(Number);
  diaAtual = new Date(ano, mes - 1, dia);
}
```

## Falha de autenticacao na API

### Possiveis causas

- Token expirado ou revogado.
- Escopo insuficiente.

### Acoes

1. Renovar token.
2. Validar escopos de leitura/escrita/criacao.
3. Reexecutar teste de criacao de subitem.

## Registro arquivado/inativo nao edita

### Sintoma

Erro indicando item inativo ou arquivado.

### Acoes

- Verificar automacoes no board.
- Desarquivar item/subitem.
- Repetir operacao de update.
