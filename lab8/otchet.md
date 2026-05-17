# Лабораторная работа №8. Текстурный анализ и контрастирование

Вариант 5:
- Текстурная матрица: LBP
- Признак: гистограмма H(LBP)
- Метод преобразования яркости: степенное 

В работе используются три изображения разных типов

### Цветовая модель HSL

Для контрастирования цветных изображений используется модель HSL. Гамма-коррекция применяется только к каналу L, а оттенок и насыщенность остаются нетронутыми. Так получается изменить контраст изображения, не искажая его цвета.

После преобразования HSL обратно конвертируется в RGB для сохранения.

### LBP

LBP - это простой и эффективный текстурный дескриптор. Для каждого пикселя берётся его окрестность 3×3 (8 соседей), и каждый сосед сравнивается с центральным пикселем:
- если яркость соседа ≥ яркости центра, в этой позиции ставится бит 1;
- иначе - бит 0.

8 битов, собранные в фиксированном порядке (обход соседей по часовой стрелке начиная с верхнего левого), дают одно число от 0 до 255 - код LBP для этого пикселя. В итоге из полутонового изображения получается «изображение кодов» того же размера, где каждый пиксель хранит информацию о локальной текстуре вокруг себя.

Далее по этой матрице строится гистограмма H(LBP) - распределение кодов от 0 до 255. Именно она и используется как текстурный дескриптор: похожие текстуры дают похожие гистограммы.

### Степенное преобразование

Степенное преобразование (гамма-коррекция) - один из самых используемых методов изменения яркости:

$$s = c \cdot \left(\frac{r}{255}\right)^{\gamma} \cdot 255$$

где r - исходная яркость пикселя, s - новая, γ - параметр.

- При γ < 1 тёмные области «вытягиваются» вверх - изображение становится светлее, проявляются детали в тенях.
- При γ > 1 наоборот - тёмные области ещё больше затемняются.
- При γ = 1 изображение не изменяется.

В работе использована γ = 0,5 - легкое осветление, подходящее для большинства фотографий, чтобы посмотреть его на изображениях разного типа

## Признаки на основе H(LBP)

По гистограмме H(LBP), нормированной к 1 , рассчитываются:

| Признак | Смысл |
|---|---|
| Mean | средний код LBP |
| Variance | дисперсия - мера разброса кодов |
| Energy | $\sum p_i^2$ - мера однородности (чем выше, тем «однообразнее» текстура) |
| Entropy | $-\sum p_i \log_2 p_i$ - мера информативности (чем выше, тем разнообразнее текстура) |
| Contrast | дисперсия относительно среднего, отражает контраст текстуры |

Признаки рассчитываются дважды: для исходного и для контрастированного изображения. Результаты сохраняются в features.csv.

## Результаты

### Изображения (до / после контрастирования)
| Имя | Исходное (RGB) | Полутон | Контрастированное (RGB) | Полутон контр. |
|---|---|---|---|---|
| image1 | <img src="input/image1.png" width="200" style="border:1px solid #888"/> | <img src="grayscale/image1.bmp" width="200" style="border:1px solid #888"/> | <img src="contrasted/image1_color.png" width="200" style="border:1px solid #888"/> | <img src="contrasted/image1_gray.bmp" width="200" style="border:1px solid #888"/> |
| image2 | <img src="input/image2.png" width="200" style="border:1px solid #888"/> | <img src="grayscale/image2.bmp" width="200" style="border:1px solid #888"/> | <img src="contrasted/image2_color.png" width="200" style="border:1px solid #888"/> | <img src="contrasted/image2_gray.bmp" width="200" style="border:1px solid #888"/> |
| image3 | <img src="input/image3.png" width="200" style="border:1px solid #888"/> | <img src="grayscale/image3.bmp" width="200" style="border:1px solid #888"/> | <img src="contrasted/image3_color.png" width="200" style="border:1px solid #888"/> | <img src="contrasted/image3_gray.bmp" width="200" style="border:1px solid #888"/> |

### Гистограммы яркости (до / после)

| Имя | До | После |
|---|---|---|
| image1 | <img src="histograms/image1_before.png" width="350"/> | <img src="histograms/image1_after.png" width="350"/> |
| image2 | <img src="histograms/image2_before.png" width="350"/> | <img src="histograms/image2_after.png" width="350"/> |
| image3 | <img src="histograms/image3_before.png" width="350"/> | <img src="histograms/image3_after.png" width="350"/> |

### Матрицы LBP 

| Имя | До | После |
|---|---|---|
| image1 | <img src="lbp_images/image1_before.png" width="250" style="border:1px solid #888"/> | <img src="lbp_images/image1_after.png" width="250" style="border:1px solid #888"/> |
| image2 | <img src="lbp_images/image2_before.png" width="250" style="border:1px solid #888"/> | <img src="lbp_images/image2_after.png" width="250" style="border:1px solid #888"/> |
| image3 | <img src="lbp_images/image3_before.png" width="250" style="border:1px solid #888"/> | <img src="lbp_images/image3_after.png" width="250" style="border:1px solid #888"/> |

### Гистограммы H(LBP)

| Имя | До | После |
|---|---|---|
| image1 | <img src="lbp_histograms/image1_before.png" width="350"/> | <img src="lbp_histograms/image1_after.png" width="350"/> |
| image2 | <img src="lbp_histograms/image2_before.png" width="350"/> | <img src="lbp_histograms/image2_after.png" width="350"/> |
| image3 | <img src="lbp_histograms/image3_before.png" width="350"/> | <img src="lbp_histograms/image3_after.png" width="350"/> |

## Вывод

Гамма-коррекция при γ = 0,5 осветляет темные участки изображений, что хорошо видно по сдвигу гистограммы яркости вправо. При этом цвета сохраняются за счёт работы только с каналом L в модели HSL.