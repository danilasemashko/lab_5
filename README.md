# Изучение влияние параметра “темп обучения” на процесс обучения нейронной сети на примере решения задачи классификации Oregon Wildlife с использованием техники обучения Transfer Learning
# 1) С использованием [1] и техники обучения Transfer Learning обучить нейронную сеть EfficientNet-B0 (предварительно обученную на базе изображений imagenet) для решения задачи классификации изображений Oregon WildLife с использованием фиксированных темпов обучения 0.1, 0.01, 0.001, 0.0001
-Графики обучения:
-Для метрики качества

 ![alt text](metrika1.jpg)
   
   График метрики качества
  ![SVG example](./metriks1.svg)
  
  -Для функции потерь
  
  ![alt text](loss1.jpg)
  
  График функции потерь
  ![SVG example](./loss1.svg)


# 2) Реализовать и применить в обучении следующие политики изменения темпаобучения [2], а также определить оптимальные параметры для каждой политики: a. Пошаговое затухание (Step Decay) b. Экспоненциальное затухание (Exponential Decay)
# a. Step Decay
Графики обучения:
-Для метрики качества

 ![alt text](exp_metrika.jpg)
   
   График метрики качества
  ![SVG example](./exp_metrika.svg)
  
  -Для функции потерь
  
  ![alt text](exp_loss.jpg)
  
  График функции потерь
  ![SVG example](./exp_loss.svg)


# b. Exponential Decay

Графики обучения:




# Анализ результатов
 По результатам приведённым на графиках видно, что применение политик изменения темпа обучения не привело к значительному улучшению качества.
 На графиках функции потерь можно увидеть что к наилучшему результату привело применени постоянного темпа обучения со значением 0.0001,это случилось из-за того, что темп обучения является шагом в методе градиентного спуска, и при наименьшем шаге мы медленно но верно спустились в самую нижнюю точку ближайшего локального минимума, тогда как при больших значениях темпа обучения мы могли просто перескочить нашу нижнюю точку локального минимума и не иметь возможности спуститься к ней и при этом не попасть в другой локальный минимум. При использовании политики Step Decay наилучший результат получился при использовании нашального шага 0.01 и уменьшении его в ~3 раза каждые 10 эпоx, однако это заняло больше времени. 
 # Вывод:
 Каждая политика хороша по своему, одна может дать лучший результат , но замедлить процесс обучения, другая же наоборот может ускорить процесс обучения , но ухудшить результат. Политику следует выбирать относительно поставленной задачи , а наилучшие значения для её реализации подбирать методом проб и ошибок.
