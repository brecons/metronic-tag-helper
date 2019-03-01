# Icon

Metronic supports the icon libraries of Flaticon, Fontawesome, Lineawesome and Socicons. To handle these icons in a easy way use the Mecons Tag Helper for icons.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/icon_01.png" width="150" alt="Mecons Icon">

```markup
<h5>Fontawesome</h5>
<icon bc-type="FA_Users" />
<icon bc-type="FA_Bus" />
<icon bc-type="FA_Star" />

<h5>Flaticon</h5>
<icon bc-type="FI_Coins" />
<icon bc-type="FI_File" />
<icon bc-type="FI_Imac" />

<h5>Lineawesome</h5>
<icon bc-type="LA_Camera" />
<icon bc-type="LA_Cogs" />
<icon bc-type="LA_StarO" />

<h5>Socicons</h5>
<icon bc-type="SI_Amazon" />
<icon bc-type="SI_Blizzard" />
<icon bc-type="SI_Digg" />
```

## Configuration `<icon>`

### Type <span class="badge info">Mandatory</span>

Specify an icon with the `bc-type` attribute.

### Color

Set a icon color with the `bc-color` attribute.

<img class="img-shadow img-responsive center-block" src="https://raw.githubusercontent.com/brecons/metronic-tag-helper/master/docs/images/icon_02.png" width="126" alt="Icon Color">

```markup
<icon bc-color="Primary" bc-type="FI_Internet" />
<icon bc-color="Danger" bc-type="FI_Download" />
<icon bc-color="Success" bc-type="FI_Light" />
```