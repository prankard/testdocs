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

The vanilla bundle...

UnityMVCSBundle
---------------

What we've added...




From here
------------

* [Readme](../README.md)
	* [A Brief Overview](./ABriefOverview.md)
	* [Features in Detail](./FeaturesInDetail.md)
	* [Platforms](./Platforms.md)
	* [Common Problems](./CommonProblems.md)
	* [The internals (how it all works)](./TheInternals.md)