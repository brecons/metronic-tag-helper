# Change Logs and Releases

In this page, you can find a record of all the changes made to Mecons such as bug fixes, new features, etc.

---

## Version 2.2.1

***Release Date: Jan. 25, 2019***

This version supports **Metronic v5.5.5** and contains new tag helpers and some bugfixes.

* Add a French language file and full support of culture code `fr`.
* Add an Italian language file and full support of culture code `it`.
* Fixed wrong `for` attribute generation in label tags of Form Controls.
* Change the `bc-toggle-text` attribute of Modal to no longer mandatory. This makes it possible to render a modal dialog without a button.
* Datatable Tag Helper now provides a JavaScript instance that allows client-side customization of the datatable.
* Fixed an error while licensing Mecons when hosting the application in local IIS.
* Fixed that the Datatable don't parse the form data during ajax calls correctly.

---

## Version 2.2.0

***Release Date: Dec. 06, 2018***

This version supports **Metronic v5.5.5** and contains new tag helpers and some bugfixes. Also the version of Mecons is compatible with `netcoreapp2.2`.

* Add new Tag Helper for [Touchspin](forms/touchspin.md).
* Add new Tag Helper for [Switch](forms/switch.md).
* Add new Tag Helper for [Timepicker](forms/timepicker.md).
* Add new Tag Helper for [Daterangepicker](forms/daterangepicker.md).
* Add support for button rendering with `<input type="button" />` in [Input Tag Helper](forms/input.md).
* Add data binding support for [noUiSlider Tag Helper](forms/nouislider.md). The dictionary attribute `asp-for-*` is available.
* Add support for pips / scales in [noUiSlider Tag Helper](forms/nouislider.md).
* Add a new page for [Tag Helper Localization](localization.md) in the documentation.
* The [Datepicker Tag Helper] is now fully localized.
* New licensing procedure without separate config file.
* Change the `bc-title` attribute of [Datatable Tag Helper](components/datatable.md) columns to not longer mandatory.
* The [Dropzone Tag Helper](forms/dropzone.md) now provides a public instance to which it's easy to bind events.
* The `bc-sliders` attribute no longer exists for the [noUiSlider Tag Helper](forms/nouislider.md). Instead, the sliders are now defined using the `bc-slider-*` attribute.
* Switch from bower package manager to [Yarn](https://yarnpkg.com).
* Solved exception when `bc-color` is not set in [Progress Widget](content/progress-widget.md).
* Solved exception when `bc-color` is not set in [Stats Widget](content/stats-widget.md).

---

## Version 2.1.0

Release Date: Sep. 15, 2018

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

---

## Version 2.0.1

Release Date: Feb. 27, 2018

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

---

## Version 2.0.0

Release Date: Dec. 06, 2017

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