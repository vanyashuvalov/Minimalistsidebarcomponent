# 🚀 Инструкция по деплою на GitHub Pages

## Метод 1: Автоматический деплой через GitHub Actions (рекомендуется)

### Шаг 1: Настройка репозитория

1. Создайте репозиторий на GitHub (если еще не создали)
2. Пушьте код в репозиторий:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/ваш-username/название-репозитория.git
git push -u origin main
```

### Шаг 2: Включите GitHub Pages

1. Откройте репозиторий на GitHub
2. Перейдите в **Settings** (Настройки)
3. В левом меню выберите **Pages**
4. В разделе **Source** (Источник) выберите **GitHub Actions**

### Шаг 3: Деплой

После настройки каждый пуш в ветку `main` будет автоматически собирать и деплоить ваше приложение!

```bash
git add .
git commit -m "Update app"
git push origin main
```

### Проверка деплоя

1. Перейдите во вкладку **Actions** в вашем репозитории
2. Дождитесь завершения workflow "Deploy to GitHub Pages" (обычно 1-2 минуты)
3. После успешного завершения сайт будет доступен по адресу:
   ```
   https://ваш-username.github.io/название-репозитория/
   ```

---

## Метод 2: Ручной деплой через gh-pages

### Шаг 1: Установите зависимости

```bash
npm install
```

### Шаг 2: Обновите vite.config.ts

Откройте `vite.config.ts` и измените строку `base`:

```typescript
export default defineConfig({
  // Замените 'your-repo-name' на название вашего репозитория
  base: '/название-вашего-репозитория/',
  // ... остальные настройки
});
```

### Шаг 3: Деплой

```bash
npm run deploy
```

Эта команда:
1. Соберет проект (`npm run build`)
2. Опубликует содержимое папки `dist` в ветку `gh-pages`

### Шаг 4: Настройте GitHub Pages

1. Откройте **Settings** → **Pages**
2. В разделе **Source** выберите ветку **gh-pages**
3. Корневую директорию оставьте **/ (root)**
4. Нажмите **Save**

Сайт будет доступен через несколько минут по адресу:
```
https://ваш-username.github.io/название-репозитория/
```

---

## 🛠️ Локальная разработка

### Запуск dev-сервера

```bash
npm run dev
```

Откроется http://localhost:3000

### Сборка для продакшена

```bash
npm run build
```

### Предпросмотр production-сборки

```bash
npm run preview
```

---

## 📋 Чек-лист перед деплоем

- [ ] Все зависимости установлены (`npm install`)
- [ ] Проект собирается без ошибок (`npm run build`)
- [ ] Файл `.nojekyll` находится в корне проекта
- [ ] В `vite.config.ts` настроен правильный `base` path
- [ ] GitHub Pages включен в настройках репозитория
- [ ] (Для метода 1) В Settings → Pages выбран источник "GitHub Actions"
- [ ] (Для метода 2) В Settings → Pages выбрана ветка "gh-pages"

---

## 🔧 Решение проблем

### Сайт не загружается / показывает 404

1. **Проверьте `base` в vite.config.ts:**
   - Для автоматического деплоя используйте: `base: './'`
   - Для ручного деплоя используйте: `base: '/название-репозитория/'`

2. **Убедитесь, что файл `.nojekyll` существует**

3. **Проверьте настройки GitHub Pages** (Settings → Pages)

### CSS не загружается

1. Проверьте в DevTools (F12) пути к файлам CSS
2. Убедитесь, что `base` path настроен правильно в `vite.config.ts`

### JavaScript ошибки

1. Проверьте консоль браузера (F12)
2. Убедитесь, что все зависимости установлены
3. Попробуйте локально: `npm run build && npm run preview`

### Изменения не отображаются

1. Очистите кеш браузера (Ctrl+Shift+R или Cmd+Shift+R)
2. Дождитесь завершения GitHub Actions (если используете метод 1)
3. GitHub Pages может обновляться с задержкой до 5-10 минут

---

## 🎯 Дополнительные настройки

### Пользовательский домен

1. Создайте файл `public/CNAME` с вашим доменом:
   ```
   your-domain.com
   ```

2. Настройте DNS записи у вашего регистратора домена
3. Подробнее: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

### Оптимизация производительности

Проект уже оптимизирован:
- ✅ Минификация кода
- ✅ Tree shaking
- ✅ Code splitting
- ✅ Удаление console.log
- ✅ Compression

---

## 📚 Полезные ссылки

- [GitHub Pages документация](https://docs.github.com/en/pages)
- [GitHub Actions документация](https://docs.github.com/en/actions)
- [Vite документация](https://vitejs.dev/)
- [Tailwind CSS документация](https://tailwindcss.com/)

---

## 💡 Совет

Рекомендуем использовать **Метод 1 (GitHub Actions)**, так как он:
- Автоматизирован
- Не требует настройки base path для конкретного репозитория
- Проще в поддержке
- Автоматически обновляется при каждом пуше
