# Validation

Provide valuable, actionable feedback with Mecons Validation to your users with HTML5 form validation. Use the Mecons Tag Helpers in combination with the default ASP.NET Core Validation mechanism to validate your forms easy and simple.

## Requirements

To enable the client-side validation in ASP.NET MVC Core in combination with Mecons, you have to load the [jquery-validation-unobtrusive](https://yarnpkg.com/en/package/jquery-validation-unobtrusive) package from [Yarn](https://yarnpkg.com).

<div class="alert alert-info">
    Yarn is a package manager and allows to use code from other developers. If you want to use Yarn, you need to install it first: https://yarnpkg.com/en/docs/install.
</div>

The easiest way to load the `jquery-validation-unobtrusive` package is to open a command prompt, switch to the `wwwroot` folder of your project and execute the following command:

```
yarn add jquery-validation-unobtrusive
```

After embedding the `jquery-validation-unobtrusive` package into your solution, add a reference within the `/Shared/_Layout.cshtml` page after the Metronic scripts:

```markup
<script src="~/node_modules/jquery-validation-unobtrusive/dist/jquery.validate.unobtrusive.js"></script>
```

## Data Binding Validation

All Mecons form controls supports the default [ASP.NET Core Validation](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-mvc-app/validation). It's possible to validate the form on client-side with [jQuery Validation](https://jqueryvalidation.org/) or after a postback on server-side.

For a **client-side** validation use data annotations in your view model and bind the properties to the form controls within your view. Mecons now renders the validation errors automatically in Metronic compatible styles.

A **server-side** validation will execute in the controller logic after a postback. Use the `ModelState` to check if the form data is valid or to add further validation errors.

***Please note:*** It is indispensable to check the [Form Configuration](https://www.brecons.net/Documentation/Mecons/Validation#form-configuration) attributes before using Mecons Validation.

### View Model

```csharp
public class RegisterViewModel
{
    [Display(Name = "User Name")]
    [Required]
    public string Name { get; set; }

    [Display(Name = "Password")]
    [Required]
    public string Password { get; set; }

    [Display(Name = "Confirm Password")]
    [Compare("Password")]
    public string PasswordConfirmation { get; set; }

    [Display(Name = "Country")]
    public int Country { get; set; }

    public List<SelectListItem> Countries { get; set; } = new List<SelectListItem>();

    public RegisterViewModel()
    {
        this.Countries.Add(new SelectListItem { Value = "0", Text = "Choose a country ..." });
        this.Countries.Add(new SelectListItem { Value = "1", Text = "Germany" });
        // Further countries ...
    }
}
```

### Controller

```csharp
public IActionResult Register()
{
    return View(new RegisterViewModel());
}

[HttpPost]
public IActionResult Register(RegisterViewModel model)
{
    // Server-side validation
    if(model.Country <= 0) ModelState.AddModelError("Country", "No country was selected.");

    // On validation errors go back to view
    if (!ModelState.IsValid) return View(model);

    return RedirectToAction("Success");
}
```

### View

<img src="/images/validation_01.png" width="438" alt="">

```markup
<form asp-action="Register" method="post" bc-validation="true">
    <form-group>
        <input type="text" asp-for="Name" />
    </form-group>
    <form-group>
        <input type="password" asp-for="Password" />
    </form-group>
    <form-group>
        <input type="password" asp-for="PasswordConfirmation" />
    </form-group>
    <form-group>
        <select asp-for="Country" asp-items="Model.Countries"></select>
    </form-group>
    <button type="submit"> Submit </button>
</form>
```

## Form Configuration `<form>`

### Validation

By default, the [ASP.NET Core Validation](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-mvc-app/validation) is enabled for all Mecons forms. That means that each control within the form renders a validation message on model error. To disable the validation for all controls within the form set the `bc-validation` attribute to `false`.

Furthermore it is possible to disable the validation on control level by setting the `bc-validation` to `false` for a specific control.

<img src="/images/validation_02.png" width="431" alt="">

```markup
<form asp-action="Register" bc-validation="true">
    ...
</form>
```