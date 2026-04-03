# ⚡ Быстрый старт - Деплой за 2 минуты

## 🚀 Самый быстрый способ

### 1. Создайте репозиторий на GitHub

```bash
# Инициализация Git (если еще не инициализирован)
git init

# Добавьте все файлы
git add .

# Создайте первый коммит
git commit -m "Initial commit: sidebar dashboard app"

# Переименуйте ветку в main
git branch -M main

# Добавьте remote (замените URL на ваш)
git remote add origin https://github.com/USERNAME/REPO-NAME.git

# Запушьте код
git push -u origin main
```

### 2. Включите GitHub Pages

1. Откройте ваш репозиторий на GitHub
2. Нажмите **Settings** (⚙️)
3. В меню слева выберите **Pages**
4. В разделе **Source** выберите **GitHub Actions**
5. Готово! 🎉

### 3. Подождите ~2 минуты

- Перейдите во вкладку **Actions**
- Дождитесь зеленой галочки ✅
- Ваш сайт готов!

### 4. Откройте ваш сайт

```
https://USERNAME.github.io/REPO-NAME/
```

Замените:
- `USERNAME` - ваш GitHub username
- `REPO-NAME` - название репозитория

---

## 🔄 Обновление сайта

Просто пушьте изменения:

```bash
git add .
git commit -m "Update dashboard"
git push
```

GitHub автоматически соберет и обновит сайт! 🚀

---

## 🛠️ Локальная разработка

### Установка

```bash
npm install
```

### Запуск

```bash
npm run dev
```

Откроется **http://localhost:3000**

### Сборка

```bash
npm run build
```

---

## ❓ Проблемы?

### Сайт показывает 404

1. Проверьте Settings → Pages → Source = **GitHub Actions**
2. Подождите 2-3 минуты после деплоя
3. Очистите кеш браузера (Ctrl+Shift+R)

### Actions не запускается

1. Проверьте файл `.github/workflows/deploy.yml`
2. Убедитесь, что вы пушите в ветку `main`
3. Проверьте вкладку Actions - могут быть ошибки

### CSS не загружается

1. Проверьте `vite.config.ts` - должно быть `base: './'`
2. Убедитесь, что файл `.nojekyll` есть в корне

---

## 📚 Подробная документация

- **[DEPLOY.md](./DEPLOY.md)** - полная инструкция по деплою
- **[OPTIMIZATIONS.md](./OPTIMIZATIONS.md)** - описание оптимизаций
- **[README.md](./README.md)** - документация проекта

---

## ✨ Готово!

Теперь у вас есть:

✅ Автоматический деплой на GitHub Pages  
✅ Оптимизированный production build  
✅ Минификация и code splitting  
✅ Быстрая загрузка (< 2 сек)  
✅ Responsive дизайн  
✅ Темная тема  

**Приятной разработки! 🎉**
