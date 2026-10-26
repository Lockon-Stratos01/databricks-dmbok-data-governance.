from pyspark.sql.functions import col, to_timestamp

df_bronze = spark.read.table("dmbok_lakehouse.bronze.tbl_sales_raw")

# Limpeza e validação
df_silver = df_bronze \
    .filter(col("data_pedido").isNotNull()) \
    .withColumn("data_pedido", to_timestamp(col("data_pedido"))) \
    .filter(col("valor").cast("double") > 0)

df_silver.write.format("delta") \
    .mode("overwrite") \
    .option("overwriteSchema", "true") \
    .saveAsTable("dmbok_lakehouse.silver.tbl_sales_cleaned")

# Atribuição de Tags DMBOK
spark.sql("ALTER TABLE dmbok_lakehouse.silver.tbl_sales_cleaned SET TAGS ('data_quality' = 'passed', 'dmbok_domain' = 'sales');")
