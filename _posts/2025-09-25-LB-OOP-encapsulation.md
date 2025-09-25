---
layout: post
categories:
  - 言語基礎
title: "[Udemy] カプセル化"
---

## 🧩 カプセル化(Encapsulation)とは？

| 使う側         | 使われる側                                                                |
| ----------- | -------------------------------------------------------------------- |
| Program     | Money                                                                |
| 読み取り専用として利用 | - privateで値を保持する。<br>- 値を書き換えるのはこのクラスのみ。<br>- ロジックが散らばらず、1か所に作業が収まる。 |


---

## 🗒️ Sample Code

```csharp
public class Money
{
	private readonly decimal _value;
    
    // constructor
    public Money(decimal value)
    {
	    _value = value;
    }
    
    public decimal Value
    {
	    get
	    {
		    return _value;
	    }
    }
    
    public decimal TaxValue
    {
	    get
	    {
		    return Value * 1.08m;
	    }
    }
}

public class Program
{
    static void Main(string[] args)
    {
	    Money money = new Money(100m);
	    Console.WriteLine($"{money.TaxValue}円");
    }
}
```

