# 🛡️ Обнаружение аномалий и фрод-детекция в транзакциях

[![Python](https://img.shields.io/badge/Python-3.10.4-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Poetry](https://img.shields.io/badge/Poetry-managed-60A5FA?logo=poetry&logoColor=white)](https://python-poetry.org/)
[![DVC](https://img.shields.io/badge/DVC-data%20versioning-945DD6?logo=dvc&logoColor=white)](https://dvc.org/)
[![MLflow](https://img.shields.io/badge/MLflow-tracking-0194E2?logo=mlflow&logoColor=white)](https://mlflow.org/)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![flake8](https://img.shields.io/badge/lint-flake8-yellow.svg)](https://flake8.pycqa.org/)

> **Проект №133** — Обнаружение аномалий / фрод-детекция в рамках курса программы Искусственный интеллект НИУ ВШЭ.
> Построение модели обнаружения аномальных и мошеннических транзакций в потоке данных.

---

## 📋 О проекте

**Проблема:** Часть транзакций являются мошенническими. Их пропуск ведет к прямым финансовым потерям, а ложные срабатывания раздражают добросовестных клиентов и снижают лояльность.

**Цель:** Разработать и протестировать модель машинного обучения для выявления аномалий и фрода в режиме реального времени (online).

**Тип задачи:** Anomaly Detection, крайне несбалансированная классификация.

**Уровень сложности:** BASE / MIDDLE

### 📊 Данные
В работе используются открытые датасеты:
*   [IEEE-CIS Fraud Detection (Kaggle)](https://www.kaggle.com/c/ieee-fraud-detection)

### 🎯 Метрики качества
*   **PR-AUC** — приоритетная метрика при сильном дисбалансе классов.
*   **Recall** при фиксированном уровне **Precision**.

---

## 👥 Команда проекта

| Роль | Участник | Telegram | GitHub |
| :--- | :--- | :--- | :--- |
| **Куратор** | Архипов Максим  | [@pirici_pip](https://t.me/pirici_pip) | |
| **Участник 1** | Кадыков Вадим | [@Junialay](https://t.me/Junialay) | [@Qiemke](https://github.com/Qiemke) |
| **Участник 2** | Титов Артём | [@artem_titoff](https://t.me/artem_titoff) | [@Artyom321](https://github.com/Artyom321) |
| **Участник 3** | Боханов Данила | [@Dansdfsdh](https://t.me/Dansdfsdh) | [@danilabohanov](https://github.com/danilabohanov) |

---

## 🗺 План работы

- [ ] **Этап 1: EDA и анализ данных**
  - Изучение дисбаланса классов.
  - Анализ типов аномалий в транзакциях.
- [ ] **Этап 2: Unsupervised Baseline**
  - Построение базовой модели (Isolation Forest, One-Class SVM, LOF).
- [ ] **Этап 3: Supervised модель**
  - Обучение модели с балансировкой классов (XGBoost / CatBoost).
  - Подбор гиперпараметров.
- [ ] **Этап 4: Настройка порога и анализ ошибок**
  - Подбор порога под целевой Precision/Recall.
  - Анализ ложных срабатываний (False Positives).
- [ ] **Этап 5: Поднятие сервиса**
  - Делаем сервис с потоковой обработкой данных.
- [ ] **Этап 6: Тестирование и мониторинг**
  - Интеграция модели в мониторинг (MLflow).
  - Тестирование устойчивости к дрейфу данных.

---

## 📈 Критерии приемки

*   Модель достигает целевого **Recall** при заданном уровне **Precision** (или **PR-AUC** выше baseline).
*   Протестирована на устойчивость к дисбалансу классов.
*   Описан процесс принятия решения (порог, объяснение флагов) для интеграции в процесс проверки.

