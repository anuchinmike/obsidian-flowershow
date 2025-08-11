# Задача: Создание структуры услуг на сайте berloga.vet

## 🎯 **Цель задачи**

Пересоздать текущие страницы услуг в виде кастомного типа записей (CPT) для улучшения структуры сайта и SEO-оптимизации.

## 📋 **Описание задачи**

### **Текущее состояние:**

- Существующие страницы услуг созданы как обычные страницы WordPress
- Кастомный тип записей 'services' уже создан, но требует редактирования
- Необходимо перенести контент и SEO-данные без потерь

### **Требуемый результат:**

- Все услуги переведены в CPT 'services'
- Сохранены все URL-адреса и мета-теги для SEO
- Улучшена структура и управление контентом
- Интеграция с системой цен и категорий

## 🔧 **Технические требования**

### **Кастомный тип записей 'services':**

- **Slug:** `service`
- **Таксономия:** `service_category` (иерархическая)
- **Поддержка:** Featured Image, Excerpt, Custom Fields

### **Кастомные поля (требуют анализа и редактирования):**

- `service_duration` - продолжительность услуги
- `service_preparation` - подготовка к приему
- `service_contraindications` - противопоказания
- `service_equipment` - используемое оборудование
- `service_primary_price` - основная цена
- `service_repeat_price` - цена повторного приема
- `service_complex_price` - цена комплексного приема
- `service_discount_info` - информация о скидках
- `service_price_category` - связь с CPT 'prices'

## 📊 **SEO-требования**

### **Критически важно:**

- Сохранение всех канонических URL-адресов
- Перенос title и description без изменений
- Сохранение внутренних ссылок
- Поддержка структурированных данных

### **Мета-данные для переноса:**

- Canonical URL
- Title tag
- Meta description
- Open Graph теги
- Schema.org разметка

## 🛠️ **Этапы выполнения**

### **1. Анализ текущего CPT 'services'**

- ✅ Проверены все поля в админке WordPress
- ✅ Определены типы полей (text, textarea, select, etc.)
- ✅ Выявлены недостающие SEO-поля

### **2. Подготовка списка страниц услуг**

- ✅ Собран список всех URL услуг
- ⏳ Требуется извлечь title и description
- ⏳ Определить структуру контента

### **3. Редактирование CPT**

- ⏳ Составить список изменений CPT
- ⏳ Определить новые SEO-поля
- ⏳ Планировать миграцию данных

### **4. Перенос контента**

- [ ] Создать записи CPT для каждой услуги
- [ ] Перенести контент и мета-данные
- [ ] Настроить редиректы

### **5. Тестирование**

- [ ] Проверить все URL
- [ ] Валидировать SEO-данные
- [ ] Тестировать функциональность

## 📋 **Анализ существующего CPT 'services'**

### **Основные поля CPT:**

- `post_title` - название услуги
- `post_content` - описание услуги
- `post_excerpt` - краткое описание
- `featured_image` - изображение услуги

#### **Детали услуги (meta box):**

- `_service_duration` - продолжительность процедуры (text)
- `_service_preparation` - подготовка к процедуре (textarea)
- `_service_contraindications` - противопоказания (textarea)
- `_service_equipment` - используемое оборудование (textarea)

#### **Цены и тарифы (meta box):**

- `_service_price_primary` - первичный прием (text)
- `_service_price_repeat` - повторный прием (text)
- `_service_price_complex` - комплексная услуга (text)
- `_service_discount_info` - информация о скидках (textarea)
- `service_price_category` - категория цен (select)

#### **Рекомендуемый специалист (meta box):**

- `_service_doctor_name` - имя врача (text)
- `_service_doctor_specialization` - специализация (text)
- `_service_doctor_experience` - опыт работы (text)
- `_service_doctor_link` - ссылка на страницу врача (url)

### **Таксономии:**

- `service_category` - категории услуг (иерархическая)

### **SEO-поля (ОТСУТСТВУЮТ - требуют добавления):**

- `seo_title` - кастомный title
- `seo_description` - кастомный description
- `seo_canonical` - канонический URL
- `seo_keywords` - ключевые слова

## 📊 **Список страниц услуг для переноса**

### **Каталог услуг:**

- **URL:** https://berloga.vet/uslugi/
- **Тип:** Страница-каталог

### **Отдельные страницы услуг:**

