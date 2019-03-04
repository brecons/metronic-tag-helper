# Button Group

The Button Group groups a seriesof buttons together on a single line.

<img src="/images/button-group_01.png" width="236" alt="Mecons Button Group">

```markup
<button-group>
	<button>Left</button>
	<button>Middle</button>
	<button>Right</button>
</button-group>
```

## Configuration `<button-group>`

### Vertical

Make a set of buttons appear vertically stacked rather than horizontally by adding the `bc-vertical` attribute.

<img src="/images/button-group_02.png" width="108" alt="Vertical Button Group">

```markup
<button-group bc-vertical="true">
	<button>Top</button>
	<button>Middle</button>
	<button>Bottom</button>
</button-group>
```

### Size

Define a size of the button group with the `bc-size` attribute. Available sizes are `Default`, `Large` or `Small`.