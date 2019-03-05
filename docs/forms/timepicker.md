# Timepicker

With the Timepicker you can easily select a time for a text input using your mouse or keyboards arrow keys.

<img src="/images/timepicker_01.png" width="433" alt="Mecons Timepicker">

```markup
<timepicker bc-label="Start Time" />
```

---

## Configuration

### Steps

Specify a gradual increase for the minutes or seconds field. To set a step for the minutes field use the `bc-minute-step` attribute and set it to an integer between `1` and `60`. The same is possible for the seconds field. Therefore use the `bc-second-step` attribute.

### Seconds

To show a field for seconds set the `bc-seconds` attribute to `true`.

<img src="/images/timepicker_02.png" width="426" alt="Timepicker with Seconds Field">

```markup
<timepicker bc-label="Start Time" bc-seconds="true" />
```

### Meridian

To show a field for meridian selection set the `bc-meridian` attribute to `true`. By default, the meridian field is enabled.

<img src="/images/timepicker_03.png" width="433" alt="Timepicker with Meridian Field">

### Input Fields

To disable the input fields for hours, minutes, seconds and meridian set the `bc-inputs` attribute to `false`.

<img src="/images/timepicker_04.png" width="434" alt="Timepicker without Input Fields">

```markup
<timepicker bc-label="Start Time" bc-inputs="false" />
```

### Icon

Set an icon addon for the timepicker with the `bc-icon` attribute.

<img src="/images/timepicker_05.png" width="434" alt="Timepicker Icon">

```markup
<timepicker bc-label="Start Time" bc-icon="FA_Clock" />
```

### Disable Focus

Setting the `bc-disable-focus` attribute to `true` disables the input from focusing. This is useful for touch screen devices that display a keyboard on input focus.