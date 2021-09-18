# 重頭開始學習 Java (Java 基礎教學)

# [Java](https://zh.wikipedia.org/wiki/Java)? Coffee? or 米?

> 編程範型:	多重範式：物件導向（類別基礎）、結構化、指令式、泛型、
> 反射、並行計算
>
>
> 實作者:	甲骨文公司 (昇陽電腦系統)
> 面市時間:	1995年，​26年前
> 穩定版本: Java SE 16 2021年3月21日，​5個月前

Java(英式發音[ˈʤɑːvə],美式發音[ˈʤɑvə])是一種廣泛使用的電腦程式設計語言，擁有跨平台、物件導向、泛型程式設計的特性，廣泛應用於企業級Web應用開發和行動應用開發。

Java程式語言的風格十分接近C++語言。繼承了C++語言物件導向技術的核心，捨棄了容易引起錯誤的指標，以參照取代；移除了C++中的運算子重載和多重繼承特性，用介面取代；增加垃圾回收器功能。

昇陽電腦對Java語言的解釋是：「Java程式語言是個簡單、物件導向、分散式、解釋性、健壯、安全、與系統無關、可移植、高效能、多執行緒和動態的語言」。

Java不同於一般的編譯語言或直譯語言。它首先將原始碼編譯成位元組碼，再依賴各種不同平台上的虛擬機器來解釋執行位元組碼，從而具有「一次編寫，到處執行」的跨平台特性。

## Java 語法基礎 (範例的說明參考自: [語言技術：Java Gossip](https://openhome.cc/Gossip/Java/))
### 型態
#### 基本型態
> 在Java中的基本型態主要可區分為:
* 整數
* 位元組
* 浮點數
* 字元
* 布林

``` java
// 基本型態 //
// 整數
// short: -32768(-2^15) ~ 32767(2^15-1)
// 佔2個位元組: 16 bit
System.out.println("Short: " + Short.SIZE / BIT);

// int: -2,147,483,648(-2^31) ~ 2,147,483,647(2^31-1)
// 佔4個位元組: 32 bit
System.out.println("Integer: " + Integer.SIZE / BIT);

// long: -9,223,372,036,854,775,808(-2^63) ~ 9,223,372,036,854,775,807(2^63-1)
// 佔8個位元組: 64 bit
System.out.println("Long: " + Long.SIZE / BIT);

// 位元組
// byte: -128(-2^7) ~ 127(2^7-1)
// 佔1個位元組: 8 bit
System.out.println("Byte: " + Byte.SIZE / BIT);

// 浮點數: 主要用來儲存小數數值
// float浮點數（佔4個位元組: 32 bit）
System.out.println("Float: " + Float.SIZE / BIT);
// double浮點數（佔8個位元組: 64 bit）
System.out.println("Double: " + Double.SIZE / BIT);

// 字元: char 型態用來儲存'A'、'B'、'林'等字元符號。
char c = 'A';
System.out.println("c: " + c);

// 布林: boolean 型態可表示true與false，分別代表邏輯的「真」與「假」。
boolean bl = false;
System.out.println("bl: " + bl);
```

#### 變數
##### 定義個名稱並給個值:
> Java 通常使用 Camel case(駝峰式) 命名

``` java
// 變數
int i = 0;
System.out.println("i: " + i);
String myName = "nobody";
System.out.println("myName: " + myName);

// 如果在指定變數值之後，就不想再改變變數值, 可以在宣告變數時加上final限定
final double PI = 3.14;
System.out.println("PI: " + PI);
```

#### 運算子
> 與算術相關的運算子+、-、*、/,
> 也就是加、減、乘、除這類運算子，
> 另外%，稱為模數運算子或餘除運算子。

``` java
// 運算子
int n1 = 1;
int n2 = 2;
int n3 = 3;
System.out.println("sum: " + (n1 + n2 + n3));
```

### 流程控制
#### if..else、switch 條件式

``` java
// if..else
int score = 85;
char level = 'A';

if (score > 90) {
    System.out.println("You got A");
} else if (score > 80) {
    System.out.println("You got B");
    level = 'B';
} else if (score > 70) {
    System.out.println("You got C");
    level = 'C';
} else if (score > 60) {
    System.out.println("You got D");
    level = 'D';
} else {
    System.out.printf("You got F");
    level = 'F';
}

// switch 條件式
switch (level) {
    case 'A':
        System.out.println("You are great");
        break;
    case 'B':
        System.out.println("Not bad");
        break;
    default:
        System.out.println("Keep going");
}
```

#### for、while 迴圈
> 在Java中如果要進行重複性指令執行，可以使用for迴圈式:
> for(初始式; 執行結果必須是boolean的重複式; 重複式) {
>    陳述句;
>}

``` java
// for、while 迴圈
for (int j = 0; j < 10; j++) {
    System.out.print(j + " ");
}
System.out.println();
```

> while(條件式) {
>    陳述句;
>}
>

``` java
int x = 0;
while (x < 10) {
    System.out.print(x + " ");
    x++;
}
System.out.println();
```

#### break、continue
> break可以離開目前switch、for、while、do..while的區塊
>
> continue作用與break類似，不過使用於迴圈，break會結束區塊執行，
> 而continue只會略過之後陳述句，並回到迴圈區塊開頭進行下一次迴圈，而不是離開迴圈。

``` java
// continue
for (int j = 0; j < 10; j++) {
    if (j == 4) {
        break;
    }
    System.out.print(j + " ");
}
System.out.println();

// continue
for (int j = 0; j < 10; j++) {
    if (j == 4) {
        continue;
    }
    System.out.print(j + " ");
}
System.out.println();
```

