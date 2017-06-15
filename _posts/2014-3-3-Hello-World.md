---
layout: post
title: Simple CRUD Application with ASP.Net MVC
---

Hello guys! So what we're going to create is a very simple Create, Read, Update, and Delete ASP.Net Application. Since I'm just a junior web developer, the purpose of this is to share my knowledge which I learned through my On-the-Job Training. If you guys have any comments, corrections, reactions, and suggestions
just add me on facebook or drop an email. Alright! Let's Get Started!. 

Requirements

First you will need Visual Studio at least 2015 version, MS SQL Server at least 2016 version and of course Internet Connection cause we need to download Entity Framework package.

The Structure

![_config.yml]({{ site.baseurl }}/images/Initial_Setup.png)

References - This is the list of dependencies referenced to your project. Most of it are automatically referenced when we created the project and some will be referenced when we are going to download and install
packages.

App-Start Folder:

BundleConfig.cs - handles all style and script bundles within the project.Some bundles are auto-generated whenever you create an MVC template. The reason behind this bundling is that you don’t have to rename your script or style whenever you modify them, you just need to create new bundle and include all needed files then include the bundle(s) in your views. Each of those files will have a new globally unique identifier (GUID) appended in its filename and will be minified.

FilterConfig.cs - basically a file which handles the built in and custom configurations that needs to be executed before or after an action method executes. But in this project we are not going to add any filters

RouteConfig.cs - sets how the routing is done within the project. 

Content Folder:
  Contains css files that will be applied to our web application.

Controllers Folder:
  Consists of controller class created from its model. This is where we are going to our back end code like Post and Get actions.

Models Folder:
  Consists of classes where we will define our tables and fields.

Scripts Folder:
  Contains javascript files that will be applied to our project.

Views Folder:
  Contains all the html files which will be auto-generated after creating controllers.

WebConfig.cs
  Simply enables you to add settings to your web application.
