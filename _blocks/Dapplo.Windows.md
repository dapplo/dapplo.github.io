---
layout: block
sort_id: 3
github_project: Dapplo.Windows
appveyor_id: n99jafhbbp74n2w7
tags: work_in_progress
---

This repository contains a Microsoft Visual Studio solution for C# .NET with one dapplo building block project and a test case project which is used for testing the code and also serves as example code. The building block was created to simplify accessing native Windows.



Here are some of the requirements and their current status:

WindowsTitleMonitor
------
When using OAuth with desktop applications, it is hard to get the token from the OAuth service without embedding a Web-Browser. Google wrote [here](https://developers.google.com/accounts/docs/OAuth2InstalledApp) that "urn:ietf:wg:oauth:2.0:oob" can be used to have the authorization code returned in the title bar of the browser. The WindowsTitleMonitor should help here!
Status: <span class="glyphicon glyphicon-ok"/>

Native wrappers
----------------
Many native User32 Enumerations & Methods are available, documentation follows.
Status: <span class="glyphicon glyphicon-ok"/>

