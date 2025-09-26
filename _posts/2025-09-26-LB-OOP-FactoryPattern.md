---
layout: post
categories:
  - 言語基礎
---

## 🧩 Factory Pattern？

オブジェクトをただただ作るだけのクラスを作ります。  
作ることだけに専念します。  
ただ、作るときに条件分岐が発生します。  
ゴールド、シルバー、プラチナなど、会員区分を判定する必要があります。  
それがアプリケーション全体に散らばらないように、ひとつの場所にまとめておきます。


---

## 🗒️ Sample Code - interface basics

```csharp
public enum MemberType

    {

        Silber,

        Gold,

        Platinum

    }

public static class MemberFactory

{

  

    public static IMember Create(MemberType member)

    {

        switch (member)

        {

            case MemberType.Silber:

                return new SilberMember();

            case MemberType.Gold:

                return new GoldMember();

            case MemberType.Platinum:

                return new PlatinumMember();

            default:

                return new SilberMember();

        }

    }

}

class Program
{
    var money = new Money(100m);

  

        string input = Console.ReadLine();

        MemberType memberType = MemberType.Silber;

  

        switch (input)

        {

            case "S":

                memberType = MemberType.Silber;

                break;

            case "G":

                memberType = MemberType.Gold;

                break;

            case "P":

                memberType = MemberType.Platinum;

                break;

            default:

                break;

        }

  

        LoginInfo.Member = MemberFactory.Create(memberType);

  

        Console.WriteLine($"{LoginInfo.Member.GetName()}: {(int)(money.Value) * LoginInfo.Member.Rate}");
}
```

