# Switch

A Switch is a simple component used for activating one of two predefined options. Commonly used as an on/off button.

<img src="/images/switch_01.png" width="236" alt="Mecons Switch">

```markup
<switch bc-label="Default Switch" />
```

## Configuration `<switch />`

### Icon

Set the `bc-icon` attribute to `true` to add an icon to the Switch.

<img src="/images/switch_02.png" width="244" alt="Switch with Icon">

```markup
<switch bc-label="Icon" bc-icon="true" />
```

### Color

For proper styling of an Switch use the `bc-color` attribute.

<img src="/images/switch_03.png" width="523" alt="Colored Switch">

```markup
<switch bc-label="Success" bc-icon="true" bc-color="Success" checked />
<switch bc-label="Warning" bc-icon="true" bc-color="Warning" checked />
<switch bc-label="Info" bc-icon="true" bc-color="Info" checked />
<switch bc-label="Danger" bc-icon="true" bc-color="Danger" checked />
```

### Outline

To render the Switch outline and inverse colors, set the `bc-outline` attribute to `true`.

<img src="/images/switch_04.png" width="531" alt="Outlined Switch">

```markup
<switch bc-label="Success" bc-icon="true" bc-color="Success" bc-outline="true" checked />
<switch bc-label="Warning" bc-icon="true" bc-color="Warning" bc-outline="true" checked />
<switch bc-label="Info" bc-icon="true" bc-color="Info" bc-outline="true" checked />
<switch bc-label="Danger" bc-icon="true" bc-color="Danger" bc-outline="true" checked />
```