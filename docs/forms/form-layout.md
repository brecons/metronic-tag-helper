# Form Layout

Use Mecons to render a form in a horizontal or vertical layout.

---

## Form Structure

The form structure in Mecons is the same as in Bootstrap. The main container is a `<form>` tag which includes the form controls. Each form control should be surrounded with an `<form-group>` tag helper. A `<form-group>` can also contains a `<label>` or a `<help>`.

```markup
<form>
    <form-group>
        <!-- Form Control -->
    </form-group>
    <form-group>
        <!-- Form Control -->
    </form-group>
    ...
</form>
```

---

## Form Configuration

### Horizontal

Set the `bc-horizontal` attribute to true if you want a horizontal form layout.

!!! Note
    If you choose a horizontal form layout it is necessary to define at least one label width for your favorite [Responsive Breakpoint](https://getbootstrap.com/docs/4.0/layout/overview/#responsive-breakpoints). For further informations check the following chapter "Label Width".

### Label Width (Mandatory on Horizontal Layout)

Set at least one label width if you render your form horizontal. It's possible to set a label width for each [Responsive Breakpoint](https://getbootstrap.com/docs/4.0/layout/overview/#responsive-breakpoints). Choose the `bc-label-width-{breakpoint}` attribute to set a label width for a breakpoint. If you define only a label width for a large breakpoint (e.g. `bc-label-width-lg` or `bc-label-width-xl`), the labels get a full width on smaller breakpoints and the conclusion is a vertical form.

### Label Display

To hide control labels on all devices execept screen readers, set the `bc-labels-sr-only` to `true`.

---

## Form Group Configuration

### State

Use the `bc-state` attribute to set a validation state for the control within the form group. Available states are `Success`, `Warning` or `Danger`.

<img src="img/form-layout_01.png" width="426" alt="Form Group State" />

```markup
<form-group bc-state="Success">
    <input type="text" bc-label="Input with success" />
</form-group>
<form-group bc-state="Warning">
    <input type="text" bc-label="Input with warning" />
</form-group>
<form-group bc-state="Danger">
    <input type="text" bc-label="Input with danger" />
</form-group>
```

---

## Vertical Form

In a vertical form each control and its corresponding label and help text will placed in a separate row.

<img src="img/form-layout_02.png" width="434" alt="Vertical Form Layout" />

```markup
<form>
    <form-group>
        <input type="text" bc-label="User name" bc-help="Usually your e-mail address" />
    </form-group>
    <form-group>
        <input type="password" bc-label="Password" />
    </form-group>
    <button type="submit">Log in</button>
</form>
```

---

## Horizontal Form

In a horizontal form each control and its corresponding label placed in the same row. The help text will placed under the control.

<img src="img/form-layout_03.png" width="429" alt="Horizontal Form Layout" />

```markup
<form bc-horizontal="true" bc-label-width-md="4">
    <form-group>
        <input type="text" bc-label="User name" bc-help="Usually your e-mail address" />
    </form-group>
    <form-group>
        <input type="password" bc-label="Password" />
    </form-group>
    <button type="submit">Log in</button>
</form>
```