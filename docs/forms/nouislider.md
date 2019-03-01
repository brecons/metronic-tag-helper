# noUiSlider

noUiSlider is a range slider without bloat. It offers a ton off features, and it is as small, lightweight and minimal as possible, which is great for mobile use on the many supported devices, including iPhone, iPad, Android devices & Windows (Phone) 8 desktops, tablets and all-in-ones. It works on desktops too, of course!

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_01.png" width="294" alt="Mecons noUiSlider">

```markup
<nouislider bc-slider-1="20" />
```

## Configuration

### Sliders <span class="badge info">Mandatory</span>

The `bc-slider-*` attribute defines an handle and its start position. The `bc-slider-*` attribute is a dictionary attribute and can be assigned multiple times (in this case the `*` must be replaced by a unique identifier, e.g. `bc-slider-1`).

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_02.png" width="430" alt="noUiSlider Slider Definition">

```markup
<nouislider bc-slider-1="20" />
<nouislider bc-slider-1="30.5" bc-slider-2="80" />
```

### Connectors

A connector is the space between two handles or between a handle and the start respectively the end point of a slider. These spaces can be filled with one color. Use the `bc-connectors` attribute to define these spaces as a connector or not. The connectors will be defined with a comma-separated list of Boolean values.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_03.png" width="431" alt="noUiSlider Connectors">

```markup
<nouislider bc-slider-1="20" bc-slider-2="80" bc-connectors="false,true,false" />
<nouislider bc-slider-1="20" bc-connectors="true,false" />
```

### Color

With the noUiSlider Tag Helper it is possible to colorize the handles and the connectors of a slider. Set a color for all handles with the `bc-color-sliders` attribute.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_04.png" width="435" alt="noUiSlider Slider Color">

```markup
<nouislider bc-slider-1="20" bc-slider-2="80" bc-color-sliders="Brand" />
```

To set a color for the connectors use the `bc-color-connectors` attribute.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_05.png" width="440" alt="noUiSlider Connector Color">

```markup
<nouislider bc-slider-1="20" bc-slider-2="80" bc-connectors="false,true,false" bc-color-sliders="Danger" bc-color-connectors="Brand" />
```

### Step

By default, the slider slides fluently. In order to make the handles jump between intervals, you can set the `bc-step` attribute. The interval is specified as an integer.

### Minimum

Set the minimum value of the slider with the `bc-min` attribute. By default, the minimum is set to `0`.

### Maximum

Set the maximum value of the slider with the `bc-max` attribute. By default, the maximum is set to `100`.

### Margin

When using two handles, the minimum distance between the handles can be set using the `bc-margin` attribute. The margin value is relative to the value set in `bc-min` and `bc-max`. This option is only available on linear sliders.

### Limit

The `bc-limit` attribute is the oposite of the `bc-margin` attribute, limiting the maximum distance between two handles. As with the `bc-margin` attribute, the limit option can only be used on linear sliders.

### Orientation

The orientation of the slider can be set by the `bc-orientation` attribute. Possible values are `Horizontal` (default) or `Vertical`. Vertical sliders don't assume a default height, so you'll need to set one. You can use any unit you want, including `%` or `px`.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_06.png" width="45" alt="noUiSlider Orientation">

```markup
<nouislider bc-slider-1="20" bc-orientation="Vertical" style="height: 100px;" />
```

### Direction

By default the sliders are top-to-bottom and left-to-right, but you can change this using the `bc-direction` attribute, which decides where the upper side of the slider is. Possible directions are `Ltr` (default) or `Rtl`.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_07.png" width="429" alt="noUiSlider Direction">

```markup
<nouislider bc-slider-1="20" bc-connectors="true,false" />
<nouislider bc-slider-1="20" bc-connectors="true,false" bc-direction="Rtl" />
```

## Scale / Pips

To improve the overview, a noUiSlider can be extended with a scale and pips. There are several ways to define scales / pips.

### Modes

A scale for the noUiSlider can be defined in several modes. The mode of the scale is be defined with the `bc-pips-mode` attribute. Possible modes are `Range`, `Steps`, `Positions`, `Count` and `Values`.

#### Range

