# Change Logs &amp; Releases

In this page, you can find a record of all the changes made to Mecons such as bug fixes, new features, etc.

## Version 2.2.0 <small class="release-date">Currently not released</small>

This version supports **Metronic v5.5.5** and contains new tag helpers and some bugfixes. Also the version of Mecons is compatible with `netcoreapp2.2`.

***Important***: The licensing procedure has changed! Please read the *Add Mecons License* section on <a href="/Documentation/Mecons?view=MeconsInstallation">Mecons Installation</a> page.

<ul class="changelog">
    <li class="ch-added">Tag Helper for <a href="/Documentation/Mecons?view=Controls_Touchspin">Touchspin</a>.</li>
    <li class="ch-added">Tag Helper for <a href="/Documentation/Mecons?view=Controls_Switch">Switch</a>.</li>
    <li class="ch-added">Tag Helper for <a href="/Documentation/Mecons?view=Controls_Timepicker">Timepicker</a>.</li>
    <li class="ch-added">Tag Helper for <a href="/Documentation/Mecons?view=Controls_Daterangepicker">Daterangepicker</a>.</li>
    <li class="ch-added">Input Tag Helper: Support for button rendering with <code>&lt;input type="button" /&gt;</code> tags.</li>
    <li class="ch-added"> Data Binding support for <a href="/Documentation/Mecons?view=Controls_NoUiSlider">noUiSlider</a> Tag Helper: The dictionary attribute <code>asp-for-*</code> is available.</li>
    <li class="ch-added">The <a href="/Documentation/Mecons?view=Controls_NoUiSlider">noUiSlider Tag Helper</a> now supports pips / scales</li>
    <li class="ch-added">Add support for Target Framework Moniker (TFM) <code>netcoreapp2.2</code>.</li>
    <li class="ch-changed">Add a new page for Tag Helper <a href="/Documentation/Mecons?view=Localization">Localization</a> in the documentation.</li>
    <li class="ch-changed">The Tag Helper for <a href="/Documentation/Mecons?view=Controls_Datepicker">DatePicker</a> is now fully localized.</li>
    <li class="ch-changed">New licensing procedure without separate config file. Check <a href="/Documentation/Mecons?view=MeconsInstallation">Mecons Installation</a> for more informations.</li>
    <li class="ch-changed"><a href="/Documentation/Mecons?view=Datatable">Data Table</a>: The <code>bc-title</code> attribute of columns are not longer mandatory.</li>
    <li class="ch-changed">The <a href="/Documentation/Mecons?view=Controls_Dropzone">Dropzone</a> Tag Helper now provides a public instance to which it's easy to bind events.</li>
    <li class="ch-changed">The <code>bc-sliders</code> attribute no longer exists for the <a href="/Documentation/Mecons?view=Controls_NoUiSlider">noUiSlider</a> Tag Helper. Instead, the sliders are now defined using the <code>bc-slider-*</code> attribute.</li>
    <li class="ch-changed">Switch from bower package manager to <a href="https://yarnpkg.com" target="_blank">Yarn</a>.</li>
    <li class="ch-fixed"><a href="/Documentation/Mecons?view=ProgressWidget">Progress Widget</a>: Exception when <code>bc-color</code> is not set.</li>
    <li class="ch-fixed"><a href="/Documentation/Mecons?view=StatsWidget">Stats Widget</a>: Exception when <code>bc-color</code> is not set.</li>
</ul>

<a href="https://www.nuget.org/packages/BSolutions.Mecons/2.2.0" class="btn btn-info">
    <i class="fa fa-link"></i> Source and Download
</a>

## Version 2.1.0 <small class="release-date">Sep. 15, 2018</small>

This version supports **Metronic v5.5.4** and contains new tag helpers and some bugfixes.

