# Localization

The Mecons Tag Helper supports multiple languages and are localized. This applies on the one hand to all texts and labels generated within a Tag Helper, but also to date and time outputs.

---

## Support

Currently the following languages are supported:

| Language | State | Available since |
--- | --- | ---
| English | Supported | Version 2.0.0
| German | Supported | Version 2.0.0
| French | Supported | Version 2.2.1
| Italian | Supported | Version 2.2.1

---

## Usage of Localization

To localize the Tag Helpers, Mecons uses the `CultureInfo` set in the <a href="https://docs.microsoft.com/de-de/dotnet/api/system.globalization.cultureinfo.currentculture?view=netcore-2.1">current thread</a>.

Use the following code snippet to modify the `CultureInfo` for the current thread:

```csharp
// Set current thread language to German
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

!!! Info
    For a complete list of all `CultureInfo` names, visit [https://msdn.microsoft.com/en-us/library/hh441729.aspx](https://msdn.microsoft.com/en-us/library/hh441729.aspx).

The `CultureInfo` for your ASP.NET Core web application is best set in the `Startup.cs` within the `Configure` method:

```csharp
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    ...

    // Language
    var cultureInfo = new CultureInfo("de-DE");
    CultureInfo.DefaultThreadCurrentCulture = cultureInfo;
    CultureInfo.DefaultThreadCurrentUICulture = cultureInfo;
}
```

!!! Note
    If Mecons can not find a suitable language file for the thread culture, the English language file will be used.