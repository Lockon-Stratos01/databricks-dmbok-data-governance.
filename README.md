# databricks-dmbok-data-governance.
Pipeline de Dados no Databricks com Arquitetura Medallion e aplicação prática do framework DAMA-DMBOK para Governança e Qualidade de Dados.

# 🚀 Governança de Dados no Databricks com DAMA-DMBOK

Este projeto demonstra a implementação prática de um pipeline de dados no **Databricks**, conectando os princípios de Governança e Qualidade do **DAMA-DMBOK** à **Arquitetura Medallion** (Bronze, Silver e Gold).

O objetivo é garantir o fluxo completo de dados com qualidade, rastreabilidade e metadados estruturados para o negócio.

---

## 📁 Estrutura do Repositório

* **[`notebooks/README.md`](./notebooks/README.md):** Documentação técnica das etapas do código PySpark (Bronze, Silver e Gold).
* **[`docs/README.md`](./docs/README.md):** Evidências de execução e capturas de tela do Unity Catalog e Tags de Governança.

---

## 💡 Aplicação Prática do DAMA-DMBOK

| Pilar DAMA-DMBOK | Aplicação no Databricks |
| :--- | :--- |
| **Data Governance** | Separação de camadas no Unity Catalog (`dmbok_lakehouse.bronze`, `silver`, `gold`). |
| **Data Quality** | Filtragem de nulos, tipagem e regras de validação de negócio na camada Silver. |
| **Metadata Management** | Inserção de colunas de auditoria (`_ingestion_timestamp`) e **TAGS** de qualidade no catálogo. |
| **Storage & Operations** | Persistência em Delta Lake com suporte a transações e `overwriteSchema`. |

---

## 🧰 Tecnologias Utilizadas
* **Databricks** (Unity Catalog)
* **PySpark** & **Delta Lake**
* **Framework DAMA-DMBOK**
