
Features In Detail
==============

#### [The Context](./features/Context.md)

The core framework for Robotlegs is the context. It's is a simple item designed for installing other code via the Install and Configure methods.
The context has a lifecycle phase, as in it can be initialized once, paused and resumed multiple times and finally destroyed.
If you have such a large application you can even add multiple contexts for different sections of the application and make the context communicate with each other on a different event dispatcher.

#### [Injector](./features/Injector.md)

Behind the context, supplying dependencies throughout the extensions is the Injector.
It's got lot of nifty features on how you want to provide values.

#### [Global Event Dispatcher](./features/GlobalEventDispatcher.md)

A messaging system of the Robotlegs framework. This provides data to mediators, models, services and even invokes commands with data.

#### [Mediators](./features/Mediators.md)

The view management system of Robotlegs with it's TypeMatcher and NamespaceMatcher allows you to mediate based on lots of conditions.

#### [Commands](./features/Commands.md)

The event command system allowing you to 'do' things in your application. Add Views, call services, update models, call parsers. If you can think of something re-usable to do, you should do it in these classes.

#### [Guards](./features/Guards.md)

Guards are tiny classes that simply Approve allowing other code to execute. We use it in the framework to allow Commands to be fired, Mediators to be created, and View Processors to be handled.

#### [Hooks](./features/Hooks.md)

Hooks are tiny classes that you can attach to the end of other executing code.
Like Guards, they are used in the framework after a Command has been fired, Mediator has been created and View Processors have been handled.

#### [View Processor](./features/ViewProcessor.md)

asdf

From here
------------

* [Readme](../README.md)
	* [A Brief Overview](./ABriefOverview.md)
	* [Features](./Features.md)
	* [Common Problems](./CommonProblems.md)
	* [The internals (how it all works)](./TheInternals.md)