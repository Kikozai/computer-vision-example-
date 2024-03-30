# Оценка скорости объекта с использованием оптического потока

## Описание

Этот репозиторий предоставляет код Python для оценки скорости объекта в видео с помощью оптического потока. Оптический поток используется для отслеживания движения объектов в последовательности кадров, и по измеренному движению вычисляется скорость объекта.

### Требования

    Python 3.x
    OpenCV 4.x

## Использование

 1. Клонируйте репозиторий или загрузите код.
 2. Запустите скрипт: 
    ```shell python vision.ipynb``` // при желанни можно в cap указать другой видеопоток

## Запуск

Запуск скрипта выполняет следующие действия: 
    Устанавливает параметры для детектирования и отслеживания признаков оптического потока.
    Читает видеопоток или видеофайл и преобразует его в последовательность кадров.
    Для каждого кадра вычисляет оптический поток и отслеживает положение признаков.
    Оценивает скорость объекта на основе смещения признаков между кадрами.
    Отображает скорость объекта в километрах в час на кадре.

## Результаты

Скрипт выводит видеопоток с нарисованными красными кругами, обозначающими расположение движущихся объектов. Скорость каждого объекта отображается рядом с кругом.

## Технические детали
  Функция ```cv2.goodFeaturesToTrack()``` используется для обнаружения признаков в кадре.
    Функция ```cv2.calcOpticalFlowPyrLK()``` используется для отслеживания признаков на последовательных кадрах.
    Для оценки скорости используется расстояние между положением признаков на последовательных кадрах.
    Масштаб изображения в метрах на пиксель рассчитывается на основе известного реального расстояния и соответствующего количества пикселей в кадре.
    Скорость выводится в километрах в час (км/ч).

### Примечания

  1.Точность оценки скорости зависит от качества оптического потока.
    2.Типы объектов, которые можно обнаружить и отслеживать, ограничены возможностями алгоритма оптического потока.
    3.Скрипт предназначен для использования с видеопотоками или видеофайлами, содержащими движущиеся объекты.
