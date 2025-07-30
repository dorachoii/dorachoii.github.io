---
layout: post
categories:
  - 言語基礎
---

## 🧩 Interfaceとは？
- **`It distances the uses of a class from the implementation.`**

 → クラスの使い方を具体的な実装から切り離すことができます。つまり、「どう動くか」ではなく「何ができるか」に集中できる設計です。
　
- **`All operations defined by the interface must be implemented.`** 

→ インターフェースで定義されたすべての操作（メソッドやプロパティ）は、それを実装するクラス側で必ず定義しなければなりません。


---

## 🗒️ Code Snippet
- **`The syntax of an interface properties appear as the signature only and no body is provided.`**

```csharp
public interface ILanguage
{
    string LanguageName { get; set; }
    string Speak();
}

public class ItalianTaveller : ILanguage, ICloneable
{
    public string LanguageName { get; set; } = "Italiano";

    public string Speak()
    {
        return "Ciao mondo";
    }

    public object Clone()
    {
        ItalianTaveller it = new ItalianTaveller();
        it.LanguageName = this.LanguageName;
        return it;
    }
}
```

---

## 🎯 例題

[【Excercism】RemoteControlCompetition](https://exercism.org/tracks/csharp/exercises/remote-control-competition/edit)

```csharp
// TODO implement the IRemoteControlCar interface
public interface IRemoteControlCar{
    int DistanceTravelled {get;}
    void Drive();
}

public class ProductionRemoteControlCar: IRemoteControlCar, IComparable<ProductionRemoteControlCar>
{
    public int DistanceTravelled { get; private set; }
    public int NumberOfVictories { get; set; }

    public void Drive()
    {
        DistanceTravelled += 10;
    }

    public int CompareTo(ProductionRemoteControlCar other)
    {
        if(this.NumberOfVictories < other.NumberOfVictories){
            return -1;
        }else if(this.NumberOfVictories > other.NumberOfVictories){
            return 1;
        }else{
            return 0;
        }
    }
}

public class ExperimentalRemoteControlCar: IRemoteControlCar
{
    public int DistanceTravelled { get; private set; }

    public void Drive()
    {
        DistanceTravelled += 20;
    }
}

public static class TestTrack
{
    public static void Race(IRemoteControlCar car)
    {
        car.Drive();
    }

    public static List<ProductionRemoteControlCar> GetRankedCars(ProductionRemoteControlCar prc1,
        ProductionRemoteControlCar prc2)
    {
        var list = new List<ProductionRemoteControlCar> { prc1, prc2 };
        list.Sort(); 
        return list;
    }
}
```
