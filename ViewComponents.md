# View Components

similar to partial views, allowing you to create reusable components with (or without) logic.  can return various content, including Razor views, JSON, or plain text. View components can be rendered synchronously or asynchronously. Finally, they can integrate with the dependency injection system of ASP.NET Core through constructor injection.

A view component

1- Renders a chunk rather than a whole response.

2- Includes the same separation-of-concerns and testability benefits found between a controller and view.

3- Can have parameters and business logic.

4- Is typically invoked from a layout page.

consists of two parts:

1- The class, typically derived from ViewComponent

2- The result it returns, typically a view.


### view component class

A view component class can be created by any of the following

Deriving from ViewComponent

Decorating a class with the [ViewComponent] attribute, or deriving from a class with the [ViewComponent] attribute

Creating a class where the name ends with the suffix ViewComponent


Invoke a view component directly from a controller
View components are typically invoked from a view, but they can be invoked directly from a controller method. While view components don't define endpoints like controllers, a controller action that returns the content of a ViewComponentResult can be implemented.

In the following example, the view component is called directly from the controller:

```
public IActionResult IndexVC(int maxPriority = 2, bool isDone = false)
{
    return ViewComponent("PriorityList",
        new { 
           maxPriority = maxPriority,
           isDone = isDone
        });
}
```
### Writing A Simple View Component

derive from the ViewComponent class,

are decorated with the [ViewComponent] attribute, or

have a name that ends with the "ViewComponent" suffix.


```
public class Navigation : ViewComponent
{

}
```

if we want to make the view component even more explicit by appending the "ViewComponent" suffix to the class name

```
[ViewComponent(Name = "Navigation")]
public class NavigationViewComponent : ViewComponent
{

}

```

special Invoke method that returns an IViewComponentResult to be rendered. 

public IViewComponentResult Invoke()
{
    return Content("Navigation");
}


### Rendering a View Component

Within our Razor views, we can use the Component helper and its Invoke method to render view components.

first argument (which is required) represents the name of the component, "Navigation"

remaining arguments (which are optional) represent parameters that our component's Invoke method might accept.

```
@Component.Invoke("Navigation")
```

We can get more compile-time safety by replacing the hardcoded string literal with a nameof() expression that references our view component's class name:

```
@Component.Invoke(nameof(Navigation))
```

In order for the Navigation class to be found, we'll have to add its namespace to the list of namespaces imported within all our Razor views.

```
@using ViewComponents.Components
```

### Returning Views from View Components

looks for a Razor view in these two locations:

1- Views/Shared/Components/{ComponentName}/Default.cshtml

2- Views/{ControllerName}/Components/{ComponentName}/Default.cshtml

simple view that renders a given list of navigation items:

If no explicit view name is specified, ASP.NET MVC 6 assumes the view to be named Default.cshtml. 

```
@model Navigation.ViewModel

<nav>
    <ul>
        @foreach (var navigationItem in Model.NavigationItems)
        {
            <li>
                <a href="@navigationItem.TargetUrl">@navigationItem.Name</a>
            </li>
        }
    </ul>
</nav>
```

create the view model classes for the navigation items and instantiate a view model that is then passed to the above Default.cshtml view.

```
public class Navigation : ViewComponent
{
    public class ViewModel
    {
        public IList<ItemViewModel> NavigationItems { get; }

        public ViewModel(IList<ItemViewModel> navigationItems)
        {
            NavigationItems = navigationItems;
        }
    }

    public class ItemViewModel
    {
        public string Name { get; }
        public string TargetUrl { get; }

        public ItemViewModel(string name, string targetUrl)
        {
            Name = name;
            TargetUrl = targetUrl;
        }
    }

    // ...
}
```

create an array of navigation items and pass it to a new view model instance

```
public IViewComponentResult Invoke()
{
    var navigationItems = new[]
    {
        new ItemViewModel("Home", Url.RouteUrl(RouteNames.Home)),
        new ItemViewModel("Contact", Url.RouteUrl(RouteNames.Contact)),
        new ItemViewModel("About", Url.RouteUrl(RouteNames.About))
    };

    var viewModel = new ViewModel(navigationItems);

    return View(viewModel);
}
```

created a extracted a simple RouteNames class that defines all route names, again using nameof

```
public static class RouteNames
{
    public const string About = nameof(About);
    public const string Contact = nameof(Contact);
    public const string Home = nameof(Home);
}
```

The Startup.Configure method also retrieves the route names from this class. Again, we get more compile-time safety for stringly-typed APIs and a much nicer IntelliSense experience

```
app.UseMvc(routes =>
{
    routes.MapRoute(RouteNames.Home, "", new { controller = "Home", action = "Index" });
    routes.MapRoute(RouteNames.About, "about", new { controller = "Home", action = "About" });
    routes.MapRoute(RouteNames.Contact, "contact", new { controller = "Home", action = "Contact" });
});
```

view components can be asynchronous

```
public async Task<IViewComponentResult> InvokeAsync()
{
    var navigationItems = await LoadNavigationItemsFromDatabase();
    var viewModel = new ViewModel(navigationItems);

    return View(viewModel);
}
```

call  Component.Invoke in our Razor

```
@await Component.InvokeAsync(nameof(Navigation))
```

### Dependency Injection Within View Components

```
public class Navigation : ViewComponent
{
    // Nested classes
    // ...

    private readonly IHostingEnvironment _environment;

    public Navigation(IHostingEnvironment environment)
    {
        _environment = environment;
    }

    public IViewComponentResult Invoke()
    {
        var navigationItems = new List<ItemViewModel>
        {
            new ItemViewModel("Home", Url.RouteUrl(RouteNames.Home)),
            new ItemViewModel("Contact", Url.RouteUrl(RouteNames.Contact)),
            new ItemViewModel("About", Url.RouteUrl(RouteNames.About))
        };

        if (_environment.IsDevelopment())
        {
            var debugItem = new ItemViewModel("Debug", "/debug");
            navigationItems.Add(debugItem);
        }

        var viewModel = new ViewModel(navigationItems);

        return View(viewModel);
    }
}
```