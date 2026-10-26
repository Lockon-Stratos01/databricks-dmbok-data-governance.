# 💻 Documentação do Pipeline (Notebooks)

Esta pasta contém a lógica do pipeline dividido nas três camadas da Arquitetura Medallion.

---

### 1. Camada Bronze (Ingestão)
Recebe os dados brutos mantendo a estrutura original e adiciona campos de auditoria para rastreabilidade (*Data Lineage*).

```python
from pyspark.sql.functions import current_timestamp, lit

dados_vendas = [
    ("PED-001", "Notebook Dell", "Eletrônicos", 3500.0, "2026-01-15", "SP"),
    ("PED-002", "Mouse Sem Fio", "Acessórios", 80.0, "2026-01-16", "RJ"),
    ("PED-003", "Teclado Mecânico", "Acessórios", 250.0, "2026-01-17", "MG"),
    ("PED-004", "Monitor 27", "Eletrônicos", 1200.0, "2026-01-18", "SP"),
    ("PED-005", "Cadeira Gamer", "Móveis", 950.0, "2026-01-19", "PR")
]

colunas = ["id_pedido", "produto", "categoria", "valor", "data_pedido", "estado"]
df_raw = spark.createDataFrame(dados_vendas, colunas)

# Auditoria DMBOK
df_bronze = df_raw \
    .withColumn("_ingestion_timestamp", current_timestamp()) \
    .withColumn("_source_file", lit("stream_vendas_ecommerce.json"))

df_bronze.write.format("delta") \
    .mode("overwrite") \
    .option("overwriteSchema", "true") \
    .saveAsTable("dmbok_lakehouse.bronze.tbl_sales_raw")
