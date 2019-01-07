# Create new Project

This is the first article of the installation guide and describes how to create a new Mecons compatible ASP.NET Core Web Application.

## Create new ASP.NET Core Web Application

The first step is to create a new project in Visual Studio. Choose the ***Web*** rubric and subsequent the ***ASP.NET Core Web Application*** template. Adapt the project parameters like ***Name***, ***Location*** and ***Solution name*** and click ***OK***.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/getting-started_01.png" width="944" alt="New Project in Visual Studio">

In the following dialog choose the ***.NET Core*** Framework and the ***ASP.NET Core 2.0*** version as well as a project template. Optionally change the authentication and click ***OK***.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/getting-started_02.png" width="789" alt="Project Configuration in Visual Studio">

## Add Service Configuration

To ensure that Mecons runs correctly it is necessary to adapt the `Startup.cs`. Register inside the `ConfigureServices` method a singleton for the `IActionContextAccessor` and import the namespace `Microsoft.AspNetCore.Mvc.Infrastructure`.

```csharp
using Microsoft.AspNetCore.Mvc.Infrastructure

...

public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();

    services.AddSingleton<IActionContextAccessor, ActionContextAccessor>();
}
```

<div class="alert alert-warning" role="alert">
    <strong>Warning:</strong> If <code>IHttpContextAccessor</code> is not registered, an <code>InvalidOperationException</code> may occur:<br />
    <i>Unable to resolve service for type 'Microsoft.AspNetCore.Http.IHttpContextAccessor' while attempting to activate
    'YourCompany.YourProject.Controllers.YourController'.</i>
</div>