The `Range` mode uses the slider range to determine where the pips should be. A pip is generated for every percentage specified.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_08.png" width="437" alt="noUiSlider with Range scale">

```markup
<nouislider bc-slider-1="0" bc-pips-mode="Range" />
```

#### Steps

In `Steps` mode, a pip is generated for every step of the slider defined with the `bc-step` attribute. In addition, each pip of a step still gets a label with the respective value.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_09.png" width="438" alt="noUiSlider with Steps scale">

```markup
<nouislider bc-slider-1="0" bc-pips-mode="Steps" bc-step="5" />
<nouislider bc-slider-1="0" bc-pips-mode="Steps" bc-step="10" />
```

#### Positions

In `Positions` mode, pips are generated at percentage-based positions on the slider.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_10.png" width="438" alt="noUiSlider with Positions scale">

```markup
<nouislider bc-slider-1="0" bc-pips-mode="Positions" bc-pips-values="0, 25, 50, 75, 100" />
<nouislider bc-slider-1="0" bc-pips-mode="Positions" bc-pips-values="0, 10, 20, 30, 40, 50, 100" />
```

#### Count

The `Count` mode can be used to generate a fixed number of pips.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_11.png" width="425" alt="noUiSlider with Count scale">

```markup
<nouislider bc-slider-1="0" bc-pips-mode="Count" bc-pips-values="5" />
<nouislider bc-slider-1="0" bc-pips-mode="Count" bc-pips-values="11" />
```

#### Values

The `Values` mode is similar to `Positions`, but it accepts values instead of percentages.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_12.png" width="433" alt="noUiSlider with Values scale">

```markup
<nouislider bc-slider-1="0" bc-pips-mode="Values" bc-pips-values="0, 10, 20, 50, 100" />
<nouislider bc-slider-1="0" bc-pips-mode="Values" bc-pips-values="0, 15, 30, 45, 100" />
```

### Density

The density value controls how many pips are placed on one percent of the slider range. With the default value of `1`, there is one pip per percent. For a value of `2`, a pip is placed for every 2 percent. A value below one will place more than one pip per percentage.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_13.png" width="457" alt="noUiSlider with density scale">

```markup
<nouislider bc-slider-1="0" bc-pips-mode="Range" />
<nouislider bc-slider-1="0" bc-pips-mode="Range" bc-pips-density="2" />
<nouislider bc-slider-1="0" bc-pips-mode="Range" bc-pips-density="4" />
```

### Stepped

By setting the `bc-pips-stepped` attribute to `true`, the pip values will be round to the slider stepping.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/nouislider_14.png" width="463" alt="noUiSlider with stepped scale">

```markup
<nouislider bc-slider-1="0" bc-pips-mode="Positions" bc-step="2" bc-pips-values="0, 25, 50, 75, 100" />
<nouislider bc-slider-1="0" bc-pips-mode="Positions" bc-step="2" bc-pips-values="0, 25, 50, 75, 100" bc-pips-stepped="true" />
```

## Data Binding

### View

The noUiSlider Tag Helper provides the dictionary attribute `asp-for-*` to bind a view model property to a slider. The attribute can be assigned multiple times within one Tag Helper. For this, only the `*` is to be replaced by the name of the slider:

```markup
<form asp-controller="Slider" asp-action="NoUiSlider" method="post">
    <form-group>
        <nouislider asp-for-1="Slider1" asp-for-2="Slider2" />
    </form-group>

    <button type="submit">Post Data</button>
</form>
```

### View Model

```csharp
public class NoUiSliderViewModel
{
    public double Slider1 { get; set; }

    public double Slider2 { get; set; }
}
```

### Controller

```csharp
public class SliderController : Controller
{
    public IActionResult NoUiSlider()
    {
        // Instance a view model with default slider values
        NoUiSliderViewModel model = new NoUiSliderViewModel { Slider1 = 33.3, Slider2 = 66.6 };

        return View(model);
    }

    [HttpPost]
    public IActionResult NoUiSlider(NoUiSliderViewModel model)
    {
        // Read value of first Slider
        var sliderValue1 = model.Slider1;

        // Read value of second Slider
        var sliderValue2 = model.Slider2;

        return View(model);
    }
}
```