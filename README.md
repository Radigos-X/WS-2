# Прогнозирование вероятности покупок

Проект направлен на анализ поведения клиентов и построение модели для прогнозирования вероятности совершения покупки на основе данных о маркетинговых коммуникациях и истории покупок.

---

## 📋 Содержание

- [Описание проекта](#описание-проекта)
- [Данные](#данные)
- [Подход к решению](#подход-к-решению)
- [Результаты](#результаты)
- [Установка](#установка)
- [Использование](#использование)
- [Зависимости](#зависимости)
- [Контакты](#контакты)

---

## 🛠️ Описание проекта

Цель проекта — разработка модели для предсказания вероятности совершения покупки клиентом на основе:
- Истории взаимодействий с маркетинговыми коммуникациями.
- Истории покупок.
- Характеристик клиента и его активности.

---

## 📊 Данные

**Источники данных:**
- **apparel_messages.csv**: информация о взаимодействии клиента с рассылками (открытия, клики, каналы связи).
- **apparel_purchases.csv**: данные о покупках (сумма, количество, категории).
- **apparel_target_binary.csv**: целевая метка для прогнозирования (покупка/не покупка).

**Признаки:**
1. Агрегированные данные о покупках (сумма трат, уникальные категории, временные окна 30/60/90 дней).
2. Метрики взаимодействия с рассылками (количество отправленных, открытых и кликнутых сообщений).
3. Многомерные категориальные признаки товаров (multi-hot encoding).

---

## 🔍 Подход к решению

4. **Обработка данных:**
   - Удалены дубликаты и обработаны пропуски.
   - Выполнена агрегация данных по клиентам.

5. **Обучение моделей:**
   - Использованы следующие модели:
     - RandomForest
     - LightGBM
     - CatBoost
     - XGBoost
     - LogisticRegression
   - Настройка гиперпараметров с помощью GridSearchCV.
   - Обработка несбалансированного набора данных с использованием SMOTE.

6. **SHAP-анализ:**
   - Оценка важности признаков.
   - Исключены признаки с минимальным вкладом.

---

## 🚀 Результаты

- Лучшая модель: **RandomForest**.
- Метрика качества: **ROC-AUC = 0.8037** на тестовой выборке.
- Основные значимые признаки:
  - **days_since_last_message**: время с последнего взаимодействия.
  - **msgs_click_30d**: клики за последние 30 дней.
  - **total_purchases**: общее количество покупок.
  - **unique_categories**: количество уникальных категорий товаров.

---

## ⚙️ Установка

1. Склонируйте репозиторий:
   ```bash
   git clone https://github.com/your-repo-name.git
   cd your-repo-name```
2. Установите зависимости:
   ```
   pip install -r requirements.txt
   ```

---

## 📖 Использование

1. **Подготовка данных:**
    
    - Загрузите данные в формате CSV.
    - Выполните предварительную обработку данных.
2. **Обучение модели:**
    
    - Запустите скрипт `train_model.py` для обучения моделей и оптимизации гиперпараметров.
3. **Прогнозирование:**
    
    - Используйте модель для предсказания вероятности покупки на новых данных:
      ```from model import predict 
      predictions = predict(new_data)```

---

## 🛠️ Зависимости

- `pandas`
- `numpy`
- `scikit-learn`
- `lightgbm`
- `xgboost`
- `catboost`
- `shap`

Установите их с помощью команды:
   ```
   pip install -r requirements.txt
   ```

---

## 📬 Контакты

Если у вас есть вопросы, пожалуйста, свяжитесь со мной:

- Email: i@outis-x.ru
- GitHub: [github.com/Radigos-X](https://github.com/Radigos-X)
