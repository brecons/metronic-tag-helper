# Checkbox List

The `<checkbox-list>` tag helper is a wrapper for checkbox input elements. For a correct rendering it is necessary to embedding all checkboxes into a checkbox list.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/checkboxlist_01.png" width="174" alt="Mecons Checkbox List">

```markup
<checkbox-list bc-label="Default Checkboxes">
    <input type="checkbox" bc-label="Default" />
    <input type="checkbox" bc-label="Disabled" disabled />
    <input type="checkbox" bc-label="Checked" checked />
</checkbox-list>
```

## Configuration

### Inline

Checkboxes can rendered on the same horizontal row by adding the `bc-inline` attribute to the list wrapper.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/checkboxlist_02.png" width="328" alt="Inline Checkbox List">

```markup
<checkbox-list bc-inline="true">
    ...
</checkbox-list>
```

### Label

To set an label for the list of checkboxes use the `bc-label` attribute.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/checkboxlist_03.png" width="171" alt="Checkbox List Label">

```markup
<checkbox-list bc-label="Default Checkboxes">
    ...
</checkbox-list>
```

### Help

To set a help text for a list of checkboxes use the `bc-help` attribute.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/checkboxlist_04.png" width="334" alt="Checkbox List Help">

```markup
<checkbox-list bc-label="Inline Checkboxes" bc-help="Some help text goes here" bc-inline="true">
    ...
</checkbox-list>
```

### Items

To bind a list of items to a Checkbox List use the `bc-items` attribute. This attribute accepts an object of `List<SelectListItem>`.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/checkboxlist_05.png" width="161" alt="Checkbox List Items">

#### View

```markup
@model BSolutions.Mecons.Test.Models.DataBindingViewModel

<checkbox-list bc-label="Equipment" bc-items="Model.Equipments"></checkbox-list>
```

#### View Model
```csharp
public class DataBindingViewModel
{
    public List<SelectListItem> Equipments { get; set; } = new List<SelectListItem>();

    public DataBindingViewModel()
    {
        this.Equipments.Add(new SelectListItem { Value = "0", Text = "Laptop" });
        this.Equipments.Add(new SelectListItem { Value = "1", Text = "Smartphone" });
        this.Equipments.Add(new SelectListItem { Value = "2", Text = "PC" });
    }
}
```

## Data Binding

Model binding in ASP.NET Core MVC maps data from HTTP requests to action method parameters. With `asp-for` attribute of the Checkbox List it is possible to bind checked options to a model parameter.

### View

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/checkboxlist_06.png" width="161" alt="">

```markup
@model BSolutions.Mecons.Test.Models.DataBindingViewModel

<checkbox-list asp-for="Equipment" bc-items="Model.Equipments"></checkbox-list>
```

### View Model

```csharp
public class DataBindingViewModel
{
    // Selected Equipment
    [Display(Name = "Equipment")]
    public List<string> Equipment { get; set; }

    // Available Equipment
    public List<SelectListItem> Equipments { get; set; } = new List<SelectListItem>();
}
```

### Controller

```csharp
public IActionResult DataBinding()
{
    var model = new DataBindingViewModel();
    model.Equipments.Add(new SelectListItem { Value = "0", Text = "Laptop" });
    model.Equipments.Add(new SelectListItem { Value = "1", Text = "Smartphone" });
    model.Equipments.Add(new SelectListItem { Value = "2", Text = "PC" });
    
    return View(model);
}

[HttpPost]
public IActionResult DataBinding(DataBindingViewModel model)
{
    foreach(var equipment in model.Equipment)
    {
        // Do something with selected equipment
    }
}
```