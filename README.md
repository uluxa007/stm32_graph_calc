# Задание на курсовое проектирование
На основе клавиатуры с разъёмом PS/2 и LCD 320x240 реализовать построение графиков простейших функций - линейной, параболы, гиперболы, степенные. Ввод формулы осуществлять в одной верхней строке. Вводимые символы: 'X', '0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '=', '+', '-',  '/', '^'. Точность типа float. Координатная плоскость имеет диапазон значений от -8 до +8 по обеим осям. При вводе '=' сразу отображается график или сообщение об ошибке. Не указанные ограничения и форматы доопределить самостоятельно. По желанию, использовать вместо клавиатуры PS/2, Keypad 4x4.
# Техническое задание на прибор
Поскольку курсовое проектирование выполняется удаленно, то необходимо выполнить проект на симуляторе Proteus. Таким образом будем считать, что у нас подключено следующее оборудование:
- Keypad 4x4 подключенный к портам входы выхода PB0-PB7

![Иллюстрация к проекту](https://github.com/uluxa007/stm32_graph_calc/blob/main/images/keypad_4x4.png)

- Графический LCD дисплей с контроллером ST7735 подключенный по интерфейсу SPI

![Иллюстрация к проекту](https://github.com/uluxa007/stm32_graph_calc/blob/main/images/lcd.png)

Так же для удобства отладки подключим Virtual Terminal, получающий команды по UART и отображающий их в отдельном окне.

![Иллюстрация к проекту](https://github.com/uluxa007/stm32_graph_calc/blob/main/images/terminal.png)

Для реализации функционала калькулятора степенных функций, построим конечный автомат, который будем менять свои состояния сразу при нажатии кнопки.
Калькулятор будет строить функции вида

![Иллюстрация к проекту](https://github.com/uluxa007/stm32_graph_calc/blob/main/images/equation.png)

Все что до знака “/” будет числителем, а то что после – знаменателем.
Ограничим размер коэффициента перед Х до 2 знаков, а степень до 1 знака.
Для ввода каждого выражения определим 4 состояния:

![Иллюстрация к проекту](https://github.com/uluxa007/stm32_graph_calc/blob/main/images/states.png)

При нажатии кнопки “=” будет осуществляться расчет функции и переход в состояние вывода функции на экран. 

![Иллюстрация к проекту](https://github.com/uluxa007/stm32_graph_calc/blob/main/images/use_case.png)
# Основные требования





