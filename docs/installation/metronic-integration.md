# Metronic Integration

This article describes how to integrate the Metronic Admin Theme into a ASP.NET Core Web Application.

## Include Metronic Files

The first step, after creation a ASP.NET Core Web Application, is to include the Metronic files into the project. Download the installation package from our server and unzip it. Afterwards also unzip the included Metronic Admin Theme archive. Copy the `assets` directory of your choosen Metronic Admin Theme (e.g. `/metronic_v5.x/dist/<YOUR FAVORITE THEME>/assets`) into the `wwwroot` of your project:

* `MyCompany.MyApplication`
  * `/wwwroot`
    * `/css`
    * `/images`
    * `/js`
    * `/lib`
    * `/metronic`
      * `/app`
      * `/demo`
      * `/snippets`
      * `/vendors`
  * `/Controllers`
  * `/Models`
  * `/Views`

## Adapt the Layout Page

### HTML Layout

Now it's time to fit the `/Views/Shared/_Layout.cshtml` of your project. Open the `index.html` of your choosen Metronic Admin Theme (e.g. `/metronic_v5.x/dist/<YOUR FAVORITE THEME>/index.html`) and copy the complete HTML structure into the `_Layout.cshtml`.

### Path Corrections

To load all included styles and scripts of the Metronic Admin Theme correctly, it is necessary to correct the paths.

Press **Ctrl + H** to open the Quick Replace Tool and replace all paths starting with `assets/` with `~/metronic/`.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/metronic-int_01.png" width="305" alt="Path correction with Quick Replace Tool">

### Body Rendering

Include the `@RenderBody()` method into the `_Layout.cshtml` at the position where the individual page content will be rendered.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/metronic-int_02.png" width="1197" alt="Insert RenderBody method into layout page">

### JavaScript Positioning

To ensure that all Mecons Tag Helpers work as expected, it is necessary to move all JavaScript includes from the bottom of the `_Layout.cshtml` into the `<head>`.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/metronic-int_03.png" width="1063" alt="Path correction with Quick Replace Tool">
