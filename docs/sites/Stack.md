# Stack

A Stack allows to build equal height and flexible blocks.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/stack_01.png" width="365" alt="Mecons Stack">

```markup
<stack>
    <stack-item>Item 1</stack-item>
    <stack-item>Item 2</stack-item>
    <stack-item>Item 3</stack-item>
    <stack-item>Item 4</stack-item>
</stack>
```

## Stack Configuration `<stack>`

### Auto Width

If the `bc-auto-width` attribute is set to `true`, each stack item gets the width of whose content.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/stack_02.png" width="411" alt="Stack Auto Width">

```markup
<stack bc-auto-width="true">
    <stack-item>Free content</stack-item>
    <stack-item>Free content</stack-item>
    <stack-item>Longer free content</stack-item>
</stack>
```

### Orientation

With the `bc-orientation` attribute the orientation of the stack can be set. Possible orientations are `Horizontal` (default) or `Vertical`.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/stack_03.png" width="350" alt="Stack Orientation">

```markup
<stack bc-orientation="Vertical">
    ...
</stack>
```

## Item Configuration `<stack-item>`

### Alignment

Set an item content alignment with `bc-alignment` attribute. Possible alignments are `Left` (default), `Center` or `Right`.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/stack_04.png" width="356" alt="Stack Item Horizontal Alignment">

```markup
<stack>
    <stack-item bc-alignment="Left">Left alignment</stack-item>
    <stack-item bc-alignment="Center">Center alignment</stack-item>
    <stack-item bc-alignment="Right">Right alignment</stack-item>
</stack>
```

### Vertical Alignment

Align the content vertically with the `bc-vertical-alignment` attribute. It is possible to align the content `Top`, `Middle` or `Bottom`.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/stack_05.png" width="353" alt="Stack Item Vertical Alignment">

```markup
<stack>
    <stack-item bc-vertical-alignment="Top">Top alignment</stack-item>
    <stack-item bc-vertical-alignment="Middle">Middle alignment</stack-item>
    <stack-item bc-vertical-alignment="Bottom">Bottom alignment</stack-item>
</stack>
```