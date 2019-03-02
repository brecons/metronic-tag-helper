# Getting Started

The Mecons Tag Helper Library comes with 30+ components, controls and UI widgets. Mecons provides a full [Keenthemes Metronic](http://keenthemes.com/metronic/) integration. Mecons is distributed as a enterprise library which can easily installed via NuGet. To activate the Tag Helper Library please buy a license for Mecons in our shop.

## Supported Platforms

The Mecons Tag Helper Library is only available for ASP.NET Core applications. The following target frameworks are supported:

<table class="table table-bordered table-striped">
    <thead>
        <tr>
            <th>Target Framework</th>
            <th>Version</th>
            <th>Target Framework Moniker (TFM)</th>
            <th>Support</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>.NET Standard</td>
            <td>1.6</td>
            <td><code>netstandard1.6</code></td>
            <td><span class="label label-danger">Not Supported</span></td>
        </tr>
        <tr>
            <td>.NET Standard</td>
            <td>2.0</td>
            <td><code>netstandard2.0</code></td>
            <td><span class="label label-success">Supported</span></td>
        </tr>
    </tbody>
</table>

## Quickstart

1. Download the latest version of **Mecons Tag Helper Library** from [CodeCanyon](file:///C:/Git/mecons-tag-helper/Envato%20Package/docs/index.html).
2. Download the latest version of **Metronic Admin Theme** from [ThemeForest](https://themeforest.net/item/metronic-responsive-admin-dashboard-template/4021469?ref=keenthemes).
3. Open Visual Studio 2017 and create a new **ASP.NET Core Web Application**.
4. Add the marked lines to `ConfigureServices` method in <code><mark>Startup.cs</mark></code>:

   ```csharp
   public void ConfigureServices(IServiceCollection services)
   {
       services.AddMvc();
       services.AddSingleton<IHttpContextAccessor, HttpContextAccessor>();
       services.AddSingleton<IActionContextAccessor, ActionContextAccessor>();
   }
