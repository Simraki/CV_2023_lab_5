# CV_2023_lab5
## Сегментация

## Датасет
[Датасет](https://drive.google.com/file/d/1PwK2oz_NbJU0NsT42Wr_Yv6rcZcJa5Uc/view?usp=sharing) представляет из себя набор подводных аннотированных снимков(исходные изображения - dataset/images, аннотации - dataset/masks), всего 1525 изображений и 8 категорий объектов:  
![image](https://github.com/compfee/CV_2023_lab5/assets/55783463/32eed333-d053-4378-a459-2ee1882ddd7a)

## Описание задачи
Язык программирования - Python  
Разрешено использовать любую библиотеку для машинного обучения (PyTorch, TensorFlow, Keras и др.)  
Необходимо создать модель для сегментации изображений с определением класса выделенной области  
Измерить время работы модели на тестовом датасете и посчитать необходимые метрики  
## Ограничения
Запрещено использование готовых архитектур "из коробки" одной строчкой. В коде должны быть прописаны слои вашей модели
## Метрики
Метрики оценки качества сегментации:  
IoU:  
![image](https://github.com/compfee/CV_2023_lab5/assets/55783463/b78b3cdc-4b02-48dd-a474-c8ec7845f5d2)  
​Per-class IoU:  
IoU по каждому из 8 классов  
Per-pixel accuracy:  
![image](https://github.com/compfee/CV_2023_lab5/assets/55783463/4093f270-9ca5-4fc8-a7de-10c93e1c44dd)  
 

## Baseline
Модель Unet, оптимизатор - SGD, lоss - cross_entropy, batch_size = 16, количество эпох - 20  
Результаты на валидационной выборке:  
Test IoU = 0.60  
Test Channel IoU = [0.63, 0.58, 0.65, 0.60, 0.77, 0.57, 0.60, 0.62]  
Test Pixel Accuracy = 0.75  

## Результаты
Модель DeepLabV3 с ResNet в качестве енкодера, оптимизатор - SGD, lоss - CrossEntropy, batch_size = 16, количество эпох - 20

Пример работы на изображении:
![example_img](https://github.com/Simraki/CV_2023_lab_5/blob/master/images/example_res.png)
  

График метрик на изображении:
![metrics_img](https://github.com/Simraki/CV_2023_lab_5/blob/master/images/plots.png)

Результаты на тестовой выборке:

- Test IoU = 0.448
- Test DICE Mean = 0.385
- Test Channel IoU = [0.94, 0.28, 0.06, 0.45, 0.11, 0.69, 0.55, 0.51]
- Test Pixel Accuracy = 0.737