<ul class="changelog">
    <li class="ch-added">Tag Helper for <a href="/Documentation/Mecons?view=StatsWidget">Stats Widget</a></li>
    <li class="ch-added">Tag Helper for <a href="/Documentation/Mecons?view=ProgressWidget">Progress Widget</a></li>
    <li class="ch-added">Tag Helper for <a href="/Documentation/Mecons?view=Controls_NoUiSlider">noUiSlider</a></li>
    <li class="ch-added">Tag Helper for <a href="/Documentation/Mecons?view=Controls_Dropzone">Dropzone</a></li>
    <li class="ch-changed">Table: The attribute <code>bc-bordered</code> has been replaced by the <code>bc-border</code> attribute.</li>
    <li class="ch-changed">Datatable: Add new attribute <code>bc-ajax-timeout</code> to define the ajax timeout.</li>
    <li class="ch-changed">Support for Fontawesome 5 Icons</li>
    <li class="ch-changed">Mandatory attributes are now checked before rendering. If a mandatory attribute is not set then an <code>MandatoryAttributeException</code> will be thrown.</li>
    <li class="ch-fixed">Forms: Static Tag Helper crashes when no property is binded.</li>
</ul>

<a href="https://www.nuget.org/packages/BSolutions.Mecons/2.1.0" class="btn btn-info">
    <i class="fa fa-link"></i> Source and Download
</a>

## Version 2.0.1 <small class="release-date">Feb. 27, 2018</small>

This version supports **Metronic v5.1** and contains some breaking changes and major bugfixes.

<ul class="changelog">
    <li class="ch-changed">Forms: Checkbox List support binding of a model member via <code>asp-for</code> attribute.</li>
    <li class="ch-changed">Forms: Radio List support binding of a model member via <code>asp-for</code> attribute.</li>
    <li class="ch-changed">Forms: Radio List support binding of Enumeration values via <code>bc-items</code> attribute.</li>
    <li class="ch-changed">Forms: Validation is now enabled by default (not longer necessary to set <code>bc-validation</code> to <code>true</code>).</li>
    <li class="ch-changed">Forms: The Static Tag Helper now supports <code>asp-for</code> attribute.</li>
    <li class="ch-changed">Datatable: The datatable has been completely redesigned and the handling improved significantly.</li>
    <li class="ch-changed">Support for Metronic v5.1</li>
    <li class="ch-fixed">Forms: The Static Tag Helper not longer have a css <code>margin-bottom</code>.</li>
    <li class="ch-fixed">Forms: The Summernote Tag Helper has a problem with ' (inverted comma) character.</li>
</ul>

<a href="https://www.nuget.org/packages/BSolutions.Mecons/2.0.1" class="btn btn-info">
    <i class="fa fa-link"></i> Source and Download
</a>

## Version 2.0.0 <small class="release-date">Dec. 06, 2017</small>

This version supports **Metronic v5.0.7.1** and is the initial release of the Mecons Tag Helper Library.

<ul class="changelog">
    <li class="ch-added">Tag Helper for Alert</li>
    <li class="ch-added">Tag Helper for Anchor</li>
    <li class="ch-added">Tag Helper for Badge</li>
    <li class="ch-added">Tag Helper for Button</li>
    <li class="ch-added">Tag Helper for Button Group</li>
    <li class="ch-added">Tag Helper for Datatable</li>
    <li class="ch-added">Tag Helper for Datepicker</li>
    <li class="ch-added">Tag Helper for Dropdown Button</li>
    <li class="ch-added">Tag Helper for Form Input Controls</li>
    <li class="ch-added">Tag Helper for Form Layout</li>
    <li class="ch-added">Tag Helper for Form Data Binding and Validation</li>
    <li class="ch-added">Tag Helper for Grid System</li>
    <li class="ch-added">Tag Helper for Icon</li>
    <li class="ch-added">Tag Helper for Markdown</li>
    <li class="ch-added">Tag Helper for Modal</li>
    <li class="ch-added">Tag Helper for Popover</li>
    <li class="ch-added">Tag Helper for Portlet</li>
    <li class="ch-added">Tag Helper for Progress</li>
    <li class="ch-added">Tag Helper for Stack</li>
    <li class="ch-added">Tag Helper for Summernote</li>
    <li class="ch-added">Tag Helper for Table</li>
    <li class="ch-added">Tag Helper for Tabs</li>
    <li class="ch-added">Tag Helper for Timeline</li>
    <li class="ch-added">Tag Helper for Tooltip</li>
</ul>

<a href="https://www.nuget.org/packages/BSolutions.Mecons/2.0.0" class="btn btn-info">
    <i class="fa fa-link"></i> Source and Download
</a>