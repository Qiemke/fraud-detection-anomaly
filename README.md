# 🛡️ Обнаружение аномалий и фрод-детекция в транзакциях

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-latest-orange?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-latest-green?logo=xgboost&logoColor=white)](https://xgboost.readthedocs.io/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **Проект №133** в рамках курса/программы [Название программы, если есть].
> Построение модели обнаружения аномальных и мошеннических транзакций в потоке данных.

---

## 📋 О проекте

**Проблема:** Часть транзакций являются мошенническими. Их пропуск ведет к прямым финансовым потерям, а ложные срабатывания раздражают добросовестных клиентов и снижают лояльность.

**Цель:** Разработать и протестировать модель машинного обучения для выявления аномалий и фрода в режиме реального времени (online).

**Тип задачи:** Anomaly Detection, крайне несбалансированная классификация.

**Уровень сложности:** BASE / MIDDLE

### 📊 Данные
В работе используются открытые датасеты:
*   [Credit Card Fraud Detection (ULB, Kaggle)](https://www.kaggle.com/mlg-ulb/creditcardfraud)
*   [IEEE-CIS Fraud Detection (Kaggle)](https://www.kaggle.com/c/ieee-fraud-detection)

### 🛠 Методы и инструменты
*   **Unsupervised:** Isolation Forest, One-Class SVM, Local Outlier Factor (LOF).
*   **Supervised:** XGBoost с балансировкой классов (class weighting).
*   **Метрики:** PR-AUC (приоритет при сильном дисбалансе), Recall при фиксированном Precision.
*   **Усложнения:** Потоковое (online) обнаружение, объяснение решений модели для комплаенса.

---

## 👥 Команда проекта

| Роль | Участник | Контакты |
| :--- | :--- | :--- |
| **Руководитель** | Архипов Максим | [@username](https://github.com/username) |
| **Участник 1** | [Имя Фамилия] | [@username](https://github.com/username) |
| **Участник 2** | [Имя Фамилия] | [@username](https://github.com/username) |
| **Участник 3** | [Имя Фамилия] | [@username](https://github.com/username) |

> *Примечание: Руководители проекта также указаны в исходном задании: Мовсумов Денис, Архипов Максим, Александр Голубев.*

---

## 🗺 План работы (Roadmap)

- [ ] **Этап 1: EDA и анализ данных**
  - Изучение дисбаланса классов.
  - Анализ типов аномалий в транзакциях.
- [ ] **Этап 2: Unsupervised Baseline**
  - Построение базовой модели (Isolation Forest).
  - Оценка качества без учителя.
- [ ] **Этап 3: Supervised модель**
  - Обучение модели с балансировкой классов (XGBoost).
  - Подбор гиперпараметров.
- [ ] **Этап 4: Настройка порога и анализ ошибок**
  - Подбор порога под целевой Precision/Recall.
  - Анализ ложных срабатываний (False Positives).
- [ ] **Этап 5: Интеграция и мониторинг**
  - Описание процесса интеграции модели в мониторинг.
  - Тестирование устойчивости к [укажите факторы, например, дрейфу данных].

---

## 📈 Критерии приемки

*   Модель достигает целевого **Recall** при заданном уровне **Precision** (или **PR-AUC** выше baseline).
*   Протестирована устойчивость к [условие из задания, например, к изменению распределения данных].

---

## 📂 Структура репозитория (примерная)

```text
.
├── data/               # Данные (или ссылки на них)
├── notebooks/          # Jupyter ноутбуки с EDA и экспериментами
├── src/                # Исходный код (скрипты обучения, инференса)
│   ├── models/
│   └── utils/
├── requirements.txt    # Зависимости проекта
└── README.md           # Этот файл
