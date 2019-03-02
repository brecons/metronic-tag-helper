# Datatable

The Datatable is a highly flexible tool which extends the HTML table with advanced interaction controls.

![Mecons Datatable](/images/datatable_01.png)

---

## Configuration

### Sorting

To enable column sorting for the Datatable, set the `bc-sorting` attribute to `true`. By default, all columns of the Datatable are sortable if this attribute is set. To disable sorting for specific columns check Sorting in the Column Configuration.

![Datatable Sorting](/images/datatable_02.png)

```markup
<datatable bc-sorting="true"> ... </datatable>
```

### Paging

Datatables can split the rows into individual pages, which is an efficient method of showing a large number of records in a small space. To enable paging set the `bc-paging` attribute to `true`.

![Datatable Paging](/images/datatable_03.png)

```markup
<datatable bc-paging="true"> ... </datatable>
```

### Page Size

Define a number of rows to display on a single page with `bc-page-size` attribute when using pagination. This attribute only has an effect if the `bc-paging` attribute is set to `true`. By default, the page size is set to `10`.

### Height

By default, the height of the table depends on its content. A fixed height can be set with the `bc-height` attribute. If the content is now higher than the defined height, a scroll bar is displayed. The height is expressed as an integer and in pixels (px).

![Datatable Height](/images/datatable_04.png)

```markup
<datatable bc-height="200"> ... </datatable>
```

### Header

Set the `bc-header` attribute to `false` to hide the table header for the Datatable. By default, the table header is shown and the attribute is `true`.

### Footer

Set the `bc-footer` attribute to `true` to show a table footer at the bottom of the Datatable.

### Searching

This option allows the search abilities of Datatables to be enabled or disabled. To enable searching it is necessary to specify a search input field with the `bc-search-input` attribute. The value specified here is the `id` of the input field.

![Datatable Searching](/images/datatable_05.png)

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

## Column Configuration

### Field (Mandatory)

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

![Datatable Column Placeholder Template](/images/datatable_06.png)

```markup
<datatable bc-ajax-url="/api/Demo/" bc-paging="true">
    <datatable-column bc-field="recordID" bc-title="#" bc-width="50" />
    <datatable-column bc-field="shipCountry" bc-title="Ship Country" bc-template="{{shipCountry}}-{{shipCity}}" />
    <datatable-column bc-field="shipCity" bc-title="Ship City" bc-width="110" />
</datatable>
```

#### Script

It is also possible to modify the content of a column using its own JavaScript. This provides more flexibility than a placeholder. The script is defined within the `<datatable-column>` tag helper and must be placed in HTML comments (`<!--` and `-->`).

![Datatable Column Script Template](/images/datatable_07.png)

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

---

## HTML Data Source

The Mecons Datatable component supports initialization from HTML table. It also defines the schema model of the data source. In addition to the visualization, the Datatable provides built-in support for operations over data such as sorting, filtering and paging performed in user browser (frontend).

To provide a traditional HTML table as Datatable, place your HTML table markup in your view and set your favorite Datatable attributes. No serverside code or processing is needed.

![Datatable HTML Datasource View](/images/datatable_08.png)

```markup
<datatable bc-paging="true" bc-sorting="true">
    <thead>
        <tr>
            <th>Order ID</th>
            <th>Owner</th>
            <th>Contact</th>
            <th>Car Make</th>
            <th>Car Model</th>
            <th>Color</th>
            <th>Deposit Paid</th>
            <th>Order Date</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>16590-107</td>
            <td>Zandra Fisbburne</td>
            <td>(916) 6137523</td>
            <td>Pontiac</td>
            <td>Grand Am</td>
            <td>Puce</td>
            <td>$75343.80</td>
            <td>2016-09-08</td>
        </tr>
        <tr> ... </tr>
        <tr> ... </tr>
        ...
    </tbody>
</datatable>
```

---

## AJAX Data Source

