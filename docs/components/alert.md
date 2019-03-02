# Alert

Provide contextual feedback messages for typical user actions with a handful of available and flexible Alert messages.

![Mecons Alert](/images/alert_01.png)

```markup
<alert bc-title="Primary!">
	Lorem ipsum dolor sit amet, consetetur sadipscing elitr
</alert>
```

---

## Configuration

### Color

For proper styling of an alert use the `bc-color` attribute.

![Alert Color](/images/alert_02.png)

```markup
<alert bc-title="Success!" bc-color="Success">
	Lorem ipsum dolor sit amet, consetetur sadipscing elitr
</alert>
<alert bc-title="Info!" bc-color="Info">
	Lorem ipsum dolor sit amet, consetetur sadipscing elitr
</alert>
<alert bc-title="Warning!" bc-color="Warning">
	Lorem ipsum dolor sit amet, consetetur sadipscing elitr
</alert>
<alert bc-title="Danger!" bc-color="Danger">
	Lorem ipsum dolor sit amet, consetetur sadipscing elitr
</alert>
```

### Dismissible

Use the `bc-dismissible` attribute to dismiss any alert inline.

![Dismissible Alert](/images/alert_03.png)

```markup
<alert bc-title="Info!" bc-color="Info" bc-dismissible="true">
	Lorem ipsum dolor sit amet, consetetur sadipscing elitr
</alert>
```

### Link Styling

Links in any alert gets automatically a matching font color for a ideal illustration. To deactivate the automatical styling use the `bc-disable-link-styling` attribute and set it to `true`.

```markup
<alert bc-title="Brand!" bc-color="Brand" bc-disable-link-styling="true">
	Lorem ipsum dolor sit amet, <a href="#">consetetur</a> sadipscing elitr
</alert>
```

### Title

Use the `bc-title` attribute to add a title for the alert in addition to the content.

![Alert Title](/images/alert_04.png)

```markup
<alert bc-title="Brand!" bc-color="Brand">
	Lorem ipsum dolor sit amet, consetetur sadipscing elitr
</alert>
```