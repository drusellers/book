# Application Solution Structure
 Below is a large generalization of how I build my .Net Applications. This format has served me well with Clojure, Node, and Rust applications but it has seen the most use _and abuse_ with C#.

```
~/
  dev/
    <project-name>/
      packages/ //nuget
      lib/      //for non-nuget dependencies
        <product name>/
          <product>.dll
      src/
        Tests/ //solution folder
          Integration/
            sproc-tests/
            function-tests/
            fake-data/
            endeca/
              validators/
            *.csproj
          UnitTests/
            *.csproj
        <Project> //core
          Infrastructure/  //non business specific code like logging, etc
          *.csproj
        Hosts/ //solution dir
          Web/   //web site
            Content/
              js/
              css/
                <Compass generated CSS files>
              scss/
                *.scss
              images/
            *.csproj
          Host/ //windows service
            *.csproj
          Console/ //command line app
            *.csproj
      build.fsx
      endeca/
      db/
        <db name>/
            functions/
            permissions/
            runAfterOtherAnyTimeScripts/
            sprocs/
                <Schema>_SprocName.sql
            up/
                0001_<Schema>_Something.sql
                0002_<Schema>_Bob.sql
            views/
      <Project>.sln
      build.bat
      ci.bat
      README.md //meta data for the application
```

