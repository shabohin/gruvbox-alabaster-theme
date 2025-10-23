Отличная идея! Это правильный подход. Вот обновлённый план:

---

# 📋 ОБНОВЛЁННЫЙ ПЛАН: OneDark-Alabaster Theme

## 📁 ШАГ 1: Клонирование репозиториев

### 1.1 Создать рабочую директорию
```bash
mkdir onedark-alabaster-theme
cd onedark-alabaster-theme
```

### 1.2 Клонировать оба репозитория во вложенные папки
```bash
# Клонировать OneDark-Pro
git clone https://github.com/Binaryify/OneDark-Pro.git ./source-onedark

# Клонировать Alabaster
git clone https://github.com/tonsky/vscode-theme-alabaster.git ./source-alabaster
```

### 1.3 Итоговая структура
```
onedark-alabaster-theme/
├── source-onedark/              ← исходники OneDark-Pro
│   └── themes/
│       ├── OneDark-Pro.json
│       ├── OneDark-Pro-flat.json    ← нужен этот!
│       └── ...
├── source-alabaster/            ← исходники Alabaster
│   └── theme/
│       └── alabaster-color-theme.json
├── package.json                 ← создать
├── themes/
│   └── onedark-alabaster.json   ← создать
└── README.md                    ← опционально
```

---

## 📝 ШАГ 2: Изучение исходников

### 2.1 Посмотреть структуру OneDark-Pro Flat
```bash
# Открыть для изучения
cat source-onedark/themes/OneDark-Pro-flat.json
```

**Что нас интересует:**
- Блок `"colors": { ... }` - UI цвета (фон, панели, кнопки)
- Структура файла

### 2.2 Посмотреть структуру Alabaster
```bash
# Открыть для изучения
cat source-alabaster/theme/alabaster-color-theme.json
```

**Что нас интересует:**
- Блок `"tokenColors": [ ... ]` - правила подсветки
- Философия минимализма (всего 4-5 правил)

---

## 🎨 ШАГ 3: Создание package.json

Создать файл `package.json` в корне `onedark-alabaster-theme/`:

```json
{
  "name": "onedark-alabaster-theme",
  "displayName": "OneDark Alabaster",
  "description": "OneDark Pro Flat UI with Alabaster minimal syntax highlighting",
  "version": "1.0.0",
  "publisher": "yourname",
  "engines": {
    "vscode": "^1.60.0"
  },
  "categories": [
    "Themes"
  ],
  "contributes": {
    "themes": [
      {
        "label": "OneDark Alabaster",
        "uiTheme": "vs-dark",
        "path": "./themes/onedark-alabaster.json"
      }
    ]
  },
  "keywords": [
    "theme",
    "dark",
    "onedark",
    "alabaster",
    "minimal"
  ],
  "license": "MIT"
}
```

---

## 🔨 ШАГ 4: Создание гибридной темы

### 4.1 Создать папку themes
```bash
mkdir themes
```

### 4.2 Создать файл `themes/onedark-alabaster.json`

**Базовая структура:**

```json
{
  "$schema": "vscode://schemas/color-theme",
  "name": "OneDark Alabaster",
  "type": "dark",
  
  "colors": {
    // ШАГ 4.3: СКОПИРОВАТЬ СЮДА весь блок colors 
    // из source-onedark/themes/OneDark-Pro-flat.json
  },
  
  "tokenColors": [
    // ШАГ 4.4: ДОБАВИТЬ СЮДА адаптированные правила
  ]
}
```

### 4.3 Скопировать блок colors из OneDark-Pro Flat

**Команда для копирования (или сделать вручную):**
```bash
# Извлечь блок colors из OneDark-Pro-flat.json
# и вставить в onedark-alabaster.json
```

**Что копировать:**
- Открыть `source-onedark/themes/OneDark-Pro-flat.json`
- Найти `"colors": {`
- Скопировать ВСЁ до закрывающей `}` (примерно 200-300 строк)
- Вставить в `themes/onedark-alabaster.json` в секцию `colors`

### 4.4 Создать tokenColors (адаптация Alabaster для тёмной темы)

**Вставить в секцию `tokenColors`:**

