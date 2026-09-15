# Aula 02 - Camada Bronze

## Objetivo

Iniciar a construção da camada Bronze da arquitetura Medallion utilizando Databricks, Apache Spark e Delta Lake.

Nesta etapa, os dados brutos são ingeridos e armazenados de forma organizada, preservando sua estrutura original para futuras transformações.

---

## Ementa da Aula

- Entender a arquitetura medalhão (Bronze, Silver e Gold) e sua importância na governança de dados.
- Descobrir como utilizar o Genie (IA do Databricks) para acelerar o desenvolvimento de códigos e análises.
- Configurar catálogos, schemas e volumes para organizar um Data Lake.
- Iniciar o projeto prático VoeBem Analytics com dados reais da ANAC.
- Compreender os conceitos de Lakehouse, Delta Lake e orquestração de pipelines automatizados.
- Implementar a camada Bronze da Arquitetura Medallion.

---

## Ambiente Preparado

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

### Volume

```text
arquivos
```

Caminho:

```text
/Volumes/voo_bem/bronze/arquivos
```

---

## Estrutura de Arquivos

### Referências

```text
/Volumes/voo_bem/bronze/arquivos/referencias
```

Arquivos:

- AerodromosPublicos.csv
- pda_empresas_aereas_nacionais.csv
- pda_empresas_aereas_estrangeiros.csv

### VRA

```text
/Volumes/voo_bem/bronze/arquivos/vra
```

Arquivos carregados:

- VRA_202510.csv
- VRA_202511.csv
- VRA_202512.csv
- VRA_20258.csv
- VRA_20259.csv
- VRA_20261.csv
- VRA_20262.csv
- VRA_20263.csv
- VRA_20264.csv
- VRA_20265.csv
- VRA_20266.csv
- VRA_20267.csv

---

## Validações Realizadas

### Seleção do catálogo

```python
spark.sql("USE CATALOG voo_bem")
spark.sql("USE SCHEMA bronze")
```

Resultado: executado com sucesso.

### Validação das pastas

```python
display(dbutils.fs.ls("/Volumes/voo_bem/bronze/arquivos"))
```

Resultado:

```text
referencias/
vra/
```

---

## Próximos Passos

- Ler arquivos CSV utilizando Spark.
- Criar DataFrames.
- Validar schemas.
- Persistir dados em formato Delta.
- Criar tabelas da camada Bronze.
- Preparar dados para a camada Silver.