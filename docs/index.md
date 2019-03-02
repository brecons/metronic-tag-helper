# Getting Started

The Mecons Tag Helper Library comes with 30+ components, controls and UI widgets. Mecons provides a full [Keenthemes Metronic](http://keenthemes.com/metronic/) integration. Mecons is distributed as a enterprise library which can easily installed via NuGet. To activate the Tag Helper Library please buy a license for Mecons in our shop.

---

## Supported Platforms

The Mecons Tag Helper Library is only available for ASP.NET Core applications. The following target frameworks are supported:

Target Framework | Version | Target Framework Moniker (TFM) | Support
--- | --- | --- | ---
.NET Standard | 1.6 | `netstandard1.6` | Supported
.NET Standard | 2.0 | `netstandard2.0` | Supported

---

## Quickstart

1. Download the latest version of **Mecons Tag Helper Library** from [CodeCanyon](file:///C:/Git/mecons-tag-helper/Envato%20Package/docs/index.html).
2. Download the latest version of **Metronic Admin Theme** from [ThemeForest](https://themeforest.net/item/metronic-responsive-admin-dashboard-template/4021469?ref=keenthemes).
3. Open Visual Studio 2017 and create a new **ASP.NET Core Web Application**.
4. Add the marked lines to `ConfigureServices` method in <code><mark>Startup.cs</mark></code>:

    ```csharp hl_lines="4 5"
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
        services.AddSingleton<IHttpContextAccessor, HttpContextAccessor>();
        services.AddSingleton<IActionContextAccessor, ActionContextAccessor>();
    }
    ```