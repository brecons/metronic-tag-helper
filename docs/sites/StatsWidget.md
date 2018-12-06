# Stats Widget

The Mecons Stats Widget is used to display KPIs (Key Performance Indicator). Here, both a widget and several contiguous widgets can be arranged.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/stats-widget_01.png" width="369" alt="Mecons Stats Widget">

```markup
<widget-stats>
    <widget-stats-item bc-title="Member Profit" bc-desc="Average Weekly Profit" bc-value="+$17,800" bc-color="Brand" />
    <widget-stats-item bc-title="Orders" bc-desc="Weekly Customer Orders" bc-value="+1,800" bc-color="Danger" />
    <widget-stats-item bc-title="Issue Reports" bc-desc="System bugs and issues" bc-value="-27,49%" bc-color="Success" />
</widget-stats>
```

## Item Configuration `<widget-stats-item>`

### Title <span class="badge info">Mandatory</span>

With the `bc-title` attribute the title of the widget can be defined. This attribute is a mandatory attribute and must be defined.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/stats-widget_02.png" width="374" alt="Stats Widget Title">

### Value <span class="badge info">Mandatory</span>

The `bc-value` attribute defines the KPI. This is a free text (not a number etc.) that can be defined as desired. This attribute is a mandatory attribute and must be defined.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/stats-widget_03.png" width="374" alt="Stats Widget Value">

### Description

A description for the KPI can be added with the `bc-desc` attribute.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/stats-widget_04.png" width="374" alt="Stats Widget Description">

### Color

Adjust the color of the KPI and the progress with the `bc-color` attribute. The default color is `Primary`.