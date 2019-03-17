# Bootstrapping Developers to work with me

1. Have them build a naive Dapper

```csharp
public class Sample
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public int Age { get; set; }
}

public class DapperTest
{
        var s =  new Sample { FirstName = "Vy", LastName = "Le", Age = 22 };
        var sql = ConvertToSql(s);
        sql.ShouldBe("UPDATE Sample SET FirstName = @FirstName, LastName = @LastName, Age = @Age")

        var params = ConvertToParams(obj);
        params.Count.ShouldBe(3);
        var firstParam = params.First();
        firstParam.ParameterName.ShouldBe("FirstName");
        firstParam.DbType.ShouldBe(DbType.String);
        firstParam.Value.ShouldBe("Vy");


        var lastParam = params.Skip(2).First();
        lastParam.ParameterName.ShouldBe("Age");
        lastParam.DbType.ShouldBe(DbType.Int32);
        lastParam.Value.ShouldBe(22);
    }

    public string ConvertToSql(Sample obj)
    {
        // TODO
    }

    public IList<IDbParam> ConvertToParams(Sample obj)
    {
        // TODO
    }
}
```

1. Have them build a naive NHibernate on top of the dapper
2. Have them build a naive IoC container
3. Make sure they understand type scanning

