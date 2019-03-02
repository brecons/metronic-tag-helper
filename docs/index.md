# Mecons Tag Helper

The Mecons Tag Helper Library comes with 30+ components, controls and UI widgets. Mecons provides a full [Keenthemes Metronic](http://keenthemes.com/metronic/) integration. Mecons is distributed as an enterprise library which can easily installed via NuGet.

---

## Supported Platforms

The Mecons Tag Helper Library is only available for ASP.NET Core Web Applications. The following target frameworks are supported:

Target Framework | Version | Target Framework Moniker (TFM)
--- | --- | ---
.NET Standard | 1.6 | `netstandard1.6`
.NET Standard | 2.0 | `netstandard2.0`

---

## Requirements

In order to use Mecons Tag Helper Library properly, you must meet certain requirements:

* [Visual Studio 2017](https://visualstudio.microsoft.com/de/downloads/) with the installed workloads *ASP.NET and web development* and *.NET Core cross-platform development*.
* [Metronic Admin Theme](https://themeforest.net/item/metronic-responsive-admin-dashboard-template/4021469)
* [Mecons Tag Helper Library](https://codecanyon.net/)

---

## Quickstart

For those in a hurry, here's a quickstart guide that allows you, as an advanced developer, to get started quickly with Mecons.

(1) Download the latest version of **Mecons Tag Helper Library** from [CodeCanyon](file:///C:/Git/mecons-tag-helper/Envato%20Package/docs/index.html).

(2) Download the latest version of **Metronic Admin Theme** from [ThemeForest](https://themeforest.net/item/metronic-responsive-admin-dashboard-template/4021469?ref=keenthemes).

(3) Open Visual Studio 2017 and create a new **ASP.NET Core Web Application**.

(4) Add the marked lines to `ConfigureServices` method in `Startup.cs`:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    services.AddSingleton<IHttpContextAccessor, HttpContextAccessor>();
    services.AddSingleton<IActionContextAccessor, ActionContextAccessor>();
}
```

(5) Copy the `assets` folder of your choosen Metronic Theme into `wwwroot` of the project.

(6) Copy the whole Metronic Theme markup of `index.html` into your layout page `/Views/Shared/_Layout.cshtml` and correct all css, image and javascript paths (e.g. into `~/assets/`).

(7) Place `@RenderBody()` method into layout page.

(8) Move all javascripts into the `<head>` of the layout page.

(9) Install Mecons NuGet Package with Package Manager Console:

    PM> Install-Package BSolutions.Mecons -Source C:\Downloads\<UNZIPPED MECONS FOLDER>\

(10) Add the marked lines to /Views/_ViewImports.cshtml:

```
@using MyCompany.MyApplication
@using MyCompany.MyApplication.Models
@using BSolutions.Mecons.Enumerations
@using BSolutions.Brecons.Core.Enumerations
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers
@addTagHelper *, BSolutions.Mecons
```