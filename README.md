# Text Quest Editor

## Что это

Text Quest Editor — это инструмент для создания текстовых квестов.

Он работает в связке с Text Quest Reader:
- **Editor** — создание квестов  
- **Reader** — запуск и прохождение  

Квесты сохраняются в формате JSON, что позволяет использовать их в любых проектах, не обязательно на Unity.

---

## Быстрый старт

1. Нажмите на кнопку  
<img src="docs/btn_new.webp" width="46">

2. Введите название квеста → Accept  
3. Добавьте один параметр  
4. Создайте две локации  
5. Соедините их переходом  
6. Нажмите  
<img src="docs/btn_play.webp" width="54">
 
У вас уже есть рабочий квест

---

## Основы

Квест создаётся и хранится как папка с JSON и ресурсами.

Editor + Reader образуют единую систему:
- Editor генерирует данные
- Reader их исполняет

---

## Как устроен квест

Квест состоит из трёх ключевых элементов:

- **Параметры** — числа (здоровье, золото и т.д.)
- **Локации** — сцены / ситуации
- **Переходы** — выбор игрока

Как это работает:
1. Игрок попадает в локацию  
2. Видит описание  
3. Выбирает переход  
4. Параметры могут измениться  

---

## Создание и загрузка

### Создание нового квеста

1. Нажмите  
<img src="docs/btn_new.webp" width="46">

2. Введите название → Accept  
3. Название = ID (не меняется)  
4. Оно должно совпадать с именем папки  

---

### Загрузка квеста

1. Нажмите  
<img src="docs/btn_load.webp" width="47">

2. Выберите квест  
3. Нажмите Load  

---

### Сохранение

1. Нажмите  
<img src="docs/btn_save.webp" width="44">

2. Нажмите Save  
3. Горячие клавиши:  
   - Ctrl + S (Windows)  
   - Cmd + S (macOS)

---

## Структура квеста

<img src="docs/quest_structure.webp" width="273">

Внутри:
- quest.json  
- Images  
- Sounds  
- Musics  

Создаются автоматически.

---

## Параметры

Начните с простых параметров:
- золото  
- здоровье  
- настроение  

### Создание

1. Нажмите  
<img src="docs/btn_params.webp" width="42">

2. Нажмите  
<img src="docs/box_add_param.webp" width="164">

3. Укажите Working title  

---

### Значения

Задайте:
- минимум  
- максимум  
- старт  

<img src="docs/param_panel_1.webp" width="891">

---

### Отображение

<img src="docs/param_panel_2.webp" width="890">

Можно:
- показывать текст
- показывать значения
- комбинировать параметры

Примеры:

<img src="docs/param_outlook_1.webp" width="301">  
<img src="docs/param_outlook_2.webp" width="180">  

<img src="docs/param_outlook_3.webp" width="778">  
<img src="docs/param_outlook_4.webp" width="159">  

<img src="docs/param_outlook_5.webp" width="849">

---

### Типы параметров

<img src="docs/param_types.webp" width="892">

- Нормальный  
- Успешный  
- Проваленный  

---

### Деактивация

<img src="docs/param_disable.webp" width="159">

---

## Локации

<img src="docs/edit_location.webp" width="895">

### Описания

<img src="docs/loc_descr_1.webp" width="164">  
<img src="docs/loc_descr_2.webp" width="444">  

Формулы выбора:

<img src="docs/loc_descr_3.webp" width="338">  
<img src="docs/loc_descr_4.webp" width="707">

---

### Типы

<img src="docs/loc_types.webp" width="173">

- Нейтральная  
- Стартовая  
- Победная  
- Проваленная  
- Пустая  

---

### Проходимость

<img src="docs/loc_pass_1.webp" width="184">  
<img src="docs/loc_pass_2.webp" width="199">

---

### Влияние

<img src="docs/loc_infl_to_param.webp" width="876">

Типы влияния:
- Единицы  
- Значение  
- Проценты  
- Формула  

---

### Формулы (упрощённо)

Примеры:

- `p1 + 1`  
- `p1 > 5`  
- `rnd(1,3)`  

---

## Переходы

<img src="docs/edit_trans.webp" width="892">

### Кнопка перехода

<img src="docs/trans_btn_text.webp" width="288">  
<img src="docs/trans_btn_view.webp" width="215">

---

### Условия показа

<img src="docs/trans_logical_condition.webp" width="277">  
<img src="docs/trans_range.webp" width="239">  
<img src="docs/trans_accepts.webp" width="241">  
<img src="docs/trans_div.webp" width="239">

---

### Порядок

<img src="docs/trans_order_1.webp" width="274">  
<img src="docs/trans_order_2.webp" width="127">

---

### Приоритет

<img src="docs/trans_prior_1.webp" width="551">  
<img src="docs/trans_prior_2.webp" width="219">

---

### Всегда показывать

<img src="docs/trans_always_show_1.webp" width="390">  
<img src="docs/trans_always_show_2.webp" width="137">

---

## Игровой режим

<img src="docs/btn_play.webp" width="54">

---

## Ресурсы

```
<im your_biautiful_picture im>
<mu your_music mu>
<so your_sound so>
```

<img src="docs/res_folders.webp" width="358">

<img src="docs/res_tags_1.webp" width="885">  
<img src="docs/res_tags_2.webp" width="893">

<img src="docs/res_cache.webp" width="225">

---

## Интерфейс

<img src="docs/modes.webp" width="177">

<img src="docs/grid_n_hints.webp" width="37">  
<img src="docs/btn_info.webp" width="26">

<img src="docs/trans_view.webp" width="172">

---

## Советы

- Начинайте с маленького квеста (5–10 локаций)  
- Не усложняйте формулы сразу  
- Постепенно добавляйте логику  
