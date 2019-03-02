# Mecons Installation

In this article we'll install the Mecons Tag Helpers into a web application with included Metronic Admin Theme.

## Install NuGet Packages

Mecons Tag Helpers can easily installed via NuGet. Right click on the project folder and choose ***Manage NuGet Packages...*** to open the NuGet Package Manager.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/mecons-inst_01.png" width="580" alt="Manage NuGet Packages in Visual Studio">

In NuGet Package Manager search for `Mecons` package, choose it and click ***Install***. All necessary bin files and dependencies for Mecons will be installed.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/mecons-inst_02.png" width="914" alt="Mecons in NuGet Package Manager">

<div class="alert alert-warning" role="alert">
    <strong>Warning!</strong>
    Not every Mecons package is compatible with every Metronic version. For further information check the description of the selected package.
</div>

## Modify View Imports

It is mandatory to modify the `/Views/_ViewImports.cshtml` and enable the Mecons Tag Helpers for the web application views:

```markup
@using MyCompany.MyApplication
@using MyCompany.MyApplication.Models
@using BSolutions.Mecons.Enumerations
@using BSolutions.Brecons.Core.Enumerations
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers
@addTagHelper *, BSolutions.Mecons
```

Add the namespaces `BSolutions.Mecons.Enumerations` and the `BSolutions.Brecons.Core.Enumerations` with the `using` keyword and the `BSolutions.Mecons` tag helpers with the `addTagHelper` keyword.

## Add Mecons License

In the last step, the license file and the license key are to be included in the project.

### License File

Create a directory named `Mecons` within the project root. Copy the license file (e.g. `mecons-x-x-x.lic`) into this new directory:

* `MyCompany.MyApplication`
  * `/wwwroot`
  * `/Controllers`
  * `/Mecons`
    * `mecons-x-x-x.lic`
  * `/Models`
  * `/Views`

!!! Note

    Please make sure that the license file were copied to output directory on build. Right click on the license file and choose <em>Properties</em>. Select <code>Copy always</code> in the <em>Copy to Output Directory</em> menu.
    <img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/mecons-inst_03.png" width="603" alt="Change Properties of Mecons License File">

### License Key

The Mecons License Key can be set in the `Startup.cs` within the `ConfigureServices` method:

```csharp
using BSolutions.Mecons

...

public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();

    services.AddSingleton<IHttpContextAccessor, HttpContextAccessor>();

    // Mecons License
    MeconsInfo.SetLicense("XXXXX-XXXXX-XXXXX-XXXXX-XXXXX");
}
```

Thats all! Now you can build your project and use the Mecons Tag Helpers.