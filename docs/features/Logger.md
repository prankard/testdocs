
Logger
======

The logger is 


Getting a logger
----------------

Output Logs
-----------

So, you want to use the logs too? Cool. All you need is an ILogTarget.

The context has a LogManager, which manages all ILogTargets. The syntax is simple:

```csharp
public class LogToFile : ILogTarget
{
	public void asdf()
	{
		
	}
}
```

From here
------------

* [Readme](../../README.md)
	* [A Brief Overview](../ABriefOverview.md)
	* [Features](../Features.md)
		* [Context](./Context.md)
		* [Injector](./Injector.md)
		* [Global Event Dispatcher](./GlobalEventDispatcher.md)
		* [Mediators](./Mediators.md)
		* [Commands](./Commands.md)
		* [Guards](./Guards.md)
		* [Hooks](./Hooks.md)
		* [View Processor](./ViewProcessor.md)
		* [Logger](./Logger.md)
	* [Platforms](../Platforms.md)
	* [Common Problems](../CommonProblems.md)
	* [The internals (how it all works)](../TheInternals.md)