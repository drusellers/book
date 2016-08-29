# Library Solution Structure

```
#NO HOSTS
Tests/
  MAG.<LibName>.UnitTests/
  MAG.<LibName>.IntegrationTests/
MAG.<LibName>/
  Configuration/
    IConfiguration.cs based configuration models
  Extensions/
    All Extension classes. Be sure to `internal` any common methods
  Internal/
    All internal implementation details
  <Needed Interfaces and Base Objects>
  I<LibName>Marker.cs
```