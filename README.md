# 🚀 Governança de Dados no Databricks com DAMA-DMBOK

Este repositório apresenta a implementação prática de um pipeline de dados no **Databricks**, unindo os princípios de Governança e Qualidade do framework **DAMA-DMBOK** à **Arquitetura Medallion** (Bronze, Silver e Gold).

---

## 🔗 Acesso Direto aos Códigos e Evidências (6 Etapas)

Explore diretamente cada parte específica do projeto através dos links abaixo:

### 💻 Códigos do Pipeline (Notebooks)
1. **[Código - Camada Bronze (Ingestão de Dados Brutos)](./notebooks/01_bronze_ingestion.md)**
2. **[Código - Camada Silver (Qualidade e Regras de Negócio)](./notebooks/02_silver_quality.md)**
3. **[Código - Camada Gold (Data Mart e Agregação)](./notebooks/03_gold_datamart.md)**

### 📸 Evidências Visuais (Unity Catalog e Execução)
4. **[Evidência - Ingestão e Estrutura Medallion](./docs/01_lakehouse_bronze_ingestion.png)**
5. **[Evidência - Governança e Tags DAMA-DMBOK (Silver)](./docs/02_dmbok_silver_governance_tags.png)**
6. **[Evidência - Modelagem da Tabela Fato (Gold)](./docs/03_gold_business_mart.png)**

---

## 💡 Aplicação Prática do DAMA-DMBOK

| Pilar DAMA-DMBOK | Aplicação no Databricks |
| :--- | :--- |
| **Data Governance** | Organização lógica no Unity Catalog (`dmbok_lakehouse.bronze`, `silver`, `gold`). |
| **Data Quality** | Filtragem de nulos, tipagem e validação de regras de negócio na camada Silver. |
| **Metadata Management** | Inserção de colunas de auditoria (`_ingestion_timestamp`) e **TAGS** de qualidade no catálogo. |
| **Storage & Operations** | Armazenamento em Delta Lake com suporte a transações ACID e `overwriteSchema`. |

---

## 🧰 Tecnologias
* **Databricks** (Unity Catalog & Serverless Compute)
* **PySpark** & **Delta Lake**
* **Framework DAMA-DMBOK**
