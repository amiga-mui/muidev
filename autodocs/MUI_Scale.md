# Scale.mui
## Super class
[Area.mui](MUI_Area.md)
## Background
A Scale object generates a percentage scale running from 0% to 100%. A good
place for such an object is e.g. below a fuel gauge.

Depending on how much space is available, the scale will be more or less
detailed.

Due to MUI's automatic layout system, you don't need to worry about it's
size. When placed in a vertical group just below the object you want to
scale, everything is fine.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Scale_Horiz](MUI_Scale.md/#MUIA_Scale_Horiz)|V4|ISG|`BOOL`

## MUIA_Scale_Horiz
### NAME
[MUIA_Scale_Horiz](MUI_Scale/#MUIA_Scale_Horiz) -- V4 [ISG], `BOOL`, 0x8042919a

### FUNCTION
Indicate whether you want a horizontal or a vertical scale.

Defaults to horizontal.

### BUGS
Currently, only the horizontal scale is implemented.

### EXAMPLE
```c++
VGroup,
  Child, GaugeObject, End,
  Child, Scaleobject, End,
  End;
```

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
