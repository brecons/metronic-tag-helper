# Tabs

Tabs are a single content area with multiple planels, each associated with a header in a list.

<img src="/images/tabs_01.png" width="487" alt="Mecons Tabs" />

```markup
<tabs>
	<tabs-pane bc-header="Home">
		<p>
			Consequat occaecat ullamco amet non eiusmod nostrud dolore ...
		</p>
	</tabs-pane>
	<tabs-pane bc-header="Profile">
		...
	</tabs-pane>
	<tabs-pane bc-header="Settings">
		...
	</tabs-pane>
</tabs>
```

---

## Configuration

### Pills

Use the `bc-pills` attribute to render the tabs as pills.

<img src="/images/tabs_02.png" width="478" alt="Tabs as Pills" />

```markup
<tabs bc-pills="true">
	<tabs-pane bc-header="Home">
		...
	</tabs-pane>
	<tabs-pane bc-header="Profile">
		...
	</tabs-pane>
	<tabs-pane bc-header="Settings">
		...
	</tabs-pane>
</tabs>
```

---

## Pane Configuration

### Header (Mandatory)

Use the `bc-header` attribute to define a title for the tab.

### Active

By default, the first tab is active on page load. If you want to modify that, use the `bc-active` attribute to activate another tab on startup.

<img src="/images/tabs_03.png" width="491" alt="Active Tab Pane" />

```markup
<tabs>
	<tabs-pane bc-header="Home">
		...
	</tabs-pane>
	<tabs-pane bc-header="Profile" bc-active="true">
		...
	</tabs-pane>
	<tabs-pane bc-header="Settings">
		...
	</tabs-pane>
</tabs>
```