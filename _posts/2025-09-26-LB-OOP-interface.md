---
layout: post
categories:
  - 言語基礎
---

## 🧩 インタフェース(Interface)？



---

## 🗒️ Sample Code - interface basics

```csharp
public interface IMember
{
    float Rate { get; }
}

public sealed class SilberMember : IMember
{
    public float Rate => 1.0f;
}
  

public sealed class GoldMember : IMember
{
    public float Rate => 0.8f;
}
  

public sealed class PlatinumMember : IMember
{
    public float Rate => 0.6f;
}

class Program
{
    static void Main(string[] args)
    {
        IMember member;
        var money = new Money(100m);

        string input = Console.ReadLine();

        switch (input)
        {
            case "S":
                member = new SilberMember();
                break;

            case "G":
                member = new GoldMember();
                break;

            case "P":
                member = new PlatinumMember();
                break;

            default:
                member = new SilberMember();    
                break;

        }
        Console.WriteLine((int)(money.Value) * member.Rate);
    }
}
```

