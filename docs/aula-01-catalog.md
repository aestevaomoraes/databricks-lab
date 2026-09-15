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

SHOW CATALOGS;

# Aula 01 - Catálogo e Organização dos Dados no Databricks

## Objetivo

Preparar o ambiente de trabalho no Databricks utilizando o Unity Catalog para armazenar e organizar os dados que serão utilizados ao longo da imersão.

---

## Estrutura Criada

### Catálogo

```text
voo_bem
```

### Schemas

```text
bronze
silver
gold
```

- Bronze: dados brutos.
- Silver: dados tratados e padronizados.
- Gold: dados prontos para consumo e análise.

---

## Volume Criado

Volume:

```text
arquivos
```

Caminho:

```text
/Volumes/voo_bem/bronze/arquivos
```

---

## Arquivos Carregados

### Referências

Diretório:

```text
/Volumes/voo_bem/bronze/arquivos/referencias
```

Arquivos:

```text
AerodromosPublicos.csv
pda_empresas_aereas_nacionais.csv
pda_empresas_aereas_estrangeiros.csv
```

### Voos Regulares Ativos (VRA)

Diretório:

```text
/Volumes/voo_bem/bronze/arquivos/vra
```

Arquivos carregados:

```text
VRA_20251.csv
VRA_20252.csv
VRA_20253.csv
...
```

---

## Conceitos Aprendidos

### Unity Catalog

Camada de governança do Databricks responsável por organizar:

- Catálogos
- Schemas
- Tabelas
- Volumes

### Volumes

Permitem armazenar arquivos não estruturados dentro do Lakehouse.

Exemplos:

- CSV
- JSON
- Imagens
- Arquivos de configuração

### Arquitetura Medallion

#### Bronze

Dados brutos sem tratamento.

#### Silver

Dados limpos e enriquecidos.

#### Gold

Dados agregados e prontos para dashboards e analytics.

---

## Observações

Foi necessário atualizar o arquivo:

```text
pda_empresas_aereas_nacionais.csv
```

utilizando uma versão mais recente disponível nos dados abertos da ANAC.

A estrutura final permaneceu compatível com a utilizada durante a aula.

---

## Próximos Passos

- Ler os arquivos CSV com Spark.
- Criar tabelas Delta na camada Bronze.
- Iniciar as transformações de dados na Aula 2.