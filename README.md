# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #5 выполнил(а):
- Еремин Егор Константинович
- РИ210940
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | # | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Цель работы

Интеграция экономической системы в проект Unity и обучение ML-Agent



![image](https://user-images.githubusercontent.com/102966721/205356818-18121c2f-6249-4673-b9b7-fdd804f704c0.png)


После подключения ML-агента устанавливаем tensorflow:

![image](https://user-images.githubusercontent.com/102966721/205350811-a5494507-c69a-412c-9f3d-0e6bb6df9677.png)

![image](https://user-images.githubusercontent.com/102966721/205351198-843999a5-6026-49a5-840f-33597720d44d.png)



## Задание 2

Обучение без изменения параметров файла:

![image](https://user-images.githubusercontent.com/102966721/205351714-8ddc0cb0-2bac-45d9-8fd0-5506215706cb.png)
![image](https://user-images.githubusercontent.com/102966721/205351760-786f94bf-ab06-4f67-b87b-8f1f4190891b.png)

### Параметр lambd увеличен до 0.99:

![image](https://user-images.githubusercontent.com/102966721/205351904-786a2b2a-71d7-4b3a-baa4-7c398f5eee6b.png)

До изменения параметра lambd обучение завершалось на 15000 шаге, с вознаграждением 1. После увеличения этого параметра обучение длится дольше.

### При увеличении параметра learning_rate:

![image](https://user-images.githubusercontent.com/102966721/205352082-9b5bcdd4-6f4b-4d0d-bdba-3ec79b2217c7.png)

Как и при изменении предыдущего параметра, обучение занимает большее количество времени.

### При увеличении параметра beta:

![image](https://user-images.githubusercontent.com/102966721/205352168-dfedfcb7-5742-4961-9177-6cfa8d497693.png)

Обучение продолжается столько же шагов, сколько и без изменений параметра 

### При увеличении параметра epsilon:

![image](https://user-images.githubusercontent.com/102966721/205352240-506d470d-301b-48d0-ab54-db7b247e742c.png)

Обучение длится большее количество шагов, но время шагов заметно меньше. Так 15000 шагов без изменений этого параметра длятся 122 секунды, а после изменения 115.

### При увеличении параметра gamma:

![image](https://user-images.githubusercontent.com/102966721/205352298-934dfbbe-4329-42a6-8092-5869016da449.png)

Обучение завершается на 10000 шагов, быстрее, чем при стандартном значении параметра.

### При уменьшении параметра gamma:

![image](https://user-images.githubusercontent.com/102966721/205352391-69ec2c4d-6792-4de1-8899-3e8b2ed69058.png)

Обучение происходит быстрее.

### При уменьшении параметра hidden_units в два раза:

![image](https://user-images.githubusercontent.com/102966721/205352484-7ed63727-74e7-4efb-a0a7-73e35dcf55d6.png)

Максимальная награда уменьшается в два раза.

### При увеличении параметра num_epoch:

![image](https://user-images.githubusercontent.com/102966721/205352577-8246ab00-e56a-44ff-9267-573731695148.png)

Обучение происходит за 10000 шагов, быстрее, чем без изменения параметра.



## Задание 3

![image](https://user-images.githubusercontent.com/102966721/205356172-1d93f688-1d69-4422-92c0-c0d7cba96d9a.png)


![image](https://user-images.githubusercontent.com/102966721/205355248-f6453d36-d8c8-4ea9-b7bf-a5e4840a2289.png)

![image](https://user-images.githubusercontent.com/102966721/205356220-a2e11542-b4a0-4a63-aaee-8b3013972ed9.png)


Cumulative Reward: Это общее вознаграждение, которое максимизирует агент.

Episode Length: Отвечает за длину периодов обучения.

Value loss: Величина потери значения.

Entropy: График показывает величину исследования агента.

## Выводы

Подготовили среды разбработки для Unity и Python.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
