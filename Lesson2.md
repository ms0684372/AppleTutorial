## Lesson 2

### 基本變數類型：

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
```
bool result = 5 > 3
if(result)
    Console.WriteLine("true");
else
    Console.WriteLine("false");
```
---

#### 數字類型 (value type)
##### 1. 整數類型(含正負號):

| 型別   | 範圍                                                    | 大小   |
|:------|:--------------------------------------------------------|:-------|
| sbyte | -128 到 127                                             | 8 bit  |
| short | -32,768 至 32,767                                       | 16 bit |
| int   | -2,147,483,648 至 2,147,483,647                         | 32 bit |
| long  | -9,223,372,036,854,775,808 至 9,223,372,036,854,775,807 | 64 bit |
```
宣告範例:
1.
int a = 1;

2.(string to int)
string inputA = Console.ReadLine();
int a = int.Parse(inputA);
```
   
##### 2. 整數類型(不含正負號):

| 型別    | 範圍                            | 大小   |
|:-------|:--------------------------------|:-------|
| byte   | 0 至 255                        | 8 bit  |
| ushort | 	0 到 65,535                    | 16 bit |
| uint   | 0 到 4,294,967,295              | 32 bit |
| ulong  | 0 到 18,446,744,073,709,551,615 | 64 bit |
    
##### 3. 浮點數類型(含正負號)

| 型別      | 大概範圍                            | 精確度       | 大小     | 表示法 |
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

參考來源:https://learn.microsoft.com/zh-tw/dotnet/csharp/language-reference/builtin-types/built-in-types
