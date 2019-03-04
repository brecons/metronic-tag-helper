# Data Annotation

For Mecons, extended data annotation is available, which will explain in this article.

Data Annotation in .NET Core Framework means add extra meaning to the data by adding attribute tags. The advantage of using Data Annotation feature is that by applying Data Attributes we can manage the data definition in a single place and do not need re-write the same rules in multiple places.

## Display Attributes

Display Attributes are used to specify how data from a member of a view model is displayed in the UI. Mecons provides some custom Display Attributes or rather extends extisting attributes:

* [BreconsDisplayAttribute](https://github.com/brecons/brecons-tag-helper/blob/master/BSolutions.Brecons/BSolutions.Brecons.Core/Attributes/BreconsDisplayAttribute.cs)<br />A Brecons own attribute to specify a display name and an optionally description for a property. This attribute is used when an own localization logic is used in an application and the DisplayAttribute of .NET isn't usable.
* [DisplayAttribute](https://msdn.microsoft.com/de-de/library/system.componentmodel.dataannotations.displayattribute(v=vs.110).aspx)<br />Provides a general-purpose attribute that lets you specify localizable strings for types and members of entity partial classes.
* [DisplayNameAttribute](https://msdn.microsoft.com/de-de/library/system.componentmodel.displaynameattribute(v=vs.110).aspx)<br />Specifies the display name for a property, event, or public void method which takes no arguments.

### Brecons Display Attribute

If you have a custom localization logic in your application it might be useful to have a custom display attribute to realize the translations. In this case create a custom display attribute and inherit from the `BSolutions.Brecons.Core.Attributes.BreconsDisplayAttribute`. Afterwards override the `DisplayName` and the `Description` property to insert custom translation logic.

<img src="/images/data-annotation_01.png" width="426" alt="Brecons Display Attribute">

#### View

```markup
@model BSolutions.Mecons.Test.Models.DataBindingViewModel
<form-group>
    <input type="text" asp-for="Product" />
</form-group>
```

#### Model

```csharp
public class DataBindingViewModel
{
    [CustomDisplay(Name = "Product.Name", Description = "Product.Description")]
    public string Product { get; set; } = "Mecons Tag Helper Library";
}
```

#### Custom Display Attribute

```csharp
public class CustomDisplayAttribute : BreconsDisplayAttribute
{
    // Your localization source provider
    private readonly ILocalizationSource _localizationSource = new LocalizationSource();

    public override string DisplayName
    {
        get
        {
            // Get translation for display name
            return this._localizationSource.Get(this._displayName);
        }
    }
    
    public override string DisplayName
    {
        get
        {
            // Get translation for description
            return this._localizationSource.Get(this._description);
        }
    }
}
```

### Display Attribute

Furthermore, the classic `DisplayAttribute` is also available to set the value of the label and help. This attribute is also fully supported by the Mecons tag helpers.

<img src="/images/data-annotation_02.png" width="426" alt="Classic Display Attribute">

#### View

```markup
@model BSolutions.Mecons.Test.Models.DataBindingViewModel
<form-group>
    <input type="text" asp-for="Product" />
</form-group>
```

#### Model

```csharp
public class DataBindingViewModel
{
    [Display(Name = "Product Name", Description = "The name of the product")]
    public string Product { get; set; } = "Mecons Tag Helper Library";
}
```