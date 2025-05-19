## Lesson 2-1 基本變數類型
```
C# 型別系統：
├── 值型別（Value Type）
│   ├── *整數型別（int, long, short, byte, sbyte, uint, ulong, ushort）
│   ├── *浮點數型別（float, double, decimal）
│   ├── *布林型別（bool）
│   ├── *字元型別（char）
│   ├── *結構（struct）
│   ├── 列舉（enum）
│
└── 參考型別（Reference Type）
    ├── *字串（string）
    ├── *類別（class）
    ├── 介面（interface）
    ├── 陣列（array）
    ├── 委派（delegate）
    ├── 物件（object）
```

#### 字串類型
##### char (value type):
| 型別 | 範圍              | 大小  |
|:-----|:-----------------|:------|
| char | U+0000 到 U+FFFF | 8 bit |
##### string (reference type):
1. 由多個char組成
2. 一旦建立後即無法修改
3. 若做運算，都將會回傳一個新的string
```
宣告範例:
string a = "abc";
string b = "cde";
string c = a + b;
Console.WriteLine("result:" + c);   //abccde
```
---

#### 布林(boolean)類型 (value type)
##### bool
1. 用於判斷邏輯
2. 只有 "true" 和 "false" 兩種結果
3. 運算子: &&, ||, &, |
4. !會變成反向
```
宣告範例:
1.一般宣告，搭配if else使用
bool result = 5 > 3
if(result)
    Console.WriteLine("true");
else
    Console.WriteLine("false");

2.
```
---

#### 數字類型 (value type)
##### 1. 整數類型(含正負號):

| 型別   | 值域                                                    | 大小   |
|:------|:--------------------------------------------------------|:-------|
| sbyte | -128 到 127                                             | 8 bit  |
| short | -32,768 至 32,767                                       | 16 bit |
| int   | -2,147,483,648 至 2,147,483,647                         | 32 bit |
| long  | -9,223,372,036,854,775,808 至 9,223,372,036,854,775,807 | 64 bit |
```
宣告範例:
1.一般宣告
int a = 1;

2.將string轉換成int
string inputA = Console.ReadLine();
int a = int.Parse(inputA);
```
   
##### 2. 整數類型(不含正負號):

| 型別    | 值域                            | 大小   |
|:-------|:--------------------------------|:-------|
| byte   | 0 至 255                        | 8 bit  |
| ushort | 	0 到 65,535                    | 16 bit |
| uint   | 0 到 4,294,967,295              | 32 bit |
| ulong  | 0 到 18,446,744,073,709,551,615 | 64 bit |
    
##### 3. 浮點數類型(含正負號)

| 型別      | 值域(大概值)                        | 精確度       | 大小     | 表示法 |
|:----------|:-----------------------------------|:------------|:--------|:---|
| float     | ±1.5 x 10^−45^ 到 ±3.4 x 10^38^    | ~6-9 位數    | 4 byte  | f |
| double    | ±5.0 × 10^−324^ 至 ±1.7 × 10^308^  | ~15-17 位數  | 8 byte  | d |
| decimal   | ±1.0 x 10^-28^ 到 ±7.9228 x 10^28^ | 28-29 位數   | 16 byte | m |
```
宣告範例:
float f = 1.0f;
double d = 1.0d;
decimal m = 1.0m;
```

算數運算子:+, -, *, /

---
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

參考來源:https://learn.microsoft.com/zh-tw/dotnet/csharp/language-reference/builtin-types/built-in-types
