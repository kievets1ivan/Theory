# Generic vs Non-generic

## �������� ������

[���������� ���� � ����� ��� �����](https://metanit.com/sharp/tutorial/3.12.php)

� ��� �������: generic and non-generic collection in C#?

## Generic Collection 

* **������ Generic Collection ��������� � System.Collections.Generics namespace.**

* **Generic Collection ������ ������������.**

* **Generic Collections ������ �������� ������ �������� �� ����������� �����.**

## Non-Generic Collection 

* **������ Non-Generic Collection ��������� � System.Collections namespace.**

* **Non-Generic Collection �� �������� ������ ������������.**

* **Non-Generic Collection ������ �������� ������ �������� ��������, � ��� ����� ��������� ������ ������ ����.**

Generic Collections:List<T>, Dictionary<TKey,TValue>, SortedList<TKey,TValue>, Hashset<T>, Queue<T>, Stack<T> 

Non-Generic Collections: ArrayList, SortedList, Stack, Queue, Hashtable, BitArray

������ Generic Collection:

```csharp  
var list = new List<int>();

list.Add(10);
list.Add(20);
list.Add(30);

list.ForEach(i => Console.WriteLine(i));
```

������ Non-Generic Collection:

```csharp 
var list = new ArrayList();

list.Add(10);
list.Add("sad");
list.Add(true);

foreach(var i in list)
    Console.WriteLine(i);
```
## ���������� ������

������:
```csharp
        static void Main(string[] args)
        {


            int x = 7;
            int y = 25;
            Swap<int>(ref x, ref y);
            Console.WriteLine($"x={x}    y={y}");   // x=25   y=7

            string s1 = "hello";
            string s2 = "bye";
            Swap<string>(ref s1, ref s2);
            Console.WriteLine($"s1={s1}    s2={s2}"); // s1=bye   s2=hello

        }

        public static void Swap<T>(ref T x, ref T y)
        {
            T temp = x;
            x = y;
            y = temp;
        }
```

## ������ ����� �������� � Generic Collections?
� ������ ������ � Non-Generic Collections �� ������������ � ������ ��������� ��� �������� (boxing) � ���������� (unboxing).
�������� (boxing) ������������ �������������� ������� ��������� ���� (��������, ���� int) � ���� object. ��� �������� ������������ ����� CLR ���������� �������� � ������ ���� System.Object � ��������� ��� � ����������� ���� (����). ���������� (unboxing), ��������, ������������ �������������� ������� ���� object � ��������� ����. �������� � ���������� ����� � �������� ������������������, ��� ��� ������� ���� ����������� ����������� ��������������.