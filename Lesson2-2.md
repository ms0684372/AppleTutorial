## Lesson 2-2 型別轉換

## 型別轉換
區分為兩種
- 隱含轉換(Implicit Conversion)
- 強制轉換(Explicit Conversion)

### 隱含轉換(Implicit Conversion)
值域小的轉為值域大的型別，稱為自動轉換或轉型(Convert)
```
short s = 100;
int i = s;
```

### 強制轉換(Explicit Conversion)
值域大轉值域小，或不同值域之間的轉換，稱為強制轉換或鑄型(Cast)
```
語法: 變數1 = (變數的型態)變數2;
```

```
錯誤寫法:
int i = 20;
short a = i; //Error，short值域比int小

正確寫法
int i = 20;
short a = (short)i;  //a: 20
```

##### 強制轉換的風險
- 可能造成資料流失或溢位

資料流失:浮點數轉整數後，小數點之後會直接捨棄
```
float f = 2.5f;
int i = (int)f;   //i: 2
```

溢位:超出值域
```
int i = 256;
byte b = (byte)i; //byte值域:0 ~ 255, b:0
```