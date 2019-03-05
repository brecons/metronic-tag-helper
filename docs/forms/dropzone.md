# Dropzone

DropzoneJS is an open source library that provides drag’n’drop file uploads with image previews.

<img src="/images/dropzone_01.png" width="299" alt="Mecons Dropzone">

```markup
<dropzone bc-url="/Forms/Dropzone" />
```

---

## Configuration

### Url (Mandatory)

The `bc-url` attribute specifies the target to which the dropped files will be uploaded. This attribute is mandatory and without it, the dropzone will not run correctly.

### Title

With the `bc-title` attribute it is possible to override the default title of the Dropzone. If the `bc-title` attribute is not set, a localized default message will be displayed.

<img src="/images/dropzone_02.png" width="648" alt="Dropzone Title">

```markup
<!-- Default Dropzone Title -->
<dropzone bc-url="/Forms/Dropzone" />

<!-- Custom Dropzone Title -->
<dropzone bc-url="/Forms/Dropzone" bc-title="This is a custom title of the dropzone." />
```

### Description

Describe the Dropzone in detail with the `bc-desc` attribute. The description will be displayed below the title.

<img src="/images/dropzone_03.png" width="295" alt="Dropzone Description">

```markup
<dropzone bc-url="/Forms/Dropzone" bc-desc="Only image, pdf and psd files are allowed for upload" />
```

### Maximum File Size

The `bc-max-file-size` attribute defines the maximum file size of an uploaded file. By default the file size haven't any limit. The maximum file size is expressed as an integer and in Megabyte (MB).

### Maximum Files

The `bc-max-files` attribute can be used to limit the maximum number of files that will be handled by the Dropzone.

### Remove Files

If the `bc-remove-files` attribute is set to `true` this will add a link to every file preview to remove or cancel (if already uploading) the file.

### Accepted Files

With the `bc-accepted` attribute it is possible to allow only certain [MIME Types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types) for the Dropzone. Multiple MIME types are specified as a comma-separated list (e.g. `image/*,application/pdf,.psd`). If the Dropzone is clickable this option will also be used as accept parameter on the hidden file input as well.

### Clickable

By default, the Dropzone element itself is clickable. This means that clicking on the Dropzone opens a file selection dialog. To disable this functionality set the `bc-clickable` attribute to `false`.

### Color

Use the `bc-color` attribute to set a color for the Dropzone.

<img src="/images/dropzone_04.png" width="297" alt="Dropzone Color">

```markup
<dropzone bc-url="/Forms/Dropzone" bc-color="Primary" />
```

### Parameter

The name of the file parameter that gets transferred to the server will specified with the `bc-name` attribute. By default, the parameter name is `file`.

---

## Server-side Processing

How to transfer the files collected in a Dropzone to the server is described in this section.

### View

First a Dropzone must be defined in a view. The important thing here is either to deliberately define a custom parameter name that will later be used to transfer the files to the server, or to use the default parameter name (`file`).

```markup
<!-- Dropzone.cshtml -->
<dropzone bc-url="/Forms/Dropzone" />
```

### Controller

On server-side it es very easy to receive the uploaded file. Use the `IFormFile` interface and a parameter with the same name of the parameter defined in the Dropzone (by default `file`).

```csharp
// Forms Controller
public IActionResult Dropzone()
{
    return View();
}

[HttpPost]
public IActionResult Dropzone(IFormFile file)
{
    // Process the transfered file

    // Return a Json result which is readable for the Dropzone
    return Json(new { success = true, response = "File uploaded." });
}
```