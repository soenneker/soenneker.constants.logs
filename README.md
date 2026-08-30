[![](https://img.shields.io/nuget/v/soenneker.constants.logs.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.constants.logs/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.constants.logs/publish-package.yml?style=for-the-badge)](https://github.com/soenneker/soenneker.constants.logs/actions/workflows/publish-package.yml)
[![](https://img.shields.io/nuget/dt/soenneker.constants.logs.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.constants.logs/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.constants.logs/codeql.yml?label=CodeQL&style=for-the-badge)](https://github.com/soenneker/soenneker.constants.logs/actions/workflows/codeql.yml)

# Soenneker.Constants.Logs

Provides the conventional log-directory name and visual separator used by Soenneker logging components.

## Install

```bash
dotnet add package Soenneker.Constants.Logs
```

## Values

| Constant | Value | Intended use |
| --- | --- | --- |
| `LogsConstants.DefaultDirectory` | `"Logs"` | Relative directory name for log files |
| `LogsConstants.NewLineSeparator` | `"*************************************************"` | Visual separator for plain-text log output |

## Usage

```csharp
using Soenneker.Constants.Logs;

string logDirectory = Path.Combine(AppContext.BaseDirectory, LogsConstants.DefaultDirectory);
logger.LogInformation("{Separator}", LogsConstants.NewLineSeparator);
```

`DefaultDirectory` is relative; resolve it against an application-owned base path rather than assuming the process working directory. This package does not create directories, configure a logging provider, rotate files, or define retention.

These are compile-time constants, so their values are embedded into consuming assemblies. Rebuild consumers after upgrading if a value changes.
