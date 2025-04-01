double a = 0;
double b = 0;
double h = 0;
double x = 0;
double y = 0;
double m = 1000000;
double n = -1000000;
int z = 0;
double l = 0;
int c = 0;
Console.WriteLine("Введите начало координат a");
a = Convert.ToDouble(Console.ReadLine());
Console.WriteLine("Введите начало координат b");
b = Convert.ToDouble(Console.ReadLine());
while (b <= a)
{
    Console.WriteLine("b не может быть меньше a. Введите еще раз b");
    b = Convert.ToDouble(Console.ReadLine());
}
Console.WriteLine("Введите шаг h");
h = Convert.ToDouble(Console.ReadLine());
while (h == 0)
{
    Console.WriteLine("Шаг не должен равняться нулю. Введите снова шаг");
    h = Convert.ToDouble(Console.ReadLine());
}
Console.WriteLine($"При координатах отрезка [{a};{b}] и шагом {h} ");
Console.WriteLine("\n     Таблица значений     ");
Console.WriteLine("---------------------------------");
Console.WriteLine("        x        |       y       ");
for (x = a; x <= b; x += h)
{
    y = Math.Round(Math.Cos(x * x) + (Math.Sin(x) * Math.Sin(x)), 2);
    Console.WriteLine("---------------------------------");
    Console.WriteLine($"       {Math.Round(x, 2)}        |       {y}       ");
    if (y < m)
    {
        m = y;
    }
    if (y > n)
    {
        n = y;
    }
    if (c > 0)
    {
        if ((l < 0 && y > 0) || (l > 0 && y < 0))
        {
            z++;
        }
    }

    l = y;
    c++;
}
Console.WriteLine("---------------------------------");
Console.WriteLine($"Максимальное число = {n}, минимальное число = {m}");
Console.WriteLine($"Знаков изменено = {z}");
Console.WriteLine($"Количество точек = {c}");
