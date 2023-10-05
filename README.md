# AYA-1
## Laboratory work I
Цели работы:
1. Научиться работать с переменными разных типов данных CTS
средствами языка C#.
2. Научиться создавать классы и поля классов, инициализировать
свойства классов. Научиться создавать перегруженные
конструкторы классов.
3. Научиться создавать тесты для реализованных методов и классов.

 ## Tasks 1
Выведите на консоль минимальные и максимальные значения для
предопределенных типов данных CTS.

код:
 ```sh
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine($"Минимальное значение для типа byte: {byte.MinValue}");
        Console.WriteLine($"Максимальное значение для типа byte: {byte.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа sbyte: {sbyte.MinValue}");
        Console.WriteLine($"Максимальное значение для типа sbyte: {sbyte.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа short: {short.MinValue}");
        Console.WriteLine($"Максимальное значение для типа short: {short.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа ushort: {ushort.MinValue}");
        Console.WriteLine($"Максимальное значение для типа ushort: {ushort.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа int: {int.MinValue}");
        Console.WriteLine($"Максимальное значение для типа int: {int.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа uint: {uint.MinValue}");
        Console.WriteLine($"Максимальное значение для типа uint: {uint.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа long: {long.MinValue}");
        Console.WriteLine($"Максимальное значение для типа long: {long.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа ulong: {ulong.MinValue}");
        Console.WriteLine($"Максимальное значение для типа ulong: {ulong.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа float: {float.MinValue}");
        Console.WriteLine($"Максимальное значение для типа float: {float.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа double: {double.MinValue}");
        Console.WriteLine($"Максимальное значение для типа double: {double.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа decimal: {decimal.MinValue}");
        Console.WriteLine($"Максимальное значение для типа decimal: {decimal.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа char: {char.MinValue}");
        Console.WriteLine($"Максимальное значение для типа char: {char.MaxValue}");

        Console.WriteLine($"Минимальное значение для типа bool: {bool.FalseString}");
        Console.WriteLine($"Максимальное значение для типа bool: {bool.TrueString}");

        Console.ReadLine();
    }
}
 ```
Результат работы программы:
```sh
Минимальное значение для типа byte: 0
Максимальное значение для типа byte: 255
Минимальное значение для типа sbyte: -128
Максимальное значение для типа sbyte: 127
Минимальное значение для типа short: -32768
Максимальное значение для типа short: 32767
Минимальное значение для типа ushort: 0
Максимальное значение для типа ushort: 65535
Минимальное значение для типа int: -2147483648
Максимальное значение для типа int: 2147483647
Минимальное значение для типа uint: 0
Максимальное значение для типа uint: 4294967295
Минимальное значение для типа long: -9223372036854775808
Максимальное значение для типа long: 9223372036854775807
Минимальное значение для типа ulong: 0
Максимальное значение для типа ulong: 18446744073709551615
Минимальное значение для типа float: -3,402823E+38
Максимальное значение для типа float: 3,402823E+38
Минимальное значение для типа double: -1,79769313486232E+308
Максимальное значение для типа double: 1,79769313486232E+308
Минимальное значение для типа decimal: -79228162514264337593543950335
Максимальное значение для типа decimal: 79228162514264337593543950335
Минимальное значение для типа char:
Максимальное значение для типа char: ?
Минимальное значение для типа bool: False
Максимальное значение для типа bool: True
```

 ## Tasks 2
 Создайте класс с именем Rectangle.
В теле класса создайте два поля, описывающие длины сторон double
side1, side2.
Создайте пользовательский конструктор Rectangle(double sideA, double
sideB), в теле которого поля sideA и sideB инициализируются
значениями аргументов.
Создайте два private метода, вычисляющие площадь прямоугольника -
double
CalculateArea() и периметр прямоугольника - double
CalculatePerimeter ().
Создайте два свойства double Area и double Perimeter с одним методом
доступа get, вызывающим созданные ранее методы.
Напишите программу, которая принимает от пользователя длины двух
сторон прямоугольника и выводит на экран периметр и площадь.
Покройте тестами методы класса Rectangle.


