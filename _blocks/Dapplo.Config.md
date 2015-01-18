---
layout: block
sort_id: 1
github_project: Dapplo.Config
appveyor_id: ujfvy3g49g6a1d1q
tags: work_in_progress
---

This repository contains a Microsoft Visual Studio solution for C# .NET with one dapplo building block project and a test case project which is used for testing the code and also serves as example code. The building block was created for containing the configuration of a .NET application with a configuration GUI in mind.

While writing Greenshot 2.x it was clear there are a lot of functions needed for writing a clean and user friendly GUI. Especially for writing extensions, it should be simple to extend the configuration for new coders.


Here are some of the requirements and their current status:

Simple
------
The code needs to be simple to use, which is the case: The developer needs to write an interface with all the needed properties and extend it with interfaces for functionality.
Status: <span class="glyphicon glyphicon-thumbs-up"/>

Basic properties
----------------
The properties of the interface are stored into a dictionary, which is automatically maintained by the proxy.
Status: <span class="glyphicon glyphicon-thumbs-up"/>

DefaultValue
------------
It should be possible to define a default value, so if none is set there is a sensible value. This is done by using the DefaultValueAttribute on the property.
Status: <span class="glyphicon glyphicon-thumbs-up"/>

Extendible
----------
It should be possible to extend the proxy with new functionality, for this an interface and attribute is created:
* IPropertyProxyExtension
* ExtensionAttribute
Status: <span class="glyphicon glyphicon-thumbs-up"/>

INotifyPropertyChanged
----------------------
Everybody knows how much boring work it is to implement the INotifyPropertyChanged interface, especially if it needs to be possible to refactor it! With the proxy this is done automatically, just by extending the property interface with the INotifyPropertyChanged.
Status: <span class="glyphicon glyphicon-thumbs-up"/>

ITransactionalProperties
-------------
Usually it should be possible to *cancel* a settings GUI and have the old settings back. If the configuration framework doesn't support this, there is a lot of work to be done. In this case, the property interface only needs to be extended with another interface to get the functionality. The interface has 3 methods, which influence the behaviour:
* StartTransaction to start "caching" the values
* CommitTransaction to commit all cached values to the backing store
* RollbackTransaction to throw away all the cached values
Status: <span class="glyphicon glyphicon-thumbs-up"/>

Write protect
-------------
Don't allow any changes after setting a flag.
Status: <span class="glyphicon glyphicon-thumbs-up"/>

HasValue
--------
Sometimes one needs a way of checking if there is a value set.
Status: <span class="glyphicon glyphicon-thumbs-down"/>

Concurrency
-----------
The whole implementation should not cause exceptions or undefined states when using from multiple threads.
Status: <span class="glyphicon glyphicon-thumbs-down"/>

Validation / Ranges
-------------------
Some values need to be restricted, this could be done inside the properties.
Status: <span class="glyphicon glyphicon-thumbs-down"/>
