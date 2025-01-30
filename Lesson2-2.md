## Lesson 2-2 基本變數類型(二)：

```
C# 型別系統：
├── 值型別（Value Type）
│   ├── 整數型別（int, long, short, byte, sbyte, uint, ulong, ushort）
│   ├── 浮點數型別（float, double, decimal）
│   ├── 布林型別（bool）
│   ├── 字元型別（char）
│   ├── *結構（struct）
│   ├── 列舉（enum）
│
└── 參考型別（Reference Type）
    ├── *類別（class）
    ├── 介面（interface）
    ├── 陣列（array）
    ├── 字串（string）
    ├── 委派（delegate）
    ├── 物件（object）
```

#### struct(結構體) (Value Type)
- 可否繼承:不能被繼承，只能實作interface
- 賦值:複製整個值(不影響原物件)
- 可否變更內容:不建議變更，建議在建構時就賦值
- 適用場合:小型物件，短生命週期的資料

##### 範例
``` C#
public struct Vector2
{
    public float x;
    public float y;
}

Vector2 a = new Vector2();
a.x = 10;
a.y = 20;

Vector2 b = a;
b.x = 11;

Console.WriteLine("a.x:" + a.x.ToString() + ", b.x:" + b.x.ToString() + b.x );
//輸出結果 a.x:10, b.x:11，a、b各自獨立，所以b改變後，a不會被影響
```

#### class(類別) (Reference Type)
- 可否繼承:支援繼承（可繼承其他 class）
- 賦值:複製物件記憶體位址(共用物件)
- 可否變更內容:可變動
- 適用場合:大型物件，長期存活的資料

##### 範例
``` C#
public class Person
{
    public string name;
    public int age;
}

Person personA = new Person();
personA.name = "Apple";
personA.age = 10;

Person personB = personA;
personB.age = 20;

//因為這兩個指到同一個記憶體位址，所以會影響到彼此
Console.WriteLine("A age:" + personA.age);  //20
Console.WriteLine("B age:" + personB.age);  //20
```