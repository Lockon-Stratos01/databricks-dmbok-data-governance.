# 🚀 Governança de Dados no Databricks com DAMA-DMBOK

Este repositório apresenta a implementação prática de um pipeline de dados no **Databricks**, unindo os princípios de Governança e Qualidade do framework **DAMA-DMBOK** à **Arquitetura Medallion** (Bronze, Silver e Gold).

O objetivo principal é demonstrar como estruturar um pipeline completo com rastreabilidade, tratamento de qualidade e metadados organizados no **Unity Catalog**.

---

## 📁 Estrutura do Repositório

* **[Documentação dos Notebooks](./notebooks/README.md):** Código PySpark e explicação de cada camada do pipeline.
* **[Evidências e Capturas de Tela](./Docs/README.md):** Validação visual da execução e das tags de governança no Unity Catalog.

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
