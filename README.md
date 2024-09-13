# Итоговая контрольная работа по основному блоку
## Задача
Написать программу, которая из имеющегося массива строк формирует новый массив из строк, длина которых меньше, либо равна 3 символам. Первоначальный массив можно ввести с клавиатуры, либо задать на старте выполнения алгоритма. При решении не рекомендуется пользоваться коллекциями, лучше обойтись исключительно массивами.

Примеры:
[“Hello”, “2”, “world”, “:-)”] → [“2”, “:-)”]
[“1234”, “1567”, “-2”, “computer science”] → [“-2”]
[“Russia”, “Denmark”, “Kazan”] → []

---

## Решение 
Ввод данных с клавиатуры в консоле был выделен в отдельную функцию.

```
string? ReadString(string msg)
{
System.Console.Write(msg);
return Console.ReadLine(); 
}
```
С помощью метода Split создаем массив из веденной строки.
И сразу же создаем второй массив который будет хранить необхадимые нам значения.

```
string[] mastr = str!.Split(", ");
string[] arrayf = new string[mastr.Length];
```

Далее создаем функцию PoiskN, которая находит необходимые нам элементы, с каличеством символов <=3, и записывать их в новый массив. 

```
void PoiskN(string[] array1, string[] array2)
{
    int count = 0;
    for (int i = 0; i < array1.Length; i++)
    {
    if(array1[i].Length <= 3)
        {
        array2[count] = array1[i];
        count++;
        }
    }
}
```

Функция PrintArray выводит получившийся массив на консоль

```
void PrintArray(string[] array)
{
    for (int i = 0; i < array.Length; i++)
    {
        Console.Write($"{array[i]} ");
    }
    Console.WriteLine();
}
```

Функция Main выглядит следующим образом

```
void Main()
{
string? str = ReadString("Введите массив символов через запятую и пробел: ");
string[] mastr = str!.Split(", ");
string[] arrayf = new string[mastr.Length];
System.Console.WriteLine(str);
PoiskN(mastr, arrayf);
PrintArray(arrayf);
}
```

---

Так же в папке с проектом присутсвует блок схема.