The Mecons Datatable component supports remote data binding. For remote data binding you can specify a remote data source that returns data in JSON/JSONP format. It also defines the schema model of the data source received from the remote data source. In addition to the visualization, the Datatable provides built-in support for operations over data such as sorting, filtering and paging performed in user browser (frontend).

### Url (Mandatory)

Use the `bc-ajax-url` attribute to specify the url to the web service which provides the data for the Datatable. This property is mandatory for remote data binding.

### Method

Choose a HTTP method for requesting the web service by setting the `bc-ajax-method` attribute. Possible methods are `Post` (default), `Get`, `Put` and `Delete`.

### Timeout

Set a number of milliseconds before the request ended. Default is `30000`, equal to 30 seconds.

### Params

Your own API may requires some parameter to call for getting the data. E.g. token, search keywords, IDs, etc. Specify query parameters with the `bc-ajax-param-*` attribute. This query parameters will be sent along in the Datatable API request.

### Headers

Set custom HTTP headers with the `bc-ajax-header-*` attribute for the API call.

### Serverside Processing

With the Mecons Datatable it is possible to process the paging, filtering and sorting logic on serverside within your API method. It is possible to enable the serverside processing individually for this functionalities.

* Set the `bc-ajax-paging` to `true` to process the paging logic on serverside.
* Set the `bc-ajax-filtering` to `true` and handle the data filtering in the API method.
* Set the `bc-ajax-sorting` to `true` and sort your data by the specified column on serverside.

---

### Usage

In order to connect a remote data source (like a REST API) to a Datatable, it is necessary to provide a web service. Also, the necessary Tag Helper Markup must be accommodated on the corresponding view.

Within the API controller it is very easy to receive all transmitted form data from the Datatable request. Use our Mecons `DatatableAjaxRequest` model class to parse the form data of the API action into a simple type-safe object.

We also assist you in sorting, searching and selecting records. Import the `BSolutions.Mecons.Controls.Datatable.Extensions` namespace into your controller and use the `FilterExtensions` to proceed your data.

The last challenge is to send the data back to the Datatable. Use the `DatatableAjaxResponse<T>` class, which transmits the data correctly in the right structure to the Datatable.

```csharp
[HttpPost]
public DatatableAjaxResponse<ShipViewModel> Post(IFormCollection data)
{
    // Get all ships from database
    IQueryable<ShipViewModel> items = this.GetAll();

    // Get all form data from Datatable request
    var request = new DatatableAjaxRequest(data);

    // Initialize a new Datatable response object
    var response = new DatatableAjaxResponse<ShipViewModel> (items.Count(), request);

    // Ordering
    IQueryable<ShipViewModel> query = items.Sort<ShipViewModel>(response);

    // Searching
    query = query.Search(request, response);

    // Paging
    query = query.Select(response);

    response.Data = query.ToList();

    return response;
}
```

Within the view place the `<datatable>` tag helper and define your columns with the `<datatable-column>` Tag Helper. Important is, that you set the `bc-field` attribute on each column with the name of the associated data field.

![Datatable AJAX Datasource View](/images/datatable_09.png)

```markup
<row>
    <column xs-size="4">
        <input type="text" class="form-control m-input m-input--solid" placeholder="Search..." id="generalSearch">
    </column>
</row>
<row>
    <column>
        <datatable bc-ajax-url="/api/Demo/" bc-ajax-sorting="true" bc-ajax-filtering="true" bc-ajax-paging="true" bc-search-input="generalSearch">
            <datatable-column bc-field="recordID" bc-title="#" bc-width="50" />
            <datatable-column bc-field="shipCountry" bc-title="Ship Country" bc-template="{{shipCountry}}-{{shipCity}}" />
            <datatable-column bc-field="shipCity" bc-title="Ship City" bc-width="110" />
            <datatable-column class="actions">
            <!--
            function (row) {
                return "<a class='btn btn-info' href='/Product/" + row.recordID + "'>Edit</a>";
            }
            -->
            </datatable-column>
        </datatable>
    </column>
</row>
```