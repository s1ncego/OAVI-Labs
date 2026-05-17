# Лабораторная работа №6. Сегментация текста

Вариант 5: Кириллица, строчные буквы - абвгдежѕзиiклмнопрстуфхцчшщъыьѣюѵѯѱѡѳѧѫ
Шрифт: Times New Roman, кегль 52.


В качестве романтической фразы выбрана:

> ты моѣ счастье

Исходное изображение:

<img src="phrase.bmp" style="border:1px solid #888; padding:6px; background:#fff;"/>

## Профили изображения
Профили фразы:

<img src="profiles/phrase_profiles.png" style="border:1px solid #888;"/>

На вертикальном профиле видны нули - это пробелы между буквами и между словами. По ним и строится сегментация.

## Задание 3. Сегментация символов

Фраза с обрамляющими прямоугольниками вокруг каждого символа:

<img src="segmented/phrase_boxes.png" style="border:1px solid #888;"/>

### Вырезанные символы фразы (в порядке чтения)

| № | Символ | Координаты (x1, y1, x2, y2) |
|:---:|:---:|:---:|
| 0 | <img src="segmented/letters/00.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (0, np.int64(13), 21, np.int64(35)) |
| 1 | <img src="segmented/letters/01.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (24, np.int64(13), 56, np.int64(35)) |
| 2 | <img src="segmented/letters/02.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (72, np.int64(13), 102, np.int64(35)) |
| 3 | <img src="segmented/letters/03.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (106, np.int64(13), 127, np.int64(35)) |
| 4 | <img src="segmented/letters/04.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (131, np.int64(0), 156, np.int64(35)) |
| 5 | <img src="segmented/letters/05.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (173, np.int64(13), 191, np.int64(35)) |
| 6 | <img src="segmented/letters/06.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (195, np.int64(13), 218, np.int64(35)) |
| 7 | <img src="segmented/letters/07.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (222, np.int64(13), 242, np.int64(35)) |
| 8 | <img src="segmented/letters/08.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (245, np.int64(13), 263, np.int64(35)) |
| 9 | <img src="segmented/letters/09.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (266, np.int64(13), 287, np.int64(35)) |
| 10 | <img src="segmented/letters/10.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (290, np.int64(13), 310, np.int64(35)) |
| 11 | <img src="segmented/letters/11.png" style="border:1px solid #888; padding:4px; background:#fff;" height="50"/> | (315, np.int64(13), 334, np.int64(35)) |

## Задание 4. Профили символов алфавита

### Эталонные изображения и профили символов фразы

| Символ | Эталон | Профили (X и Y) |
|:---:|:---:|:---:|
| т | <img src="symbols/т.png" style="border:1px solid #888; padding:4px; background:#fff;" height="60"/> | <img src="profiles/alphabet/т.png" height="160"/> |
| ы | <img src="symbols/ы.png" style="border:1px solid #888; padding:4px; background:#fff;" height="60"/> | <img src="profiles/alphabet/ы.png" height="160"/> |
| м | <img src="symbols/м.png" style="border:1px solid #888; padding:4px; background:#fff;" height="60"/> | <img src="profiles/alphabet/м.png" height="160"/> |
| о | <img src="symbols/о.png" style="border:1px solid #888; padding:4px; background:#fff;" height="60"/> | <img src="profiles/alphabet/о.png" height="160"/> |
| ѣ | <img src="symbols/ѣ.png" style="border:1px solid #888; padding:4px; background:#fff;" height="60"/> | <img src="profiles/alphabet/ѣ.png" height="160"/> |
| с | <img src="symbols/с.png" style="border:1px solid #888; padding:4px; background:#fff;" height="60"/> | <img src="profiles/alphabet/с.png" height="160"/> |
| ч | <img src="symbols/ч.png" style="border:1px solid #888; padding:4px; background:#fff;" height="60"/> | <img src="profiles/alphabet/ч.png" height="160"/> |
| а | <img src="symbols/а.png" style="border:1px solid #888; padding:4px; background:#fff;" height="60"/> | <img src="profiles/alphabet/а.png" height="160"/> |
| ь | <img src="symbols/ь.png" style="border:1px solid #888; padding:4px; background:#fff;" height="60"/> | <img src="profiles/alphabet/ь.png" height="160"/> |
| е | <img src="symbols/е.png" style="border:1px solid #888; padding:4px; background:#fff;" height="60"/> | <img src="profiles/alphabet/е.png" height="160"/> |
