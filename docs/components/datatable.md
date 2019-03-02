# Datatable

The Datatable is a highly flexible tool which extends the HTML table with advanced interaction controls.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/datatable_01.png" width="922" alt="Mecons Datatable">

---

## Data Sources

There are several ways to bind data to a Datatable. Click on your favorite data source to learn more about their use.

### <i class="fa fa-html5"></i> HTML Data Source

The Mecons Datatable component supports initialization from HTML table. It also defines the schema model of the data source.

[Learn more](datatable-html-datasource.md)

### <i class="fa fa-cloud"></i> AJAX Data Source

The Mecons Datatable component supports remote data binding. For remote data binding you can specify a remote data source that returns data in JSON/JSONP format.

[Learn more](datatable-ajax-datasource.md)

---

## Datatable Configuration `<datatable>`

### Sorting

To enable column sorting for the Datatable, set the `bc-sorting` attribute to `true`. By default, all columns of the Datatable are sortable if this attribute is set. To disable sorting for specific columns check Sorting in the Column Configuration.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/datatable_02.png" width="914" alt="Datatable Sorting">

```markup
<datatable bc-sorting="true"> ... </datatable>
```

### Paging

Datatables can split the rows into individual pages, which is an efficient method of showing a large number of records in a small space. To enable paging set the `bc-paging` attribute to `true`.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/datatable_03.png" width="924" alt="Datatable Paging">

```markup
<datatable bc-paging="true"> ... </datatable>
```

### Page Size

Define a number of rows to display on a single page with `bc-page-size` attribute when using pagination. This attribute only has an effect if the `bc-paging` attribute is set to `true`. By default, the page size is set to `10`.

### Height

By default, the height of the table depends on its content. A fixed height can be set with the `bc-height` attribute. If the content is now higher than the defined height, a scroll bar is displayed. The height is expressed as an integer and in pixels (px).

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/datatable_04.png" width="919" alt="Datatable Height">

```markup
<datatable bc-height="200"> ... </datatable>
```

### Header

Set the `bc-header` attribute to `false` to hide the table header for the Datatable. By default, the table header is shown and the attribute is `true`.

### Footer

Set the `bc-footer` attribute to `true` to show a table footer at the bottom of the Datatable.

### Searching

This option allows the search abilities of Datatables to be enabled or disabled. To enable searching it is necessary to specify a search input field with the `bc-search-input` attribute. The value specified here is the `id` of the input field.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/datatable_05.png" width="929" alt="Datatable Searching">

```markup
<row>
    <column xs-size="4">
        <input id="generalSearch" type="text" class="form-control m-input m-input--solid" placeholder="Search...">
    </column>
</row>
<row>
    <column>
        <datatable bc-search-input="generalSearch">
    </column>
</row>
```

Control the speed of search and data load request to reduce the search call frequency automatically. Use the `bc-search-delay` attribute to set the number of milliseconds. By default, the search delay is `400` milliseconds.

---

## Column Configuration `<datatable-column>`

### Field <span class="badge info">Mandatory</span>

The data field name of the column will be set with the `bc-field` attribute. This attribute maps a field of the data source to the defined column.

### Title

The title name will be displayed as header or footer and can set with `bc-title` attribute. This is the displayed title of the column.

### Sorting

When the sorting is enabled on `<datatable>` level, by default all columns can be sorted. If you want to disable sorting for a column, set the `bc-sorting` attribute to `false`.

### Searching

When a search input field is specified on `<datatable>` level, by default all columns are searchable. If you want to disable searching for a column, set the `bc-searching` attribute to `false`.

### Width

By default, all columns have the same width. Define a custom column width with the `bc-width` attribute. The width is expressed as an integer and in pixels (px).

### Alignment

The horizontal alignment of cells text for a specific column can set with `bc-alignment` attribute. Possible alignments are `Left` (default), `Center` or `Right`.

### Overflow

The `bc-overflow` attribute specifies what should happen if content overflows a cell in within a column. The possible values of this attribute equals the [CSS Overflow Property](https://www.w3schools.com/cssref/pr_pos_overflow.asp). By default, the overflow is set to `Initial`.

### Template

There are two ways to influence the appearance of a column. The placeholder provides an easy way to enrich or modify the content of a cell. An own template script offers the full flexibility for the free design of the column content.

#### Placeholder

Customize the cell content rendering with the `bc-template` attribute. Use placeholders (e.g. `{{FieldName}}`) to access the content of column fields and define a custom template. This mechanism is well known from the C# String Interpolation.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/datatable_06.png" width="929" alt="Datatable Column Placeholder Template">

```markup
<datatable bc-ajax-url="/api/Demo/" bc-paging="true">
    <datatable-column bc-field="recordID" bc-title="#" bc-width="50" />
    <datatable-column bc-field="shipCountry" bc-title="Ship Country" bc-template="{{shipCountry}}-{{shipCity}}" />
    <datatable-column bc-field="shipCity" bc-title="Ship City" bc-width="110" />
</datatable>
```

#### Script

It is also possible to modify the content of a column using its own JavaScript. This provides more flexibility than a placeholder. The script is defined within the `<datatable-column>` tag helper and must be placed in HTML comments (`<!--` and `-->`).

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/datatable_07.png" width="929" alt="Datatable Column Script Template">

```markup
<datatable bc-ajax-url="/api/Demo/" bc-paging="true">
    <datatable-column bc-field="recordID" bc-title="#" bc-width="50" />
    <datatable-column bc-field="shipCountry" bc-title="Ship Country" bc-template="{{shipCountry}}-{{shipCity}}" />
    <datatable-column bc-field="shipCity" bc-title="Ship City" bc-width="110" />
    <datatable-column bc-alignment="Right">
        <!--
        function (row) {
        return "<a class='btn btn-info' href='/Product/" + row.recordID + "'>Edit</a>";
        }
        -->
    </datatable-column>
</datatable>
```