# AJAX Datasource

The Mecons Datatable component supports remote data binding. For remote data binding you can specify a remote data source that returns data in JSON/JSONP format. It also defines the schema model of the data source received from the remote data source. In addition to the visualization, the Datatable provides built-in support for operations over data such as sorting, filtering and paging performed in user browser (frontend).

---

## Configuration

### Url <span class="badge info">Mandatory</span>

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

## Usage

In order to connect a remote data source (like a REST API) to a Datatable, it is necessary to provide a web service. Also, the necessary Tag Helper Markup must be accommodated on the corresponding view.

### Controller

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

### View

Within the view place the `<datatable>` tag helper and define your columns with the `<datatable-column>` Tag Helper. Important is, that you set the `bc-field` attribute on each column with the name of the associated data field.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/datatable-ajax_01.png" width="933" alt="Datatable AJAX Datasource View">

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