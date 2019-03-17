# Solution Structure

Below is a large generalization of how I build my .Net Applications. This format has served me well with Clojure, Node, and Rust applications but it has seen the most use _and abuse_ with C\#. I've based this structure on a lot of OSS.

## High level Structure

```text
~/
    packages/
    src/
    build/
    db/
    <Project>.sln
    build.bat
    ci.bat
    README.md
```

This is the basic setup. This divides the application into its major parts. `src` contains the actual source code of the project. `build` houses the scripts to automate source builds \(Note in languages like rust or dynamic languages this makes less sense. `db` contains the required files to version the database product for the application. The files `build.bat` and `ci.bat` are for the CI server and devs to use for building the source project. The final file `README.md` is a simple markdown file that helps a new dev get started with the project. The `packages` folder is for NuGet content. **DO NOT** check the `packages` folder into source control.

## Inside of src

```text
~/
    src/
        clients/
        hosts/
        tests/
        <core project>/
```

### Clients

This directory holds projects that expose client libraries to the overall solution. When building a webservice, we will also build a client library that can be shared internally. This way users of our services will not have to rewrite this code over and over.

### Hosts

This directory holds the process hosts. These are the actual computer entry points. An example one might look like:

```text
~/src/hosts/
    <ProjectName>.Cmd/
        Program.cs
    <ProjectName>.Web/
        Global.asax
```

The goal is to make these as slim and possible and devoid of as much business logic and application logic as possible.

### Tests

This directory holds all of the test projects.

```text
~/src/tests/
    Integration/
        <integration tests>.cs
    Unit/
        <unit tests>.cs
```

Unit tests should not need anything external to the project. They should all run quickly and stay green. They will be executed by the build server on every commit. The integration tests are going to need to access something out side the system itself. They will be run on the build server with every commit ideally, but could be run less often.

### Core Project

This is where the core code of the project lives. This is the Business Logic.

## Complete Picture

```text
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

