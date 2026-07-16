# 🏦 Enterprise Architecture: AI Agent for MSB Credit Applications

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/)
[![PlantUML](https://img.shields.io/badge/Diagrams-PlantUML-green.svg)](http://plantuml.com/)
[![Compliance](https://img.shields.io/badge/Compliance-152--FZ_%7C_CBR-orange.svg)]()
[![Architecture](https://img.shields.io/badge/Style-C4_Model-lightgrey.svg)]()

> Полное Архитектурное Решение (АР) для мультиагентной системы обработки кредитных заявок малого и среднего бизнеса (МСБ). Документ разработан в соответствии с корпоративными стандартами (УКП) и методологией AI-DISRUPT PDLC.

## 🎯 Цель проекта
Сокращение Lead Time обработки кредитной заявки МСБ с 5–7 дней до 4 часов (для 80% заявок) за счет внедрения мультиагентной оркестрации в контуре IDP с соблюдением 100% compliance (152-ФЗ, требования ЦБ РФ).

## 🏗 Ключевые архитектурные решения
* **Мультиагентная оркестрация:** Паттерн Orchestrator-Workers с изоляцией контекста и протоколом A2A для передачи фаз.
* **Безопасность и Compliance:** Policy Hook Bus (OPA Rego) для enforcement политик в реальном времени, эфемерные секреты через HashiCorp Vault, append-only audit с хранением 7 лет.
* **Интеграция:** Единый шлюз MCP (Model Context Protocol) для безопасного доступа агентов к корпоративным системам (АБС, БКИ, ФНС) и внешним API.
* **Управление автономией:** Адаптивная риск-ориентированная лестница разрешений (R0–R5), динамически пересчитываемая на основе триады: критичность × риск × сложность.

## 📊 Архитектурные диаграммы

### 1. Информационная архитектура (Потоки данных)
Описывает последовательность передачи данных от намерения (Intent Loop) к реализации (Implementation Loop).
![Информационная архитектура](./diagrams/info_architecture.png)


### 2. Системная архитектура (Сетевые взаимодействия)
Отражает физическое воплощение решения: сетевые сегменты (УКП LAN, DMZ, Cloud), namespaces в Kubernetes и протоколы взаимодействия (gRPC, mTLS, HTTPS).
![Системная архитектура](./diagrams/sys_architecture.png)


## 📚 Структура документа
Полный текст Архитектурного Решения, включая глоссарий, бизнес-архитектуру, требования к реализации, информационную безопасность и нефункциональные требования, доступен в папке `docs/`:
* 📄 [Architecture_Document.docx](./docs/Architecture_Document.docx)
* 📄 [Architecture_Document.md](./docs/Architecture_Document.md)

## 🛠 Технологический стек (Reference)
* **Оркестрация:** LangGraph, Temporal, Kafka
* **Интеграция:** MCP Proxy, LiteLLM
* **Данные:** PostgreSQL, Qdrant (RAG), Redis, S3
* **Безопасность:** Keycloak, HashiCorp Vault, OPA Rego

---
*Автор: Ганжа Илья*  
*Связь: https://hh.ru/resume/483458f9ff1036b39b0039ed1f34305434714d*