```json
"tokenColors": [
  {
    "name": "Base text - not highlighted",
    "scope": [
      "source",
      "text",
      "variable",
      "variable.other.readwrite",
      "variable.other.object",
      "variable.other.property",
      "variable.parameter",
      "support.variable",
      "meta.object-literal.key"
    ],
    "settings": {
      "foreground": "#ABB2BF"
    }
  },
  {
    "name": "Comments - BRIGHT (Alabaster principle)",
    "scope": [
      "comment",
      "punctuation.definition.comment"
    ],
    "settings": {
      "foreground": "#E5C07B"
    }
  },
  {
    "name": "Strings",
    "scope": [
      "string",
      "string.quoted",
      "string.template",
      "string.regexp",
      "constant.other.symbol"
    ],
    "settings": {
      "foreground": "#98C379"
    }
  },
  {
    "name": "String escape sequences",
    "scope": [
      "constant.character.escape",
      "constant.other.placeholder"
    ],
    "settings": {
      "foreground": "#5C6370"
    }
  },
  {
    "name": "Numbers and Constants",
    "scope": [
      "constant.numeric",
      "constant.character",
      "constant.language.boolean",
      "constant.language.null",
      "constant.language.undefined",
      "constant.language"
    ],
    "settings": {
      "foreground": "#C678DD"
    }
  },
  {
    "name": "Global definitions (functions, classes) - Alabaster principle",
    "scope": [
      "entity.name.function",
      "entity.name.class",
      "entity.name.type",
      "support.class",
      "support.type"
    ],
    "settings": {
      "foreground": "#61AFEF"
    }
  },
  {
    "name": "Keywords - BASE COLOR (not highlighted, Alabaster principle)",
    "scope": [
      "keyword",
      "keyword.control",
      "keyword.operator",
      "keyword.other",
      "storage.type",
      "storage.modifier"
    ],
    "settings": {
      "foreground": "#ABB2BF"
    }
  },
  {
    "name": "Function/method calls - BASE COLOR (not highlighted)",
    "scope": [
      "meta.function-call",
      "support.function"
    ],
    "settings": {
      "foreground": "#ABB2BF"
    }
  },
  {
    "name": "Punctuation - slightly dimmed",
    "scope": [
      "punctuation",
      "meta.brace",
      "meta.bracket",
      "punctuation.separator",
      "punctuation.terminator"
    ],
    "settings": {
      "foreground": "#5C6370"
    }
  },
  {
    "name": "Invalid/Deprecated",
    "scope": [
      "invalid",
      "invalid.deprecated"
    ],
    "settings": {
      "foreground": "#E06C75",
      "fontStyle": "strikethrough"
    }
  }
]
```

---

## 🔧 ШАГ 5: Установка темы локально

### 5.1 Скопировать проект в extensions VSCode

```bash
# Узнать путь к extensions
code --list-extensions --show-versions

# Скопировать (пример для macOS/Linux)
cp -r . ~/.vscode/extensions/onedark-alabaster-theme/

# Для Windows:
# xcopy /E /I . %USERPROFILE%\.vscode\extensions\onedark-alabaster-theme\
```

**ИЛИ создать симлинк (удобнее для разработки):**

```bash
# macOS/Linux
ln -s $(pwd) ~/.vscode/extensions/onedark-alabaster-theme

# Windows (запустить cmd как администратор)
# mklink /D "%USERPROFILE%\.vscode\extensions\onedark-alabaster-theme" "путь\к\проекту"
```

### 5.2 Перезапустить VSCode

**Обязательно!** Полный перезапуск приложения.

### 5.3 Активировать тему

1. `Ctrl+Shift+P` (или `Cmd+Shift+P`)
2. `Preferences: Color Theme`
3. Выбрать: **OneDark Alabaster**

---

## 🎨 ШАГ 6: Итеративная настройка

### 6.1 Workflow для изменений

**При использовании симлинка:**
1. Изменить `themes/onedark-alabaster.json`
2. Сохранить файл
3. `Ctrl+Shift+P` → `Developer: Reload Window`
4. Изменения применятся

### 6.2 Полезные команды для отладки

```bash
# Проверить валидность JSON
cat themes/onedark-alabaster.json | jq .

# Или в VSCode
# Ctrl+Shift+P → "Developer: Inspect Editor Tokens and Scopes"
```

---

## 📦 ШАГ 7: Сохранение в Git

### 7.1 Создать .gitignore

```bash
cat > .gitignore << EOF
source-onedark/
source-alabaster/
node_modules/
*.vsix
.DS_Store
EOF
```

### 7.2 Инициализировать Git

```bash
git init
git add package.json themes/ README.md .gitignore
git commit -m "Initial commit: OneDark Alabaster theme"
```

---

## 🎯 ЧЕКЛИСТ ДЛЯ АГЕНТА

### Подготовка:
- [ ] Создать папку `onedark-alabaster-theme`
- [ ] Клонировать OneDark-Pro в `source-onedark/`
- [ ] Клонировать Alabaster в `source-alabaster/`

### Создание темы:
- [ ] Создать `package.json`
- [ ] Создать `themes/onedark-alabaster.json`
- [ ] Скопировать блок `colors` из `source-onedark/themes/OneDark-Pro-flat.json`
- [ ] Добавить адаптированные `tokenColors` (из Шага 4.4)

### Установка:
- [ ] Скопировать проект в `~/.vscode/extensions/onedark-alabaster-theme/`
  - ИЛИ создать симлинк (рекомендуется для разработки)
- [ ] Перезапустить VSCode
- [ ] Активировать тему

### Опционально:
- [ ] Настроить цвета под себя
- [ ] Протестировать на разных языках
- [ ] Создать README.md
- [ ] Инициализировать Git

---

## 💡 ПРЕИМУЩЕСТВА ЭТОГО ПОДХОДА

1. ✅ **Полный контроль** - видишь весь исходный код обеих тем
2. ✅ **Git history** - можешь смотреть изменения в оригинальных темах
3. ✅ **Легко обновлять** - `git pull` в source-папках для получения обновлений
4. ✅ **Симлинк** - изменения применяются сразу после Reload Window
5. ✅ **Чистота** - source-папки не идут в финальную тему (.gitignore)

---

Этот план теперь полностью готов для агента! 🚀
