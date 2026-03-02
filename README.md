# Semantic Model Generator

[English Version](./README_EN.md) | 中文版

> 为 Snowflake Cortex Analyst 生成和管理语义模型的开源工具，支持 Snowflake 中国区部署。

---

## 📁 项目结构

```
semantic-model-generator/
├── README.md                    # 项目文档 (中文)
├── README_EN.md                 # 项目文档 (English)
├── app.py                       # 主应用入口 (Streamlit)
├── environment.yml              # Conda 环境配置
├── pyproject.toml               # Python 项目配置
├── Makefile                     # 构建脚本
├── .env.example                 # 环境变量示例
│
├── semantic_model_generator/    # 核心生成逻辑
│   ├── data_processing/         # 数据处理工具
│   ├── protos/                  # Protocol Buffers 定义
│   ├── snowflake_utils/         # Snowflake 连接与 LLM 工具
│   └── validate/                # 模型验证逻辑
│
├── app_utils/                   # 应用工具
├── journeys/                    # 用户流程
├── partner/                     # Partner 集成 (dbt, Looker)
├── sis_setup/                   # Streamlit in Snowflake 部署脚本
└── images/                      # 图片资源
```

---

## 📌 功能特性

- ✅ **自动生成语义模型**：从 Snowflake 表/视图自动生成语义模型
- ✅ **AI 生成描述**：使用 LLM 自动生成字段描述
- ✅ **模型验证**：验证语义模型是否符合 Schema 规范
- ✅ **Partner 集成**：支持 dbt Semantic Model 和 Looker Explore
- ✅ **中国区支持**：支持通义千问、DeepSeek 等国产 LLM

---

## 🚀 快速开始

### Streamlit in Snowflake 部署（推荐）

```bash
# 1. 安装 Snowflake CLI
pip install snowflake-cli

# 2. 部署应用
snow sql -f sis_setup/app_setup.sql

# 3. 打开应用
snow streamlit get-url SEMANTIC_MODEL_GENERATOR --open \
    --database cortex_analyst_semantics \
    --schema semantic_model_generator
```

### 本地部署

```bash
# 1. 创建环境
conda env create -f environment.yml
conda activate semantic-model-generator

# 2. 配置环境变量
cp .env.example .env

# 3. 启动应用
streamlit run app.py
```

---

## 📚 相关项目

- [Snowflake-China (SPCS)](https://github.com/yuhenghub/Snowflake-China) - 中国区自托管 LLM 服务
- [cortex-agent-china](https://github.com/yuhenghub/cortex-agent-china) - Cortex Agent 中国区替代方案

---

## 📄 License

Apache 2.0 License

*基于 [Snowflake-Labs/semantic-model-generator](https://github.com/Snowflake-Labs/semantic-model-generator) 改编。*
