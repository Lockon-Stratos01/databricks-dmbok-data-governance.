from pyspark.sql.functions import sum, count, date_trunc, col

df_silver = spark.read.table("dmbok_lakehouse.silver.tbl_sales_cleaned")

df_gold = df_silver.groupBy(date_trunc("month", col("data_pedido")).alias("mes_referencia")) \
    .agg(
        sum("valor").alias("faturamento_total"),
        count("id_pedido").alias("total_pedidos")
    )

df_gold.write.format("delta") \
    .mode("overwrite") \
    .option("overwriteSchema", "true") \
    .saveAsTable("dmbok_lakehouse.gold.fato_faturamento_mensal")
