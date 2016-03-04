---
layout: block
sort_id: 2
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
Status: <span class="glyphicon glyphicon-ok"/>

Basic properties
----------------
The properties of the interface are stored into a dictionary, which are automatically maintained by the proxy.
Status: <span class="glyphicon glyphicon-ok"/>

DefaultValue
------------
It should be possible to define a default value, so if none is set there is a sensible value. This is done by using the System.ComponentModel.DefaultValueAttribute on the property.
Status: <span class="glyphicon glyphicon-ok"/>

Extendible
----------
It should be possible to extend the proxy with new functionality, for this an interface and attribute is created:
* IPropertyProxyExtension
* ExtensionAttribute
Status: <span class="glyphicon glyphicon-ok"/>

INotifyPropertyChanged
----------------------
Everybody knows how much boring work it is to implement the INotifyPropertyChanged interface, especially if it needs to be possible to refactor it! With the proxy this is done automatically, just by extending the property interface with the INotifyPropertyChanged.
Status: <span class="glyphicon glyphicon-ok"/>

ITransactionalProperties
-------------
Usually it should be possible to *cancel* a settings GUI and have the old settings back. If the configuration framework doesn't support this, there is a lot of work to be done. In this case, the property interface only needs to be extended with another interface to get the functionality. The interface has 3 methods, which influence the behaviour:
* StartTransaction to start "caching" the values
* CommitTransaction to commit all cached values to the backing store
* RollbackTransaction to throw away all the cached values
Status: <span class="glyphicon glyphicon-ok"/>

Write protect
-------------
Don't allow any changes after setting a flag. This can be done by extending your properties interface with IWriteProtectProperties<YourPropertiesInterface>, this way one can write protect properties and also check if they are write protected.
It is also possible to make the property read-only with the [ReadOnlyAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.readonlyattribute.aspx) which makes it unchangeable im code.
Status: <span class="glyphicon glyphicon-ok"/>

Tagging
-------
By having the possibility to tag properties with certain "tags", which can be checked, you can add your own functionality. An example would be to tag certain properties with "Expert", showing these in the UI only when someone enables expert features. Or tagging the properties with the needed rights to be able to change the properties.
Status: <span class="glyphicon glyphicon-ok"/>


Next there are some ideas for future extensions:

Configuration read/write
------------------------
Added support for reading & writing from the registry, ini files and JSON.
For certain types it should be possible to use the [DescriptionAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.descriptionattribute.aspx) and [CategoryAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.categoryattribute.aspx) as documentation
Properties with the [NonSerializedAttribute](https://msdn.microsoft.com/en-us/library/system.nonserializedattribute.aspx) should be ignored, values which don't pass validation also.
The property can be mapped to another property in JSON, Ini or the registry by using the [DisplayNameAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.displaynameattribute.aspx)
Status: <span class="glyphicon glyphicon-remove"/>


HasValue
--------
Sometimes one needs a way of checking if there is a value set.
Status: <span class="glyphicon glyphicon-remove"/>

Concurrency
-----------
The whole implementation should not cause exceptions or undefined states when using from multiple threads.
Status: <span class="glyphicon glyphicon-remove"/>

Validation / Ranges
-------------------
A configuration UI should have the possibility to validate the values, by storing the possible values in attributes it should be possible use this information in the UI.
Eventually it should be possible to use the [ValidationAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.validationattribute.aspx#inheritanceContinued) in the System.ComponentModel.DataAnnotations namespace, this way there is no need to create & learn new attributes.
Also the [IDataErrorInfo](https://msdn.microsoft.com/en-us/library/system.componentmodel.idataerrorinfo.aspx) should be implemented so validation error information can be shown in e.g. WPF 
Status: <span class="glyphicon glyphicon-remove"/>

Converter
---------
While using the properties with a .ini (or other string based configuration types) the values are converted string -> object while reading and object -> string while writing.
As not all types can be converted without additional code it should be easy to convert certain values without changing the code of this block, it is possible to specify the converter to use.
Specify the [TypeConverterAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.typeconverterattribute.aspx) to tell the framework what converter to use!
Status: <span class="glyphicon glyphicon-remove"/>
