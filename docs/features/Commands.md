
Commands
========

So commands are small classes that do things in Robotlegs.

You might be adding a view to your application, changing values in your model, calling a method on a service or even all three.

Let's go ahead and make one

```csharp
public class ExampleCommand : ICommand
{
	public void Execute()
	{
		Console.WriteLine("Executed");
	}
}
```

That's probably even too basic for a command. Again, like a lot of classes in Robotlegs. The command class doesn't have to implement ICommand. It just needs an execute method.

Mapping an event command
------------------------

With the IEventCommandMap we can map events that when dispatched onto the global event dispatcher will trigger a command. This is usually done (but not limited to) in an IConfig in the setup phase.

```csharp
eventCommandMap.Map(EventClass.Type.ACTION_1).ToCommand<ExampleCommand>();
```

You can also change the Execute method used for the command in the mapping phase

```csharp
eventCommandMap.Map(EventClass.Type.ACTION_1).ToCommand<ExampleCommand>().WithExecuteMethod("CustomMethodName");
```

And you can also use the WithGuards to prevent the command being invoked under certain conditions and add WithHooks to add extra functionality just before the command is executed. 

```csharp
eventCommandMap.Map(EventClass.Type.ACTION_1).ToCommand<ExampleCommand>().WithGuards<ExampleGuard>().WithHooks<ExampleHook>();
```

> Tip: Read the [Guards](./Guards.md) and [Hooks](./Hooks.md) documentation for more information


Invoking a command
------------------

So with an event mapped to a command. All you have to do to dispatch the event with the correct type on the global event dispatcher and it will be called.

```csharp
dispatcher.Dispatch(new EventClass(EventClass.Type.ACTION_1));
```

It's good to know that you can also invoke a command with the [DirectCommandMap TODO:LINK](./link.md) or if you don't like events with the [Signals TODO:EXTENSION](./link) extension instead.


Getting data in the command
---------------------------

So like the View when creating the mediator. An injection is made for the event that has invoked the event. So you can pass more data into the command.

Here is an example of the command injecting the event command and using that to populate a model.

```csharp
public class ExampleCommand : ICommand
{
	[Inject]
	public EventClass evt;

	[Inject]
	public ExampleModel model;

	public void Execute()
	{
		model.SetData(evt.customData);
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