# Hijri Calendar for XFCE4

GTK календарь хиджры с интеграцией в панель XFCE.

## Компоненты

| Файл | Описание |
|------|----------|
| `hijri-date` | CLI для получения даты хиджры |
| `hijri-calendar` | GTK календарь с навигацией |
| `hijri-genmon` | Скрипт для панели XFCE (genmon) |

## Установка

### 1. Зависимости

```bash
pip install hijri-converter --user --break-system-packages
```

### 2. Копирование скриптов

```bash
cp hijri-date hijri-calendar hijri-genmon ~/bin/
chmod +x ~/bin/hijri-date ~/bin/hijri-calendar ~/bin/hijri-genmon
```

### 3. Добавление на панель XFCE

1. **Правый клик на панели** → "Панель" → "Добавить элементы..."
2. Найти **"Универсальный монитор"** (Generic Monitor) → Добавить
3. **Правый клик на новом элементе** → "Свойства"
4. Настройки:
   - **Команда:** `~/bin/hijri-genmon`
   - **Интервал:** `60` секунд
   - **Метка:** убрать галочку

## Использование

### Панель
- Показывает: `al-Arbi'a 25 Rajab 1447`
- **Клик** → открывает календарь

### Календарь
| Действие | Результат |
|----------|-----------|
| **◀ / ▶** или **← →** | Листать месяцы |
| **Today** | Вернуться к текущему дню |
| **- / +** | Корректировка ±1 день |
| **Esc** | Закрыть |

### CLI

```bash
~/bin/hijri-date              # al-Arbi'a 25 Rajab 1447 H
~/bin/hijri-date panel        # al-Arbi'a 25 Rajab 1447
~/bin/hijri-date short        # 25 Rajab 1447
~/bin/hijri-date ar           # الأربعاء 25 رجب 1447

~/bin/hijri-date set 1        # +1 день
~/bin/hijri-date set -1       # -1 день
~/bin/hijri-date set 0        # сброс
```

## Конфигурация

Корректировка хранится в `~/.config/hijri-date.conf`

Все компоненты синхронизированы через этот файл.

## TODO

- [ ] Исламские праздники (подсветка)
- [ ] Время намаза
- [ ] Выбор формата даты в настройках
