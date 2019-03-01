# Radio List

The `<radio-list>` tag helper is a wrapper for radio input elements. For a correct rendering it is necessary to embedding all radios into a radio list.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/radiolist_01.png" width="178" alt="Mecons Radio List">

```markup
<radio-list bc-label="Default Radiobuttons">
    <input type="radio" name="radio1" bc-label="Default" />
    <input type="radio" name="radio1" bc-label="Disabled" disabled />
    <input type="radio" name="radio1" bc-label="Checked" checked />
</radio-list>
```

## Configuration

### Inline

Radios can rendered on the same horizontal row by adding the `bc-inline` attribute to the list wrapper.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/radiolist_02.png" width="328" alt="Inline Radio List">

```markup
<radio-list bc-inline="true">
    ...
</radio-list>
```

### Label

To set a label for a list of radios use the `bc-label` attribute.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/radiolist_03.png" width="185" alt="Radio List Label">

```markup
<radio-list bc-label="Default Radios">
    ...
</radio-list>
```

### Help

To set a help text for a list of radios use the `bc-help` attribute.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/radiolist_04.png" width="343" alt="Radio List Help">

```markup
<radio-list bc-label="Inline Radios" bc-help="Some help text goes here" bc-inline="true">
    ...
</radio-list>
```

### Items

To bind a list of items to a Radio List use the `bc-items` attribute. This attribute accepts an object of `List<SelectListItem>`.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/radiolist_05.png" width="369" alt="Radio List Items">

#### View

```markup
@model BSolutions.Mecons.Test.Models.DataBindingViewModel

<radio-list bc-label="Character" bc-items="Model.Characters" bc-inline="true"></radio-list>
```

#### View Model

```csharp
public class DataBindingViewModel
{
    public List<SelectListItem> Characters { get; set; } = new List<SelectListItem>();

    public DataBindingViewModel()
    {
        this.Characters.Add(new SelectListItem { Value = "0", Text = "Calm" });
        this.Characters.Add(new SelectListItem { Value = "1", Text = "Bright" });
        this.Characters.Add(new SelectListItem { Value = "2", Text = "Lively" });
        this.Characters.Add(new SelectListItem { Value = "3", Text = "Crazy" });
    }
}
```

It is also possible to bind the values of an enumeration to a Radio List. Use the `Html.GetEnumSelectList<TEnum>()` method of the HtmlHelper class to return a select list for the given enum type.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/radiolist_06.png" width="204" alt="">

#### View

```markup
@model BSolutions.Mecons.Test.Models.DataBindingViewModel

<radio-list bc-label="Gender" bc-inline="true" bc-items="Html.GetEnumSelectList<Gender>()"></radio-list>
```

#### Enumeration

```csharp
public enum Gender
{
    [Display(Name = "Male")]
    Male,

    [Display(Name = "Female")]
    Female
}
```

## Data Binding

Model binding in ASP.NET Core MVC maps data from HTTP requests to action method parameters. With `asp-for` attribute of the Radio List it is possible to bind selected option to a model parameter.

### View

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/radiolist_07.png" width="304" alt="">

```markup
@model BSolutions.Mecons.Test.Models.DataBindingViewModel

<form-group>
<radio-list asp-for="Gender" bc-items="Html.GetEnumSelectList<Gender>()"></radio-list>
</form-group>
<form-group>
	<radio-list asp-for="Character" bc-items="Model.Characters"></radio-list>
</form-group>
```

### View Model

```csharp
public class DataBindingViewModel
{
    [Display(Name = "Gender")]
    public Gender Gender { get; set; }

    [Display(Name = "Character")]
    public string Character { get; set; }

    public List<SelectListItem> Characters { get; set; } = new List<SelectListItem>();
}
    
public enum Gender
{
    Male,
    Female
}
```

### Controller

```csharp
public IActionResult DataBinding()
{
	var model = new DataBindingViewModel();
    model.Characters.Add(new SelectListItem { Value = "0", Text = "Calm" });
    model.Characters.Add(new SelectListItem { Value = "1", Text = "Bright" });
    model.Characters.Add(new SelectListItem { Value = "2", Text = "Lively" });
    model.Characters.Add(new SelectListItem { Value = "3", Text = "Crazy" });
	
	return View(model);
}

[HttpPost]
public IActionResult DataBinding(DataBindingViewModel model)
{
	// Get selected Gender with model.Gender

    // Get selected Character with model.Character
}
```