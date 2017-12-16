# Лабораторная работа по предмету Анализ данных ([Классификация](https://github.com/EgerV/Laba2/blob/master/Laba.ipynb))
## Описание задачи
Для данной работы мною был выбран Dataset [MNIST](https://mega.nz/#!tBcFgQyT!ut7yQPgTBNe4sl7kmQLeB-U3o5IAmLQsu88k_LdCD68). Задача состоит в распознавании рукописных цифр.
## Описание dataset'а
Он состоит из 42000 объектов, 784 признаков.  
Каждый объект представляет собой изображение цифры 28x28.  
Каждый признак представляет собой определенный пиксель изображения, хранящий значение от 0-255, 0 - черный цвет, 255 - белый.  
Классы представляют собой цифры, 0-9.  
## Используемая метрика качества
Для данной задачи я решил выбрать метрику F1 с макро усреднением, так как данная метрика определяет, насколько точно и полно были классифицированы объекты, что достаточно полно оценивает качество данной задачи.
## Качество полученных классификаторов
### kNN
![Confusion matrix, without normalization](https://github.com/EgerV/Laba2/blob/master/CM/kNN_CM.png)
![Normalized confusion matrix](https://github.com/EgerV/Laba2/blob/master/CM/kNN_NCM.png)  
#### Лучшие параметры:
 - Количество соседей: 3
 - L-метрика: эвклидова (2)
 - Весовая функция, используемая в прогнозировании: distance
#### Оценка предсказания тренировочной выборки с данными параметрами: 0.960868885832
#### Оценка предсказания тестовой выборки с данными параметрами: 0.963131490105
### SVM
![Confusion matrix, without normalization](https://github.com/EgerV/Laba2/blob/master/CM/SVM_CM.png)
![Normalized confusion matrix](https://github.com/EgerV/Laba2/blob/master/CM/SVM_NCM.png)  
#### Лучшие параметры:
 - Ядро: rbf
 - Штраф параметра C ошибки: 10
 - Gamma: 0.05
#### Оценка предсказания тренировочной выборки с данными параметрами: 0.973670095438
#### Оценка предсказания тестовой выборки с данными параметрами: 0.976794711685
### Дерево решений
![Confusion matrix, without normalization](https://github.com/EgerV/Laba2/blob/master/CM/Tree_CM.png)
![Normalized confusion matrix](https://github.com/EgerV/Laba2/blob/master/CM/Tree_NCM.png)  
#### Лучшие параметры:
 - Критерий: entropy
 - Максимальная глубина: 256
 - Минимальное разделение: 5
#### Оценка предсказания тренировочной выборки с данными параметрами: 0.844682794709
#### Оценка предсказания тестовой выборки с данными параметрами: 0.849533950892
### CNN
![Confusion matrix, without normalization](https://github.com/EgerV/Laba2/blob/master/CM/CNN_CM.png)
![Normalized confusion matrix](https://github.com/EgerV/Laba2/blob/master/CM/CNN_NCM.png)  
#### Лучшие параметры:
 - Эпохи: 15
 - Batch size: 128
#### Оценка предсказания тренировочной выборки с данными параметрами: 0.989575132164
#### Оценка предсказания тестовой выборки с данными параметрами: 0.991909716852
### Наивный байесовский
![Confusion matrix, without normalization](https://github.com/EgerV/Laba2/blob/master/CM/NB_CM.png)
![Normalized confusion matrix](https://github.com/EgerV/Laba2/blob/master/CM/NB_NCM.png)  
#### Лучшие параметры:
 - Alpha: 0
 - Fit prior: False
#### Оценка предсказания тренировочной выборки с данными параметрами: 0.833490481369
#### Оценка предсказания тестовой выборки с данными параметрами: 0.833690526198
## Лучшая модель
Для данной задачи лучшей моделью являются сверточные нейронные сети, но это я покажу когда наконец-то они посчитаются :-)