| № | URL | Название услуги | Статус |
|---|-----|----------------|--------|
| 1 | https://berloga.vet/akusherstvo-i-ginekologiya/ | Акушерство и гинекология | Требует переноса |
| 2 | https://berloga.vet/veterinar-ortoped-travmatolog/ | Ветеринар ортопед травматолог | Требует переноса |
| 3 | https://berloga.vet/gastroenterologiya/ | Гастроэнтерология | Требует переноса |
| 4 | https://berloga.vet/laboratornaya-diagnostika/ | Лабораторная диагностика | Требует переноса |
| 5 | https://berloga.vet/terapija/ | Терапия | Требует переноса |
| 6 | https://berloga.vet/veterinarnyj-kardiolog-kardiologiya-dlya-sobak-i-koshek/ | Ветеринарный кардиолог | Требует переноса |
| 7 | https://berloga.vet/stomatologiya/ | Стоматология | Требует переноса |
| 8 | https://berloga.vet/xirurgiya/ | Хирургия | Требует переноса |
| 9 | https://berloga.vet/diagnosticheskaya-laparotomiya-u-koshek-i-sobak/ | Диагностическая лапаротомия | Требует переноса |
| 10 | https://berloga.vet/dnevnoj-stacionar-dlya-zhivotnyx/ | Дневной стационар | Требует переноса |
| 11 | https://berloga.vet/izmerenie-davleniya-u-koshek-i-sobak/ | Измерение давления | Требует переноса |
| 12 | https://berloga.vet/kastracija-i-sterilizacija/ | Кастрация и стерилизация | Требует переноса |
| 13 | https://berloga.vet/kastraciya-kota/ | Кастрация кота | Требует переноса |
| 14 | https://berloga.vet/kastraciya-sobaki-kobelya/ | Кастрация собаки кобеля | Требует переноса |
| 15 | https://berloga.vet/kesarevo-sechenie/ | Кесарево сечение | Требует переноса |
| 16 | https://berloga.vet/konsultaciya-veterinara/ | Консультация ветеринара | Требует переноса |
| 17 | https://berloga.vet/onkologiya/ | Онкология | Требует переноса |
| 18 | https://berloga.vet/lechenie-piometry/ | Лечение пиометры | Требует переноса |
| 19 | https://berloga.vet/nefrologiya-veterinar-nefrolog/ | Нефрология | Требует переноса |
| 20 | https://berloga.vet/obrabotka-i-snyatie-shvov-u-zhivotnyh/ | Обработка и снятие швов | Требует переноса |
| 21 | https://berloga.vet/osteosintez-u-zhivotnyh/ | Остеосинтез | Требует переноса |
| 22 | https://berloga.vet/rentgen/ | Рентген | Требует переноса |
| 23 | https://berloga.vet/sterilizaciya-domashnix-zhivotnyx/ | Стерилизация домашних животных | Требует переноса |
| 24 | https://berloga.vet/sterilizaciya-koshek/ | Стерилизация кошек | Требует переноса |
| 25 | https://berloga.vet/sterilizaciya-sobak/ | Стерилизация собак | Требует переноса |
| 26 | https://berloga.vet/strizhka-kogtej/ | Стрижка когтей | Требует переноса |
| 27 | https://berloga.vet/ultrazvukovoe-issledovanie/ | Ультразвуковое исследование | Требует переноса |
| 28 | https://berloga.vet/uslugi/vakcinaciya/ | Вакцинация | Требует переноса |
| 29 | https://berloga.vet/uslugi/dermatologiya/ | Дерматология | Требует переноса |
| 30 | https://berloga.vet/obrabotka-ran-ekzemy-vskrytie-abscessa/ | Обработка ран, экземы, вскрытие абсцесса | Требует переноса |
| 31 | https://berloga.vet/check-up-dlya-sobak-i-koshek/ | Check-up для собак и кошек | Требует переноса |
| 32 | https://berloga.vet/chipirovanie-sobak-i-koshek/ | Чипирование собак и кошек | Требует переноса |
| 33 | https://berloga.vet/evtanaziya-i-kremaciya/ | Эвтаназия и кремация | Требует переноса |

**Всего страниц для переноса: 33**

## 🔍 **Необходимый анализ**

### **1. Анализ существующего CPT:**

- ✅ Проверены все поля в админке WordPress
- ✅ Определены типы полей (text, textarea, select, etc.)
- ✅ Выявлены недостающие SEO-поля

### **2. Анализ страниц услуг:**

- ✅ Собран список всех URL услуг
- ⏳ Требуется извлечь title и description
- ⏳ Определить структуру контента

### **3. Планирование редактирования:**

- ⏳ Составить список изменений CPT
- ⏳ Определить новые SEO-поля
- ⏳ Планировать миграцию данных

## 📊 **Ожидаемые результаты**

### **После выполнения:**

- ✅ Все услуги в единой структуре CPT
- ✅ Сохранены все SEO-параметры
- ✅ Улучшена управляемость контентом
- ✅ Интеграция с системой цен
- ✅ Готовность к дальнейшему развитию

### **Метрики успеха:**

- Сохранение всех URL без изменений
- Отсутствие ошибок 404
- Сохранение позиций в поисковой выдаче
- Улучшение структуры сайта

---

**Статус:** Требует анализа и планирования  
**Приоритет:** Высокий  
**Сроки:** После анализа существующего CPT

---

## 📋 **Таблица для анализа SEO-данных страниц услуг**

### **Задача:** Собрать title и description для каждой страницы услуги

