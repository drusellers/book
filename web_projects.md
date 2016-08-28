# Web Projects

> This is largely because of the way the current version of ASP.Net MVC is constructed.

> For the purposes of this discussion this is a project that is built in Visual Studio, targeting the .Net platform, to be hosted in IIS. In the larger solution, the path is something like ~/Hosts/<Proj>.Web/

> Please remember these sites will need to support CDN

```
~/
    Content/
        scripts/
        styles/
        images/
    Controllers/
        <Controller>Controller.cs
        Api/
            <Name>Controller.cs
    Views/
        <ControllerName>/
            <ActionName>.cshtml
```

## Versioned APIs

```
~/
    Controllers/
        <Controller>Controller.cs
        Api/
          v1/
            <ControllerName>/
              ApiModels/
                <ApiModel>.cs
              Validation/
                //validation classes
              <Name>Controller.cs
```