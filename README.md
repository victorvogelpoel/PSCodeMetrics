# PSCodeMetrics

A long time ago I was working on a hefty framework for a client to install a SharePoint 2013 farm from scratch onto 1-to-many servers remotely. That was fun, and I wanted to know how may modules, lines of code and comments we wrote.

```Measure-ScriptCode``` calculates metrics from PowerShell source files. For your curiosity, these are the metrics of that particular SharePoint installing framework:

```powershell
Files                : 189
Modules              : 8
Manifests            : 8
CodeLines            : 11704
Comments             : 3823
Functions            : 262
Workflows            : 8
Filters              : 1
Characters           : 559350
Lines                : 18773
Words                : 67540
```

The metrics are calculated using Abstract Syntax Tree (AST), which is part of the PowerShell language parser.

See my old [blogpost about Measure-ScriptCode](https://blog.victorvogelpoel.nl/2014/01/12/powershell-measure-scriptcode-calculating-script-code-metrics/) for more information about this function.

## Using ```Measure-ScriptCode```

Dot-source the function into the PowerShell Session:

```. .\measure-scriptcode.ps1```

and the function will be registered with the PowerShell session. And then provide the function with one or more powershell files:

``` powershell
PS> Measure-ScriptCode -ScriptFile "C:\PROJECTS-PERSONAL\PSCodeMetrics\Measure-ScriptCode.ps1"

Files       : 1
Modules     : 0
Manifests   : 0
CodeLines   : 80
Comments    : 14
Functions   : 1
Workflows   : 0
Filters     : 0
ParseErrors : 0
Characters  : 2555
Lines       : 111
Words       : 419

```

Last tested on Windows PowerShell 5.1.