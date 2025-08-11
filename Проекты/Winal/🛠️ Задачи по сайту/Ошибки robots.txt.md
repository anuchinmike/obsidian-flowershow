---
title: Ошибки robots.txt
created: 2025-07-09
modified: 2025-07-23
status: completed
tags:
  - winal
  - winal-задачи-сайт
  - winal-техническое-обслуживание
aliases:
---
## Формулировка проблемы:

![[Pasted image 20250723141238.png]]


**Выявленная проблема:** Текущий файл robots.txt содержал только базовые блокировки WordPress директорий, но не учитывал современные SEO-требования. Из-за этого поисковые роботы индексировали множество дублей страниц с GET-параметрами (UTM-метки, рекламные параметры), что привело к критической ошибке в Яндекс.Вебмастере "Найдены страницы-дубликаты с GET-параметрами".

## Принятое решение

**Создан оптимизированный robots.txt** с современными настройками:

- **Заблокированы все GET-параметры**, создающие дубли (utm_source, gclid, yclid, fbclid и др.)
    
- **Усилена защита системных файлов** WordPress
    
- **Добавлены разрешения** для важных ресурсов (CSS, JS, изображения)
    
- **Настроена скорость сканирования** для снижения нагрузки на сервер
    
- **Заблокированы агрессивные боты** и технические страницы
    

**Результат:** Поисковые роботы перестанут индексировать дубли страниц, что решит критическую ошибку в Яндекс.Вебмастере и оптимизирует расход краулингового бюджета на важные страницы сайта.

## Новое содержание файла robots.txt

```
# ========================================
# ROBOTS.TXT для WordPress сайта winal.ru
# Последнее обновление: 23.07.2025
# ========================================

# Основная директива для всех поисковых роботов
User-agent: *

# ========================================
# БЛОКИРОВКА СИСТЕМНЫХ ДИРЕКТОРИЙ WORDPRESS
# ========================================

# Административная панель (критично для безопасности)
Disallow: /wp-admin/
# Исключение: AJAX-запросы нужны для корректной работы фронтенда
Allow: /wp-admin/admin-ajax.php

# Системные директории WordPress
Disallow: /wp-includes/          # Ядро WP, не индексируется
Disallow: /wp-content/plugins/   # Файлы плагинов (уязвимости)
Disallow: /wp-content/themes/    # Исходники тем
Disallow: /wp-content/cache/     # Кеш файлы
Disallow: /wp-content/upgrade/   # Временные файлы обновлений

# ========================================
# БЛОКИРОВКА ТЕХНИЧЕСКИХ ФАЙЛОВ
# ========================================

# Конфигурационные и служебные файлы
Disallow: /wp-config.php
Disallow: /readme.html
Disallow: /license.txt
Disallow: /wp-trackback.php
Disallow: /wp-comments-post.php
Disallow: /xmlrpc.php            # Защита от брутфорса

# Временные и логи
Disallow: /wp-content/debug.log
Disallow: /error_log
Disallow: /*.log$

# ========================================
# РЕШЕНИЕ ПРОБЛЕМЫ ДУБЛИКАТОВ (GET-ПАРАМЕТРЫ)
# ========================================

# UTM-метки и рекламные параметры
Disallow: /*?*utm_source=*       # Google Analytics UTM
Disallow: /*?*utm_medium=*
Disallow: /*?*utm_campaign=*
Disallow: /*?*utm_term=*
Disallow: /*?*utm_content=*

# Яндекс.Директ и рекламные системы
Disallow: /*?*yclid=*           # Яндекс.Директ
Disallow: /*?*gclid=*           # Google Ads
Disallow: /*?*fbclid=*          # Facebook
Disallow: /*?*msclkid=*         # Microsoft Advertising

# Социальные сети и трекинг
Disallow: /*?*ref=*             # Referrer параметры
Disallow: /*?*source=*          # Источники трафика
Disallow: /*?*campaign=*        # Кампании
Disallow: /*?*medium=*          # Медиум
Disallow: /*?*sm_pkey=*         # Social media keys

# Технические параметры
Disallow: /*?*v=*               # Версионность
Disallow: /*?*ver=*             # Версии файлов
Disallow: /*?*_ga=*             # Google Analytics
Disallow: /*?*_gl=*             # Google Linker
Disallow: /*?*mc_eid=*          # MailChimp
Disallow: /*?*_ke=*             # Klaviyo

# ========================================
# БЛОКИРОВКА ДУБЛЕЙ КОНТЕНТА
# ========================================

# Фиды и RSS (если не нужны в поиске)
Disallow: /feed/
Disallow: /*/feed/
Disallow: /comments/feed/
Disallow: /*/*/feed/
Disallow: /*/*/*/feed/

# Страницы поиска и фильтрации
Disallow: /?s=*                 # Результаты поиска
Disallow: /search/              # Альтернативные URL поиска
Disallow: /*?search=*           # GET-поиск

# Пагинация в GET-параметрах (если используется)
Disallow: /*?page=*
Disallow: /*?paged=*

# ========================================
# СПЕЦИФИЧНЫЕ БЛОКИРОВКИ ДЛЯ WINAL.RU
# ========================================

# Существующие блокировки из текущего файла
Disallow: /wp-content/uploads/wpo/wpo-plugins-tables-list.json

# Дополнительные блокировки для оптимизации производительности
Disallow: /wp-content/uploads/*/cache/
Disallow: /wp-content/uploads/*/logs/

# ========================================
# РАЗРЕШЕНИЯ (ВАЖНЫЕ ИСКЛЮЧЕНИЯ)
# ========================================

# CSS и JS файлы тем (нужны для правильного рендеринга)
Allow: /wp-content/themes/*.css
Allow: /wp-content/themes/*.js
Allow: /wp-includes/*.css
Allow: /wp-includes/*.js

# Изображения и медиафайлы
Allow: /wp-content/uploads/*.jpg
Allow: /wp-content/uploads/*.jpeg
Allow: /wp-content/uploads/*.png
Allow: /wp-content/uploads/*.gif
Allow: /wp-content/uploads/*.webp
Allow: /wp-content/uploads/*.svg
Allow: /wp-content/uploads/*.pdf

# ========================================
# НАСТРОЙКИ ДЛЯ СПЕЦИФИЧНЫХ БОТОВ
# ========================================

# Yandex bot (дополнительные ограничения) 
User-agent: Yandex 

# Ограничиваем скорость сканирования (1 запрос в 2 секунды) 
Crawl-delay: 2 

# Наследуем все блокировки выше 
Disallow: /wp-admin/ Allow: /wp-admin/admin-ajax.php 

# Google bot (стандартные настройки) 
User-agent: Googlebot 

# Наследует основные правила 
User-agent: * 

# Блокировка агрессивных ботов 

User-agent: AhrefsBot 
Disallow: / 

User-agent: MJ12bot 
Disallow: / 

# ======================================== 
# КАРТА САЙТА 
# ======================================== 

# Основная карта сайта (обязательно в конце файла) 
Sitemap: https://winal.ru/sitemap_index.xml 

# ======================================== 
# ДОПОЛНИТЕЛЬНАЯ ИНФОРМАЦИЯ 
# ======================================== 
# Этот robots.txt создан для решения проблем: 
# 1. Критических дубликатов с GET-параметрами 
# 2. Оптимизации краулингового бюджета 
# 3. Защиты системных файлов WordPress 
# 4. Улучшения индексации важного контента

```