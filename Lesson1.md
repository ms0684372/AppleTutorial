## Lesson 1

### 這是一段C#程式碼的基本構成

```csharp
using System;  // 引用 System 命名空間

namespace AppleApp  // 自訂命名空間
{
    public class Program  // 定義一個class(類別)
    {
        // Main 方法是應用程式的入口點
        public static void Main()
        {
            Console.WriteLine("Hello, World!");  // 輸出訊息
        }
    }
}
```

### 接下來一行一行來看

#### using System;
引用System這個命名空間
1. using：
   - 一種指令，用來引用其他命名空間
1. System：
   - C#內建的命名空間
1. ;(分號)：
   - C#中很重要的語法符號，用來定義語句的結尾，可以想成是句點，少了這個的話，編譯器會無法辨識哪裡是句尾

---

#### namespace AppleApp
宣告一個叫做AppleApp的命名空間
1. namespace：(可以不宣告，但是會變很亂)
   - 宣告一個命名空間
2. AppleApp：
   - 自定義的命名空間名稱
3. {}(大括號)：
   - C#中很重要的語法符號，用來定義範圍

---

#### public class Program
宣告一個叫做Program的class，宣告class時一定要加存取修飾詞
1. public：
   - 存取修飾詞，表示公開的
   - 這邊先提一下他的好朋友有：
      - private：表示私有的，完全不對外公開
      - protected：存取限於包含類別或衍生自包含類別的型別
      - 其他的以後有機會再說
2. class：
   - 宣告一個類別
   - 可以宣告多層class，視情況使用。
3. Program：
   - 自定義的class名稱

---

#### public static void Main()
宣告一個叫做Main的公開且靜態的方法
⚠️**警告:** Main是一個應用程式的入口點，他必須要是靜態的
1. public：
   - 在宣告方法的時候，可加可不加，沒加存取修飾詞的話，預設會是private
   - 其他上面有提到了，就不重複講
2. static：
   - 靜態的，代表function或變數是屬於類別(class)的，而不是一個
3. void：
   - 回傳值，每個方法都一定要宣告回傳值，void代表沒有回傳東西
4. Main：
   - 自定義方法名稱(Main不算)

---

#### Console.WriteLine("Hello, World!");
> 輸出訊息，這是Console這個class的static方法
