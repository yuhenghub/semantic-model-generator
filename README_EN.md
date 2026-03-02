# Semantic Model Generator

English Version | [中文版](./README.md)

> An open-source tool for generating and managing semantic models for Snowflake Cortex Analyst, with China region support.

---

## 📁 Project Structure

```
semantic-model-generator/
├── README.md                    # Documentation (Chinese)
├── README_EN.md                 # Documentation (English)
├── app.py                       # Main app entry (Streamlit)
├── environment.yml              # Conda environment config
├── pyproject.toml               # Python project config
├── Makefile                     # Build scripts
├── .env.example                 # Environment variables example
│
├── semantic_model_generator/    # Core generation logic
│   ├── data_processing/         # Data processing utilities
│   ├── protos/                  # Protocol Buffers definitions
│   ├── snowflake_utils/         # Snowflake connection & LLM utilities
│   └── validate/                # Model validation logic
│
├── app_utils/                   # Application utilities
├── journeys/                    # User journeys
├── partner/                     # Partner integrations (dbt, Looker)
├── sis_setup/                   # Streamlit in Snowflake deployment scripts
└── images/                      # Image assets
```

---

## 📌 Features

- ✅ **Auto-generate Semantic Models**: Generate semantic models from Snowflake tables/views
- ✅ **AI-powered Descriptions**: Use LLM to auto-generate field descriptions
- ✅ **Model Validation**: Validate semantic models against schema constraints
- ✅ **Partner Integrations**: Support dbt Semantic Model and Looker Explore
- ✅ **China Region Support**: Support Qwen, DeepSeek and other China-based LLMs

---

## 🚀 Quick Start

### Streamlit in Snowflake Deployment (Recommended)

```bash
# 1. Install Snowflake CLI
pip install snowflake-cli

# 2. Deploy app
snow sql -f sis_setup/app_setup.sql

# 3. Open app
snow streamlit get-url SEMANTIC_MODEL_GENERATOR --open \
    --database cortex_analyst_semantics \
    --schema semantic_model_generator
```

### Local Deployment

```bash
# 1. Create environment
conda env create -f environment.yml
conda activate semantic-model-generator

# 2. Configure environment variables
cp .env.example .env

# 3. Start app
streamlit run app.py
```

---

## 📚 Related Projects

- [Snowflake-China (SPCS)](https://github.com/yuhenghub/Snowflake-China) - Self-hosted LLM service for China region
- [cortex-agent-china](https://github.com/yuhenghub/cortex-agent-china) - Cortex Agent alternative for China region

---

## 📄 License

Apache 2.0 License

*Adapted from [Snowflake-Labs/semantic-model-generator](https://github.com/Snowflake-Labs/semantic-model-generator).*
