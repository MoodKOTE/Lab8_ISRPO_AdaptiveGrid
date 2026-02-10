# Лабораторная работа №8. Адаптивная верстка: CSS Grid

## Цель работы
Освоить современные технологии CSS-разметки — CSS Grid для создания адаптивных веб-макетов.

## Описание проекта
Лабораторная работа состоит из нескольких примеров, демонстрирующих возможности CSS Grid Layout:
1. Базовая Grid-сетка
2. Макет страницы с использованием именованных областей
3. Адаптивная галерея изображений
4. Сложный дашборд (самостоятельное задание)

## Структура проекта
- Lab8_Adaptive_FIO/
- index.html
- grid.css
- gridPractice.html
- gridPractice.css
- grid-practice.html 
- README.md
- img/
- gitPushLab8_FIO.png
- grid_examplesGrid_Lab8_FIO.png
- grid_examplesGridPractice_Lab8_FIO.png
- gridPracticeLab8_FIO.

## Примеры
### Пример 1: Базовая Grid-сетка 3x3
```html
<div class="grid-container">
  <div class="grid-item">1</div>
  <div class="grid-item">2</div>
  <div class="grid-item">3</div>
  <div class="grid-item">4</div>
  <div class="grid-item">5</div>
  <div class="grid-item">6</div>
</div>
```

```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(2, 100px);
  gap: 20px;
}

.grid-item {
  background-color: #4CAF50;
  color: white;
  padding: 20px;
  text-align: center;
  border-radius: 5px;
}
```

### Пример 2: Макет страницы с использованием Grid Areas
```html
<div class="page-layout">
  <header class="header">Header</header>
  <aside class="sidebar">Sidebar</aside>
  <main class="main">Main Content</main>
  <footer class="footer">Footer</footer>
</div>
```
```css
.page-layout {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  grid-template-columns: 200px 1fr;
  grid-template-rows: 80px 1fr 60px;
  gap: 10px;
  height: 500px;
}

.header {
  grid-area: header;
  background-color: #333;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 5px;
}

.sidebar {
  grid-area: sidebar;
  background-color: #f0f0f0;
  padding: 20px;
  border-radius: 5px;
}

.main {
  grid-area: main;
  background-color: #fff;
  border: 2px solid #ddd;
  padding: 20px;
  border-radius: 5px;
}

.footer {
  grid-area: footer;
  background-color: #333;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 5px;
}
```

### Пример 3: Адаптивная галерея изображений
```html
<div class="gallery">
  <div class="gallery-item">Фото 1</div>
  <div class="gallery-item">Фото 2</div>
  <div class="gallery-item">Фото 3</div>
  <div class="gallery-item">Фото 4</div>
  <div class="gallery-item">Фото 5</div>
  <div class="gallery-item">Фото 6</div>
</div>
```
```css
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 15px;
}

.gallery-item {
  background-color: #2196f3;
  color: white;
  padding: 60px;
  text-align: center;
  border-radius: 5px;
  transition: transform 0.3s ease;
}

.gallery-item:hover {
  transform: scale(1.05);
}
```

### Сравнение Flexbox и CSS Grid
|Критерий|Flexbox|CSS Grid|
|--------|-------|--------|
|Тип компоновки|Одномерная|Двумерная|
|Управление|Строка или столбец|Строки и столбцы|
|Основное назначение|Выравнивание элементов|Построение макетов|
|Подходит для|Компонентов|Страниц и сеток|

**Вывод**: Flexbox лучше подходит для линейных структур, Grid — для табличных и сложных.

### Типичные сценарии использования
|Задача|Рекомендуется|
|---|---|
|Навигационное меню| Flexbox|
|Карточки товаров |Flexbox + Grid|
|Центрирование элемента| Flexbox|
|Макет страницы| Grid|
|Галерея изображений| Grid|
|Дашборд |Grid|