Код:
```sh
using System;

class Rectangle
{
    private double side1;
    private double side2;

    public Rectangle(double sideA, double sideB)
    {
        side1 = sideA;
        side2 = sideB;
    }

    private double CalculateArea()
    {
        return side1 * side2;
    }

    private double CalculatePerimeter()
    {
        return 2 * (side1 + side2);
    }

    public double Area
    {
        get { return CalculateArea(); }
    }

    public double Perimeter
    {
        get { return CalculatePerimeter(); }
    }
}

class Program
{
    static void Main()
    {
        Console.WriteLine("Введите длину стороны A прямоугольника:");
        double sideA = double.Parse(Console.ReadLine());

        Console.WriteLine("Введите длину стороны B прямоугольника:");
        double sideB = double.Parse(Console.ReadLine());

        Rectangle rectangle = new Rectangle(sideA, sideB);

        Console.WriteLine($"Площадь прямоугольника: {rectangle.Area}");
        Console.WriteLine($"Периметр прямоугольника: {rectangle.Perimeter}");

        Console.ReadLine();
    }
}

```

Результат работы программы:
```sh
Введите длину стороны A прямоугольника:
3
Введите длину стороны B прямоугольника:
2
Площадь прямоугольника: 6
Периметр прямоугольника: 10
```

 ## Tasks 3
 Создайте классы Point и Figure.
Класс Point должен содержать два целочисленных поля с координатами
точки.
Создайте два свойства с одним методом доступа get.
Создайте пользовательский конструктор, в теле которого
проинициализируйте поля значениями аргументов.
Класс Figure должен содержать конструкторы, которые принимают от
3-х до 5-ти аргументов типа Point, а также строковое автосвойство для
хранения названия фигуры.
Создайте два метода: double LengthSide(Point A, Point B), который
рассчитывает длину стороны многоугольника; void PerimeterCalculator(),
который рассчитывает периметр многоугольника.
Напишите программу, которая выводит на экран название и периметр
многоугольника. Покройте тестами методы класса Figure.
Примечание:
Избегайте повторения кода при реализации перегруженных конструкторов, используйте реализованные ранее
конструкторы с помощью ключевого слова this, например, так:

Код:
```sh
using System;

class Point
{
    private int x;
    private int y;

    public Point(int x, int y)
    {
        this.x = x;
        this.y = y;
    }

    public int X
    {
        get { return x; }
    }

    public int Y
    {
        get { return y; }
    }
}

class Figure
{
    private Point[] points;
    private string name;

    public Figure(Point point1, Point point2, Point point3)
    {
        points = new Point[] { point1, point2, point3 };
        name = "Треугольник";
    }

    public Figure(Point point1, Point point2, Point point3, Point point4)
    {
        points = new Point[] { point1, point2, point3, point4 };
        name = "Четырехугольник";
    }

    public Figure(Point point1, Point point2, Point point3, Point point4, Point point5)
    {
        points = new Point[] { point1, point2, point3, point4, point5 };
        name = "Пятиугольник";
    }

    private double LengthSide(Point A, Point B)
    {
        return Math.Sqrt(Math.Pow((B.X - A.X), 2) + Math.Pow((B.Y - A.Y), 2));
    }

    public void PerimeterCalculator()
    {
        double perimeter = 0;
        for (int i = 0; i < points.Length - 1; i++)
        {
            perimeter += LengthSide(points[i], points[i + 1]);
        }
        perimeter += LengthSide(points[points.Length - 1], points[0]);

        Console.WriteLine($"Название фигуры: {name}");
        Console.WriteLine($"Периметр фигуры: {perimeter}");
    }
}

class Program
{
    static void Main()
    {
        Point point1 = new Point(0, 0);
        Point point2 = new Point(0, 5);
        Point point3 = new Point(5, 0);

        Figure triangle = new Figure(point1, point2, point3);
        triangle.PerimeterCalculator();

        Console.ReadLine();
    }
}
```

Результат работы программы
```sh
Название фигуры: Треугольник
Периметр фигуры: 17,0710678118655
```
