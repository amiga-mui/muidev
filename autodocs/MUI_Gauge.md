# Gauge.mui
## Super class
[Area.mui](MUI_Area)
## Background
A gauge object is a nice looking display element useful for some kind of
progress display.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Gauge_Current](MUI_Gauge.md/#MUIA_Gauge_Current)|V4|ISG|`LONG`
[MUIA_Gauge_Divide](MUI_Gauge.md/#MUIA_Gauge_Divide)|V4|ISG|`ULONG`
[MUIA_Gauge_Horiz](MUI_Gauge.md/#MUIA_Gauge_Horiz)|V4|I..|`BOOL`
[MUIA_Gauge_InfoRate](MUI_Gauge.md/#MUIA_Gauge_InfoRate)|V4|ISG|`LONG`
[MUIA_Gauge_InfoText](MUI_Gauge.md/#MUIA_Gauge_InfoText)|V7|ISG|`STRPTR`
[MUIA_Gauge_Max](MUI_Gauge.md/#MUIA_Gauge_Max)|V4|ISG|`LONG`

## MUIA_Gauge_Current
### NAME
[MUIA_Gauge_Current](MUI_Gauge/#MUIA_Gauge_Current) -- V4 [ISG], `LONG`, 0x8042f0dd

### FUNCTION
Set the current level of the gauge. The value must be between 0 and
[MUIA_Gauge_Max](MUI_Gauge/#MUIA_Gauge_Max).

### SEE ALSO
[MUIA_Gauge_Max](MUI_Gauge/#MUIA_Gauge_Max)

## MUIA_Gauge_Divide
### NAME
[MUIA_Gauge_Divide](MUI_Gauge/#MUIA_Gauge_Divide) -- V4 [ISG], `ULONG`, 0x8042d8df

### FUNCTION
If this attribute is != 0, every value set with [MUIA_Gauge_Current](MUI_Gauge/#MUIA_Gauge_Current) will be
divided by this before further processing.

### EXAMPLE
See BoopsiDoor demo program.

### SEE ALSO
[MUIA_Gauge_Current](MUI_Gauge/#MUIA_Gauge_Current)

## MUIA_Gauge_Horiz
### NAME
[MUIA_Gauge_Horiz](MUI_Gauge/#MUIA_Gauge_Horiz) -- V4 [I..], `BOOL`, 0x804232dd

### FUNCTION
Determine if you want a horizontal or vertical gauge.

Defaults to FALSE

### SEE ALSO
[MUIA_Gauge_Current](MUI_Gauge/#MUIA_Gauge_Current)

## MUIA_Gauge_InfoRate
### NAME
[MUIA_Gauge_InfoRate](MUI_Gauge/#MUIA_Gauge_InfoRate) -- V4 [ISG], `LONG`, 0x804253c8

### FUNCTION
Setting this attribute to an integer value n will update the gauge's
[MUIA_Gauge_InfoText](MUI_Gauge/#MUIA_Gauge_InfoText) on every (n+1)th refresh only. Use this attribute if the
gauge is used to visualize some very heavily updated information to avoid
tearing effects.

Defaults to 0 which means to update the info text on every refresh.

### EXAMPLE
```c++
MUIA_Gauge_InfoRate, 10,
```

### SEE ALSO
[MUIA_Gauge_InfoText](MUI_Gauge/#MUIA_Gauge_InfoText)

## MUIA_Gauge_InfoText
### NAME
[MUIA_Gauge_InfoText](MUI_Gauge/#MUIA_Gauge_InfoText) -- V7 [ISG], `STRPTR`, 0x8042bf15

### FUNCTION
The text given here is displayed within a gauge object and is usually
intended to show some kind of percentage information.

This texts preparse is set to "\33c\0338", this makes it appear centered and
highlighted by default.

Any %ld will be replaced with the current value of [MUIA_Gauge_Current](MUI_Gauge/#MUIA_Gauge_Current).

Note: Up to V18 of Gauge class InfoText worked only for horizontal gauges. If
you intend to use and change info text, you should specify an empty
[MUIA_Gauge_InfoText](MUI_Gauge/#MUIA_Gauge_InfoText) ("") at object creation time. This makes your object get
a fixed height that fits the height of the info text.

Since version 19 of Gauge class, you can also use [MUIA_Gauge_InfoText](MUI_Gauge/#MUIA_Gauge_InfoText) for
vertical gauges.

### NOTES
Implemented in version 7 of Gauge class (MUI 1.5). Version 19 of Gauge class
(MUI 3.8) enhances this attribute to work with vertical gauge objects too.

### EXAMPLE
```c++
MUIA_Gauge_InfoText, "%ld %%",
```

### SEE ALSO
[MUIA_Gauge_Current](MUI_Gauge/#MUIA_Gauge_Current)

## MUIA_Gauge_Max
### NAME
[MUIA_Gauge_Max](MUI_Gauge/#MUIA_Gauge_Max) -- V4 [ISG], `LONG`, 0x8042bcdb

### FUNCTION
Set the maximum value for the gauge.

Defaults to 100.

### SEE ALSO
[MUIA_Gauge_Current](MUI_Gauge/#MUIA_Gauge_Current)

----
<table class='compact' style='border: none; border-spacing: 0px; margin: 0px' width='100%'>
<tr>
<td style='text-align: left; vertical-align: top' width='33%'>Copyright &copy 1992-2006 by Stefan Stuntz<br>Copyright &copy 2006-2021 by Thore B&ouml;ckelmann, Jens Maus</TD>
<td style='text-align: center; vertical-align: top' width='33%'>
<a href=http://muidev.de>MUI for AmigaOS Homepage</a><br>
<a href=http://muidev.de/wiki/Documentation>MUI Autodocs Index</a>
</td>
<td style='text-align: right; vertical-align: top' width='33%'>Updated: 10-Jan-2021</td>
</tr>
</table>
