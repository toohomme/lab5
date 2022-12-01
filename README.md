# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #5 выполнил(а):
- Еремин Егор Константинович
- РИ210940
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | # | 60 |
| Задание 2 | # | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Цель работы
Ознакомиться с основными операторами зыка Python на примере реализации линейной регрессии.

## Задание 1
### Написать программы Hello World на Python и Unity
Ход работы:

1.Запуск программы выводящей Hello World в Google Colab:
![image](https://user-images.githubusercontent.com/102966721/192340576-f4121125-d660-4ab4-abb3-b7fe8dd947b3.png)
2.Сохранение блокнота с программой на диск:
![image](https://user-images.githubusercontent.com/102966721/192340769-12a1658f-6162-4694-bc62-c99bda68d993.png)
3.Вывод в консоль Hello World на Unity:
![image](https://user-images.githubusercontent.com/102966721/192340939-4765700e-cda7-4868-99ee-ae3ab21f9ed6.png)
4.Код на C# для вывода в консоль на Unity:
![image](https://user-images.githubusercontent.com/102966721/192341090-ffc03b47-09bd-45e8-8b92-c822276d10b2.png)

Итог: Вывели сообщение Hello World на Python и Unity


## Задание 2
### В разделе "ход работы" пошагово выполнить каждый пункт с описанием и примером реализации задачи по теме лабораторной работы.

1.Подготовка данных:
```py
In [ ]:
#Import the required modules, numpy for calculation, and Matplotlib for drawing
import numpy as np
import matplotlib.pyplot as plt
#This code is for jupyter Notebook only
%matplotlib inline

# define data, and change list to array
x = [3,21,22,34,54,34,55,67,89,99]
x = np.array(x)
y = [2,22,24,65,79,82,55,130,150,199]
y = np.array(y)

#Show the effect of a scatter plot
plt.scatter(x,y)
```

2. Определение связанных функций. Функция model определяет модель линейной регрессии wx+b. Функция loss_function - функиця потерь среденеквадратичной ошибки. Функция optimize: метод градиентного спуска для нахождения частных производных w и b. Функция iterated возвращает a и b после итераций.
```py
In [ ]:
def model (a,b,x):
    return a * x + b

def loss_function(a,b,x,y):
    num = len(x)
    prediction = model(a,b,x)
    return (0.5/num)*(np.square(prediction-y)).sum()

def optimize (a,b,x,y):
    num = len(x)
    prediction = model(a,b,x)
    da = (1.0/num)*((prediction - y)*x).sum()
    db = (1.0/num)*((prediction - y).sum())
    a = a - Lr*da
    b = b - Lr*db
    return a,b

def iterate(a,b,x,y,times):
    for i in range(times):
        a,b = optimize(a,b,x,y)
    return a,b
    
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
Lr = 0.000001
x = [3,21,22,34,54,34,55,67,89,99]
x = np.array(x)
y = [2,22,24,65,79,82,55,130,150,199]
y = np.array(y)
```
3. Задаем параметры и производим итерации:
```py
def model (a,b,x):
    return a * x + b

def loss_function(a,b,x,y):
    num = len(x)
    prediction = model(a,b,x)
    return (0.5/num)*(np.square(prediction-y)).sum()

def optimize (a,b,x,y):
    num = len(x)
    prediction = model(a,b,x)
    da = (1.0/num)*((prediction - y)*x).sum()
    db = (1.0/num)*((prediction - y).sum())
    a = a - Lr*da
    b = b - Lr*db
    return a,b

def iterate(a,b,x,y,times):
    for i in range(times):
        a,b = optimize(a,b,x,y)
    return a,b
    
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
Lr = 0.000001
x = [3,21,22,34,54,34,55,67,89,99]
x = np.array(x)
y = [2,22,24,65,79,82,55,130,150,199]
y = np.array(y)
a = np.random.rand(1)
print(a)
b = np.random.rand(1)
print(b)
#Для итераций меняем последний параметр, в функции iterate
a,b = iterate(a,b,x,y,1) 
prediction = model(a,b,x)
loss = loss_function(a,b,x,y)
print(a,b,loss)
plt.scatter(x,y)
plt.plot(x,prediction)

plt.scatter(x,y)
```
На каждом шаге итерации отображаются значения параметров, значения потерь и эффекты визуализации после итерации. 


## Задание 3
### Какова роль параметра Lr? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ. В качестве эксперимента можете изменить значение параметра.

- Перечисленные в этом туториале действия могут быть выполнены запуском на исполнение скрипт-файла, доступного [в репозитории](https://github.com/Den1sovDm1triy/hfss-scripting/blob/main/ScreatingSphereInAEDT.py).
- Для запуска скрипт-файла откройте Ansys Electronics Desktop. Перейдите во вкладку [Automation] - [Run Script] - [Выберите файл с именем ScreatingSphereInAEDT.py из репозитория].

```py

import ScriptEnv
ScriptEnv.Initialize("Ansoft.ElectronicsDesktop")
oDesktop.RestoreWindow()
oProject = oDesktop.NewProject()
oProject.Rename("C:/Users/denisov.dv/Documents/Ansoft/SphereDIffraction.aedt", True)
oProject.InsertDesign("HFSS", "HFSSDesign1", "HFSS Terminal Network", "")
oDesign = oProject.SetActiveDesign("HFSSDesign1")
oEditor = oDesign.SetActiveEditor("3D Modeler")
oEditor.CreateSphere(
	[
		"NAME:SphereParameters",
		"XCenter:="		, "0mm",
		"YCenter:="		, "0mm",
		"ZCenter:="		, "0mm",
		"Radius:="		, "1.0770329614269mm"
	], 
)

```

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
