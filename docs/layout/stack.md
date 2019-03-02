# Stack

A Stack allows to build equal height and flexible blocks.

![Mecons Stack](/images/stack_01.png)

```markup
<stack>
    <stack-item>Item 1</stack-item>
    <stack-item>Item 2</stack-item>
    <stack-item>Item 3</stack-item>
    <stack-item>Item 4</stack-item>
</stack>
```

---

## Configuration

### Auto Width

If the `bc-auto-width` attribute is set to `true`, each stack item gets the width of whose content.

![Stack Auto Width](/images/stack_02.png)

```markup
<stack bc-auto-width="true">
    <stack-item>Free content</stack-item>
    <stack-item>Free content</stack-item>
    <stack-item>Longer free content</stack-item>
</stack>
```

### Orientation

With the `bc-orientation` attribute the orientation of the stack can be set. Possible orientations are `Horizontal` (default) or `Vertical`.

![Stack Orientation](/images/stack_03.png)

```markup
<stack bc-orientation="Vertical">
    ...
</stack>
```

---

## Stack Item Configuration

### Alignment

Set an item content alignment with `bc-alignment` attribute. Possible alignments are `Left` (default), `Center` or `Right`.

![Stack Item Horizontal Alignment](/images/stack_04.png)

```markup
<stack>
    <stack-item bc-alignment="Left">Left alignment</stack-item>
    <stack-item bc-alignment="Center">Center alignment</stack-item>
    <stack-item bc-alignment="Right">Right alignment</stack-item>
</stack>
```

### Vertical Alignment

Align the content vertically with the `bc-vertical-alignment` attribute. It is possible to align the content `Top`, `Middle` or `Bottom`.

![Stack Item Vertical Alignment](/images/stack_05.png)

```markup
<stack>
    <stack-item bc-vertical-alignment="Top">Top alignment</stack-item>
    <stack-item bc-vertical-alignment="Middle">Middle alignment</stack-item>
    <stack-item bc-vertical-alignment="Bottom">Bottom alignment</stack-item>
</stack>
```