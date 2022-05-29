# MVC-Forms

Views in ASP.NET Core MVC

view handles the app's data presentation and user interaction. A view is an HTML template with embedded Razor markup. Razor markup is code that interacts with HTML markup to produce a webpage that's sent to the client.

* Use layouts to provide consistent webpage sections and reduce code repetition. Layouts often contain the header, navigation and menu elements, and the footer.

* Partial views reduce code duplication by managing reusable parts of views. For example, a partial view is useful for an author biography on a blog website that appears in several views.

* View components are similar to partial views in that they allow you to reduce repetitive code, but they're appropriate for view content that requires code to run on the server in order to render the webpage.

### Benefits of using views

1- The app is easier to maintain because it's better organized. Views are generally grouped by app feature. This makes it easier to find related views when working on a feature.

2- The parts of the app are loosely coupled. You can build and update the app's views separately from the business logic and data access components. You can modify the views of the app without necessarily having to update other parts of the app.

3- It's easier to test the user interface parts of the app because the views are separate units.

4- Due to better organization, it's less likely that you'll accidentally repeat sections of the user interface.

Views that are specific to a controller are created in the Views/[ControllerName] folder. Views that are shared among controllers are placed in the Views/Shared folder

### How controllers specify views

use the View helper method to return the ViewResult:

```
public IActionResult About()
{
    ViewData["Message"] = "Your application description page.";

    return View();
}
```

The View helper method has several overloads. You can optionally specify:

An explicit view to return:
```
return View("Orders");
```

A model to pass to the view:

```
return View(Orders);
```

Both a view and a model:

```
return View("Orders", Orders);
```

Pass data to views
Pass data to views using several approaches:

* Strongly typed data: viewmodel
* Weakly typed data
  
   1- ViewData (ViewDataAttribute)
   
   2- ViewBag

### differences between ViewData and ViewBag

#### ViewData

Derives from ViewDataDictionary, so it has dictionary properties that can be useful, such as ContainsKey, Add, Remove, and Clear.

Keys in the dictionary are strings, so whitespace is allowed. Example: ViewData["Some Key With Whitespace"]

Any type other than a string must be cast in the view to use ViewData.

#### ViewBag

Derives from Microsoft.AspNetCore.Mvc.ViewFeatures.Internal.DynamicViewData, so it allows the creation of dynamic properties using dot notation (@ViewBag.SomeKey = \<value or object>), and no casting is required. The syntax of ViewBag makes it quicker to add to controllers and views.

Simpler to check for null values. Example: @ViewBag.Person?.Name


### CSS isolation

Isolate CSS styles to individual pages, views, and components to reduce or avoid:

* Dependencies on global styles that can be challenging to maintain.

* Style conflicts in nested content.

### Create Form

1. FORMS – WEAKLY TYPED

\<form action="form1" method=”post”>, form1 is Action Method that gets executed when forms sends data to HomeController using post method. In the next chapter, you will learn about post and get method in mvc.

In the \<input type="text" name="txtId" />, the property name=”txtId” must be same as parameter name in form 1 action method.

Advantage:

1. It is easy to create a form using Weakly Typed mechanism

2. Mostly used when you need to create a form with one or two input items.

Disadvantage:

1. Because, it is not strongly typed so IntelliSense doesn't help you.

2. Have higher chance of getting exception and runtime error messages.

3. Very difficult to manage when forms have multiple input items and controls.

4. It is very clumsy when you need to add or remove some input items.

2. FORMS : STRONGLY TYPED

we send objects (model) instead of sending each item as parameter. It is easy to maintain because you don't need to remember each input item and IntelliSense will show you automatically the each item.

3. FORMS - STRONGLY TYPED AJAX (ASYNCHRONOUS)

Asynchronous AJAX Forms simply post back the data to the controllers and update the only that part of the page, which has to display output.

a. Ajax.BeginForm is used for creating Asynchronous AJAX Forms.
b. Form3 is an Action method.
c. Home is a Controller name.
d. HttpMethod = “POST” denotes that data will be sent to server using POST method.
e. UpdateTargetId updates the area which will get updated and display output. In my program, \<h4 id="id1" style="color:purple">\</h4> will be updated and display output.
f. LoadingElementId display the loading image or loading message meanwhile AJAX is posting and retrieving data from models or controllers.
g. OnSuccess works when task completed successfully.
h. OnFailure works when task gets failed.

4. PURE HTML FORMS WITH AJAX AND JQUERY

 use html elements like \<p>…\</p>, \<span>…\</span> to send data to controllers. This is pure JQuery and AJAX query.









6. 
6. 
6. 

