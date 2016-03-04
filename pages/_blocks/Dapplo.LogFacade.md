---
layout: block
sort_id: 0
github_project: Dapplo.LogFacade
appveyor_id: 3ocr4r55ne8yiji0
tags: work_in_progress
---

# Dapplo.LogFacade
Glue code which allows your framework/library to log without a logger.

Ever written a framework? Well... I did, and one of the biggest problems I had was deciding on a logger framework.
Most of the time, I didn't use a logger as this would force the user to use or at least include the one I used.

So what does this project do? Well, it allows you NOT use a logger!
It makes it possible to add log statements which do nothing untill a logger is defined.

To you this, you add the nuget package.
Add the using statement to your class:
```
using Dapplo.LogFacade;
```

Include a static one-liner in your class:
```
private static readonly LogSource Log = new LogSource();
```

And wherever you want to write a log statement, you call:
```
Log.Info().WriteLine(message, params);
Log.Error().WriteLine(exception, message, params);
```

Where the Log is the static LogSource variable in your class, the method after this defines the log level and the WriteLine only specifies the information to log. There is a reason why this is defined like this:
- The LogSource captures the calling class (by using StackTrace) once, so you know where the log came from.
- The log level method is an extension method which defines the level, captures the calling method and line of the code. Available levels are:
  - Verbose
  - Debug
  - Info
  - Warn
  - Error
  - Fatal
- The WriteLine takes care of the arguments.
- All information is forgotten unless you define and assign a logger, this should pass all information to the logger you want to used.

Just so you can start using it, without having a log framework there are one or two loggers available.
TraceLogger, which uses the System.Diagnostics.Trace to write the formatted information to.
ConsoleLogger, which uses the Console to write the formatted information to.

So, where is the file logger? There is none, I wanted to keep it as simple as possible.