| № | URL | Название услуги | Title (требует заполнения) | Description (требует заполнения) | Статус |
|---|-----|----------------|---------------------------|----------------------------------|--------|
| 1 | https://berloga.vet/akusherstvo-i-ginekologiya/ | Акушерство и гинекология | | | ⏳ Требует анализа |
| 2 | https://berloga.vet/veterinar-ortoped-travmatolog/ | Ветеринар ортопед травматолог | | | ⏳ Требует анализа |
| 3 | https://berloga.vet/gastroenterologiya/ | Гастроэнтерология | | | ⏳ Требует анализа |
| 4 | https://berloga.vet/laboratornaya-diagnostika/ | Лабораторная диагностика | | | ⏳ Требует анализа |
| 5 | https://berloga.vet/terapija/ | Терапия | | | ⏳ Требует анализа |
| 6 | https://berloga.vet/veterinarnyj-kardiolog-kardiologiya-dlya-sobak-i-koshek/ | Ветеринарный кардиолог | | | ⏳ Требует анализа |
| 7 | https://berloga.vet/stomatologiya/ | Стоматология | | | ⏳ Требует анализа |
| 8 | https://berloga.vet/xirurgiya/ | Хирургия | | | ⏳ Требует анализа |
| 9 | https://berloga.vet/diagnosticheskaya-laparotomiya-u-koshek-i-sobak/ | Диагностическая лапаротомия | | | ⏳ Требует анализа |
| 10 | https://berloga.vet/dnevnoj-stacionar-dlya-zhivotnyx/ | Дневной стационар | | | ⏳ Требует анализа |
| 11 | https://berloga.vet/izmerenie-davleniya-u-koshek-i-sobak/ | Измерение давления | | | ⏳ Требует анализа |
| 12 | https://berloga.vet/kastracija-i-sterilizacija/ | Кастрация и стерилизация | | | ⏳ Требует анализа |
| 13 | https://berloga.vet/kastraciya-kota/ | Кастрация кота | | | ⏳ Требует анализа |
| 14 | https://berloga.vet/kastraciya-sobaki-kobelya/ | Кастрация собаки кобеля | | | ⏳ Требует анализа |
| 15 | https://berloga.vet/kesarevo-sechenie/ | Кесарево сечение | | | ⏳ Требует анализа |
| 16 | https://berloga.vet/konsultaciya-veterinara/ | Консультация ветеринара | | | ⏳ Требует анализа |
| 17 | https://berloga.vet/onkologiya/ | Онкология | | | ⏳ Требует анализа |
| 18 | https://berloga.vet/lechenie-piometry/ | Лечение пиометры | | | ⏳ Требует анализа |
| 19 | https://berloga.vet/nefrologiya-veterinar-nefrolog/ | Нефрология | | | ⏳ Требует анализа |
| 20 | https://berloga.vet/obrabotka-i-snyatie-shvov-u-zhivotnyh/ | Обработка и снятие швов | | | ⏳ Требует анализа |
| 21 | https://berloga.vet/osteosintez-u-zhivotnyh/ | Остеосинтез | | | ⏳ Требует анализа |
| 22 | https://berloga.vet/rentgen/ | Рентген | | | ⏳ Требует анализа |
| 23 | https://berloga.vet/sterilizaciya-domashnix-zhivotnyx/ | Стерилизация домашних животных | | | ⏳ Требует анализа |
| 24 | https://berloga.vet/sterilizaciya-koshek/ | Стерилизация кошек | | | ⏳ Требует анализа |
| 25 | https://berloga.vet/sterilizaciya-sobak/ | Стерилизация собак | | | ⏳ Требует анализа |
| 26 | https://berloga.vet/strizhka-kogtej/ | Стрижка когтей | | | ⏳ Требует анализа |
| 27 | https://berloga.vet/ultrazvukovoe-issledovanie/ | Ультразвуковое исследование | | | ⏳ Требует анализа |
| 28 | https://berloga.vet/uslugi/vakcinaciya/ | Вакцинация | | | ⏳ Требует анализа |
| 29 | https://berloga.vet/uslugi/dermatologiya/ | Дерматология | | | ⏳ Требует анализа |
| 30 | https://berloga.vet/obrabotka-ran-ekzemy-vskrytie-abscessa/ | Обработка ран, экземы, вскрытие абсцесса | | | ⏳ Требует анализа |
| 31 | https://berloga.vet/check-up-dlya-sobak-i-koshek/ | Check-up для собак и кошек | | | ⏳ Требует анализа |
| 32 | https://berloga.vet/chipirovanie-sobak-i-koshek/ | Чипирование собак и кошек | | | ⏳ Требует анализа |
| 33 | https://berloga.vet/evtanaziya-i-kremaciya/ | Эвтаназия и кремация | | | ⏳ Требует анализа |

### **Инструкции по заполнению:**

1. **Title** - извлечь из `<title>` тега страницы
2. **Description** - извлечь из `<meta name="description">` тега
3. **Статус** - отметить как "✅ Заполнено" после извлечения данных

### **Цель:** Сохранить все SEO-данные при переносе в CPT для предотвращения потери позиций в поисковой выдаче.