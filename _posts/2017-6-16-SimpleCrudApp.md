---
layout: post
title: Simple CRUD Application with ASP.Net MVC
---

Hello guys! So what we're going to create is a very simple Create, Read, Update, and Delete ASP.Net Application. Since I'm just a junior web developer, the purpose of this is to share my knowledge which I learned through my On-the-Job Training. If you guys have any comments, corrections, reactions, and suggestions just send me a message on facebook or drop an email. Alright! Let's Get Started!.

**Requirements**

First you will need Visual Studio at least 2015 version, MS SQL Server at least 2016 version and of course Internet Connection cause we need to download Entity Framework package.

**The Structure**

![Initial_Setup]({{ site.baseurl }}/images/Initial_Setup.PNG)

**References** - This is the list of dependencies referenced to your project. Most of it are automatically referenced when we created the project and some will be referenced when we are going to download and install packages.

**App_Start Folder:**

**BundleConfig.cs** - handles all style and script bundles within the project.Some bundles are auto-generated whenever you create an MVC template. The reason behind this bundling is that you don’t have to rename your script or style whenever you modify them, you just need to create new bundle and include all needed files then include the bundle(s) in your views. Each of those files will have a new globally unique identifier (GUID) appended in its filename and will be minified.

**FilterConfig.cs** - basically a file which handles the built in and custom configurations that needs to be executed before or after an action method executes. But in this project we are not going to add any filters

**RouteConfig.cs** - sets how the routing is done within the project.

**Content Folder:**  
Contains css files that will be applied to our web application.

**Controllers Folder:**  
Consists of controller class created from its model. This is where we are going to our back end code like Post and Get actions.

**Models Folder:**  
Consists of classes where we will define our tables and fields.

**Scripts Folder:**  
Contains javascript files that will be applied to our project.

**Views Folder:**  
Contains all the html files which will be auto-generated after creating controllers.

**Web.Config**  
Simply enables you to add settings to your web application.


**Steps in creating the App**  

1.	Open Visual studio 2015 and navigate to File > New > Project. 
2.	Select Web > ASP.Net Web Application and name it “CrudApp”.
3.	Then choose MVC, uncheck “Host in the cloud”, click “Change Authentication” and tick “No Authentication”.
4.	Navigate to Tools > Nuget Package Manager > Manage Nuget Packages for Solution. Click “Browser” Tab and search for “entity framework”. Once displayed, select entity framework and tick CrudApp project in the right side and hit Install (*Check image below for reference). Or you could navigate to Tools > Nuget Package Manager > Package Manager Console and type “install-package entityframework”. You can always use console as long as you know the package name.
5.	Right click Model Folder > Add > Class and name it “Student”. 
6.	Create the following properties as you can see in the image below.  
![Student]({{ site.baseurl }}/images/StudentClass.PNG)  
7.	Then create new class under Models and name it “StudentDbContext” and create the following property and method as you can see in the image below.  
![StudentDbContext]({{ site.baseurl }}/images/context.PNG)  
8.  Find Web.Config and open it. Type the code below after AppSettings tag. If you are using windows authentication exclude user id and password otherwise you need to specify those.  
{% highlight csharp %}  
<connectionStrings>
    <add name="StudentDbContext" connectionString="data source=.\yoursqlserverinstance;initial catalog=StudentContext;user id=yourusernameiftheresany;password=yourpassiftheresany" providerName="System.Data.SqlClient"/>
</connectionStrings>  
{% endhighlight %}  
  
9. Now we need to enable migrations. Find Package Manager Console in the bottom left of visual studio and click it.  
10. Type the following commands:  
```
PM > enable-migrations (enter)
PM > add-migration CreateDatabase (enter)
PM > update-database (enter)
```  
10.  Right click Controllers folder > Add > Controller > MVC 5 Controller with views, using Entity Framework.  
11.  Click the arrow down icon in the right most part of the dropdown field Model Class and select Student.  
12.  Select StudentDbContext from the dropdown field Data Context Class and hit Add.
13.  Press F5 to run the app. You can access the page using the URL localhost:portnumber/Students, where portnumber is automatically given whenever you run the app so you only need to append "/Students" in the url.
