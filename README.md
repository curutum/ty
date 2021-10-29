# Лабороторная работа 5 
### Задание 1 (32) ' Дано значение температуры T в градусах Цельсия. Определить значение этой же температуры в градусах Фаренгейта. Температура по Цельсию TC и температура по Фаренгейту TF связаны следующим соотношением: TC = (TF − 32)·5/9 '
   
    import random
    TC = random.randrange(-10,30)
    TF = TC*9/5+32
    print("Degrees Celsius = ", TC)
    print("Degrees Fahrenheit = ", round(TF,2))
### Задание 2 (22) 'С начала суток прошло N секунд (N — целое). Найти количество секунд, прошедших с начала последнего часа'

    import random
    N = random.randrange(0,86400)
    print("Число секунд: ", N)
    a = N%3600
    print("Секунды с последнего часа: ", a)
### Задание 3 (32) 'Даны целые числа a, b, c, являющиеся сторонами некоторого треугольника. Проверить истинность высказывания: «Треугольник со сторонами a, b, c является прямоугольным»'

    import random
    def TriangleInequality(A,B,C):
    return (A < B+C) and (B < A+C) and (C < A+B)
    a,b = [random.randrange(1, 7) for i in range(0,2)]
    c = random.randrange(5, 12)
    while not TriangleInequality(a,b,c):
    a,b = [random.randrange(1, 7) for i in range(0,2)]
    c = random.randrange(5, 12)
    #a,b,c = [5,3,4]
    print("Треугольник")
    print("Сторона a: ", a)
    print("Сторона b: ", b)
    print("Сторона c: ", c)
    bool_expr = ((a*a == b*b + c*c) or (b*b == a*a + c*c) or (c*c == b*b + a*a))
    print("Треугольник является прямоугольным: ",bool_expr)   
### Задание 4 (22) 'Даны координаты точки, не лежащей на координатных осях OX и OY. Определить номер координатной четверти, в которой находится данная точка'
    
    import random
    lst = [i for i in list(range(-10,11)) if i != 0]
    for i in range(0,5):
    x = random.choice(lst)
    y = random.choice(lst)
    print("\nТочка (x, y): ({0},{1})".format(x, y))
    print("Координатная четверть: ", end="")
    if x > 0 and y > 0:
        print("I")
    elif x < 0 and y > 0:
        print("II")
    elif x < 0 and y < 0:
        print("III")
    else:
        print("IV")
### Задание 5 (9) 'Даны два целых числа: D (день) и M (месяц), определяющие правильную дату невисокосного года. Вывести значения D и M для даты, следующей за указанной'
   
    import random
    M = random.randrange(1,13)
    month = {
    1: 31,
    2: 28,
    3: 31,
    4: 30,
    5: 31,
    6: 30,
    7: 31,
    8: 31,
    9: 30,
    10: 31,
    11: 30,
    12: 31
    }
    try:
    D_Max = month[M]
    D = random.randrange(1,D_Max+1)
    print("Дата:")
    print("Месяц: {0}. День: {1}".format(M,D))
    if D < D_Max:
        D += 1
    else:
        D = 1
        if M == 12:
            M = 1
        else:
            M +=1
    print("Следующая дата:")
    print("Месяц: {0}. День: {1}".format(M,D))
    except KeyError as e:
    print('Ошибка')
### Задание 6 (9) 'Даны два целых числа A и B (A < B). Найти сумму квадратов всех целых чисел от A до B включительно '

    import random
    A = random.randrange(5)
    n = random.randrange(5)+1
    B = A + n
    print('A = ', A)
    print('B = ', B)
    S = 0
    for i in range(A,B+1,1):
    S += i*i
    print(i," : ",i*i," : ",S)
    print("Sum of squares = ",S)
### Задание 6 (32) 'Дано целое число N (> 0). Последовательность вещественных чисел AK определяется следующим образом: A0 = 1, AK = (AK−1 + 1)/K, K = 1, 2, . . . . Вывести элементы A1, A2, . . . , AN '
