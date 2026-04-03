# Sidebar Dashboard Application

Современное веб-приложение с адаптивным сайдбаром, построенное на React, TypeScript и Tailwind CSS.

## 🚀 Деплой на GitHub Pages

### Автоматический деплой (рекомендуется)

1. **Включите GitHub Pages в настройках репозитория:**
   - Откройте Settings → Pages
   - В разделе "Source" выберите "GitHub Actions"

2. **Пушьте код в main ветку:**
   ```bash
   git add .
   git commit -m "Deploy to GitHub Pages"
   git push origin main
   ```

3. **GitHub Actions автоматически соберет и задеплоит приложение**
   - Проверьте статус в разделе Actions
   - После завершения сайт будет доступен по адресу: `https://ваш-username.github.io/название-репозитория/`

### Ручной деплой

Если хотите использовать ручной деплой через gh-pages:

1. **Установите зависимости:**
   ```bash
   npm install
   ```

2. **Соберите и задеплойте:**
   ```bash
   npm run deploy
   ```

## 🛠️ Разработка

### Установка

```bash
npm install
```

### Запуск локального сервера

```bash
npm run dev
```

Приложение откроется по адресу http://localhost:3000

### Сборка для продакшена

```bash
npm run build
```

Собранные файлы будут в папке `dist/`

### Предпросмотр production-сборки

```bash
npm run preview
```

## 📦 Оптимизации

- ✅ Минификация кода с помощью Terser
- ✅ Удаление console.log в продакшене
- ✅ Code splitting для vendor библиотек
- ✅ Относительные пути для корректной работы на GitHub Pages
- ✅ Optimized chunks для лучшего кеширования
- ✅ Source maps отключены в production для уменьшения размера

## 🎨 Возможности

- Адаптивный сайдбар с анимациями
- Динамический контент для разных секций
- Темная тема
- Раскрывающиеся меню
- Поиск
- Множество иконок Carbon Design System

## 📁 Структура проекта

```
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions для автодеплоя
├── components/
│   ├── SidebarDemo.tsx         # Основной компонент сайдбара
│   └── ui/                     # UI компоненты
├── imports/                    # SVG и другие импортированные ресурсы
├── styles/
│   └── globals.css             # Глобальные стили
├── App.tsx                     # Главный компонент
├── vite.config.ts              # Конфигурация Vite
└── package.json                # Зависимости и скрипты
```

## 🔧 Технологии

- React 18
- TypeScript
- Tailwind CSS v4
- Vite
- Carbon Icons React
- GitHub Pages

## 📝 Примечания

- При использовании GitHub Actions убедитесь, что в Settings → Pages выбран источник "GitHub Actions"
- Файл `.nojekyll` предотвращает обработку Jekyll на GitHub Pages
- Base path настроен как относительный (`./`) для корректной работы в любом репозитории

## 📄 Лицензия

MIT
