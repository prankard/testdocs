Platforms
=========

The original Robotlegs framework was dependant on it's platform for view management.

We've had to cut out some view management features in the vanilla bundle, and make it more expandable so you can add a platform.

The main benefits of having platform specific MVCS bundles are:

* Stage Sync, The context's life to by synced with with a view element and automatically call Initialize and Destroy methods.
* View Manager / Container Registy - The ability to have Root containers/views that define which context the view belongs to and find the rules of mediation / viewprocessor.
* Stage Crawler - To look through all view objects and attempt to mediate/process them upon the Context's initialization, incase they were alive before any rules had been assigned.
* Child Context - An automatic parental hierarchy allowing parents to give injection rules to children.

You can also add more features to each platform if required by adding your own Extensions if appropriate.

MVCSBundle
----------

The orignal bundle comes packed with MVCS allowing for one context.

**ConsoleLoggingExtension** - Gets our logging to log out to the console
**VigilanceExtension** - Converts logger.Warn() into Errors because we strive for perfection
**InjectableLoggerExtension** - Allows you to inject the logger for easy logging
**EventDispatcherExtension** - Makes our single message channel to communicate
**ModularityExtension** ... er useless?
**DirectCommandMapExtension** - Allows you to call command directly without events
**EventCommandMapExtension** - Ties events on the main channel to commands to be invoked
**LocalEventMapExtension** - Gives us local event map to we can easily remove lots of events listeners in the Mediator class
**ViewManagerExtension** - Allows us to call processes on views that get registered (MediatorMap  / ViewProcessorMap)
**MediatorMapExtension** - Allows us to tie multiple meditors to views
**ViewProcessorMapExtension** - Gives the user the ability to do anything else to views
**FallbackContainerConfig** - Sets up all views in the ViewManager to be processed by this config (allows for only one context)

UnityMVCSBundle
---------------

We've removed the Console Logging Extension, and have added the DebugLoggingExtension so the logger logs out to the correct console.

We've added UnityStageCrawler, which takes the contextview and searches through it's components in children after intialization to process any views that might have already awoken.

We've added a UnityParentFinder, which enables the ViewManager know who is parented to whom.

We've included the modularity extension.

We've added a UnityStateWatcher, which moniters the context view to know when it has initalized or been destroyed.

We've added View and EventView classes, to easily extend and to be Mediated.


From here
------------

* [Readme](../README.md)
	* [A Brief Overview](./ABriefOverview.md)
	* [Features](./Features.md)
	* [Platforms](./Platforms.md)
	* [Common Problems](./CommonProblems.md)
	* [The internals (how it all works)](./TheInternals.md)