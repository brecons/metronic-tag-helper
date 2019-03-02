# HTML Datasource

The Mecons Datatable component supports initialization from HTML table. It also defines the schema model of the data source. In addition to the visualization, the Datatable provides built-in support for operations over data such as sorting, filtering and paging performed in user browser (frontend).

---

## Usage

To provide a traditional HTML table as Datatable, place your HTML table markup in your view and set your favorite Datatable attributes. No serverside code or processing is needed.

### View

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/datatable-html_01.png" width="927" alt="Datatable HTML Datasource View">

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