## 認識物件
### 類別與物件
* [定義類別](https://openhome.cc/Gossip/Java/Class.html)
* [陣列物件](https://openhome.cc/Gossip/Java/Array.html)
* [字串物件](https://openhome.cc/Gossip/Java/String.html)

## Java 物件導向
> 封裝、繼承、多型 … 以及用 Java 實現 …

### 封裝
#### [封裝物件初始流程](https://openhome.cc/Gossip/Java/EncapsulateInitialization.html)
> 在Java中可使用class關鍵字進行定義

``` java
package com.my;

class Person {
    String name;
    int height;
    int weight;
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.name = "nobody";
        person.height = 170;
        person.weight = 65;

        System.out.println(person.name);
        System.out.println(person.height);
        System.out.println(person.weight);
    }
}
```

> Java中可以定義建構式（Constructor）

``` java
package com.my;

class Person {
    String name;
    int height;
    int weight;

     /**
     * Constructor
     * @param name
     * @param height
     * @param weight
     */
    public Person(String name, int height, int weight) {
        this.name = name;
        this.height = height;
        this.weight = weight;
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person("nobody", 170,65);

        System.out.println(person.name);
        System.out.println(person.height);
        System.out.println(person.weight);
    }
}
```

#### [封裝物件操作流程](https://openhome.cc/Gossip/Java/EncapsulateOperation.html)
> 在Java中，你可以定義方法（Method）

``` java
/**
 * Set name
 * @param name
 */
public void setName(String name) {
    this.name = name;
}

/**
 * Get name
 * @return name
 */
public String getName() {
    return this.name;
}
```

#### [封裝物件內部資料](https://openhome.cc/Gossip/Java/EncapsulatePrivateMember.html)
> 如果有些資料是類別所私有，在Java中可以使用private關鍵字定義

``` java
package com.my;

class Person {
    private String name;
    private int height;
    private int weight;

    /**
     * Constructor
     * @param name
     * @param height
     * @param weight
     */
    public Person(String name, int height, int weight) {
        this.name = name;
        this.height = height;
        this.weight = weight;
    }

    /**
     * Set name
     * @param name
     */
    public void setName(String name) {
        this.name = name;
    }

    /**
     * Get name
     * @return name
     */
    public String getName() {
        return this.name;
    }

    /**
     * Set height
     * @param height
     */
    public void setHeight(int height) {
        this.height = height;
    }

    /**
     * Get height
     * @return height
     */
    public int getHeight() {
        return this.height;
    }

    /**
     * Set weight
     * @param weight
     */
    public void setWeight(int weight) {
        this.weight = weight;
    }

    /**
     * Get weight
     * @return weight
     */
    public int getWeight() {
        return this.weight;
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person("nobody", 170,65);

        person.setName("nobody2");
        System.out.println(person.getName());
        System.out.println(person.getHeight());
        System.out.println(person.getWeight());
    }
}
```

### 繼承與多型
#### [繼承共同實作](https://openhome.cc/Gossip/Java/Inheritance.html)
> 繼承基本上就是避免多個類別間重複定義了相同的實作。

#### [多型與 is-a 關係](https://openhome.cc/Gossip/Java/Polymorphism-is-a.html)
> 在Java中，子類別只能繼承一個父類別，繼承除了可避免類別間重複的實作定義外，還有個重要的關係，那就是子類別與父類別間會有is-a的關係，中文稱為「是一種」的關係，這是什麼意思？以先前範例來說，SwordsMan繼承了Role，所以SwordsMan是一種Role（SwordsMan is a Role），Magician繼承了Role，所以Magician是一種Role（Magician is a Role）。

#### [重新定義實作](https://openhome.cc/Gossip/Java/Override.html)
#### [抽象方法、抽象類別](https://openhome.cc/Gossip/Java/Abstract.html)
> 類別中若有方法沒有實作，並且標示為abstract，表示這個類別定義不完整，定義不完整的類別就不能用來生成實例，這就好比設計圖不完整，不能用來生產成品一樣。
>
> 子類別如果繼承抽象類別，對於抽象方法有兩種作法，一種作法是繼續標示該方法為abstract（該子類別因此也是個抽象類別，必須在class前標示abstract），另一個作法就是實作抽象方法。如果兩個作法都沒實施，就會引發編譯錯誤

### 介面與多型
#### [介面定義行為](https://openhome.cc/Gossip/Java/Interface.html)
#### [行為的多型](https://openhome.cc/Gossip/Java/Polymorphism-interface.html)
#### [解決需求變化](https://openhome.cc/Gossip/Java/Refactor.html)

### 介面語法細節
#### [介面的預設](https://openhome.cc/Gossip/Java/InterfaceSyntax.html)
#### [匿名內部類別](https://openhome.cc/Gossip/Java/AnonymousInnerClass.html)

## 例外處理
#### [使用 try、catch](https://openhome.cc/Gossip/Java/TryCatch.html)
#### [例外繼承架構](https://openhome.cc/Gossip/Java/ThrowableHierarchy.html)
#### [要抓還是要拋？](https://openhome.cc/Gossip/Java/Throw.html)
#### [貼心還是造成麻煩？](https://openhome.cc/Gossip/Java/CheckedException.html)
#### [認識堆疊追蹤](https://openhome.cc/Gossip/Java/StackTrace.html)
#### [關於 assert](https://openhome.cc/Gossip/Java/Assert.html)