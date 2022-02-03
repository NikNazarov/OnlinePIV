# Программа для анализа PIV данных
В данной программе реализованы основные алгоритмы метода PIV, такие как итерационный кросс-корреляционный метод на основе FFT, фильтрация и интерполяция эффекта потери праы и тд. На данном этапе доступен __графический интерфейс__, возможность выбора гиперпараметров PIV. Ключевой особенностью проекта является использование графических ускорителей за счет библиотеки __torch__.

__Параметры программы:__
1. Размер окна поиска 
2. Размер перекрытия окон
3. Масштаб координат
4. Время между кадрами
5. Выбор устройства для расчета (ЦПУ или ГПУ)
6. Интерполяция поля (увеличение количества веркторов за счет интерполяции на первой итерации алгоритма)
7. Количество итераций алгоритма
8. Параметры окна поиска во время итераций
9. Выбор поддерживаемых форматов изображений (bmp, jpg, tiff, ect.)
10. Выбор опций для сохранения результатов программы

__Скорость алгоритма__:
Данный алгоритм позволяет обработать 4 тыс. пар изображений размером 4 Мп с окном поиска 64, перекрытием 50%, двумя итерациями с переразбиением (увеличение количества векторов в 4 раза) менее чем за 1 час. Первая итерация алгоритма (без интерполированных векторов) занимает 100 мс на ГПУ Geforce GTX 1050.

__Дальнейшие планы работы__:
Создание версии программы для обработки данных во время их записи. Возможность отображения интерактивных графиков профилей скорости. Возможность обработки данных стерео PIV.
