# Aula 01 - Catalog Explorer

## Objetivo

Compreender a estrutura do Catalog Explorer e a organização dos objetos no Databricks.

---

## Conceitos Fundamentais

O Databricks organiza os dados em uma estrutura hierárquica:

Catalog
└── Schema
    └── Table

Exemplo:

workspace.default.clientes

Onde:

- workspace = Catalog
- default = Schema
- clientes = Table

---

## SHOW CATALOGS

### Comando

```sql
SHOW CATALOGS;