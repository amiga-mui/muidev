# Slider.mui
## Super class
[Numeric.mui](MUI_Numeric)
## Background
The slider class generates a GU element that allows a user to adjust a
numeric value. The programmer has not very much influence on the slider's
outfit, there are only very few tags available. Future versions of MUI will
probably include some preferences options to allow the user (**NOT** the
programmer) to configure this outfit.

Note that since slider is a subclass of group class, you can get horizontal
or vertical sliders by simply using the [MUIA_Group_Horiz](MUI_Group/#MUIA_Group_Horiz) attribute. Default
is a horizontal slider.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Slider_Horiz](MUI_Slider.md/#MUIA_Slider_Horiz)|V11|ISG|`BOOL`
[MUIA_Slider_Level](MUI_Slider.md/#MUIA_Slider_Level)|V4|ISG|`LONG` **(OBSOLETE)**
[MUIA_Slider_Max](MUI_Slider.md/#MUIA_Slider_Max)|V4|ISG|`LONG` **(OBSOLETE)**
[MUIA_Slider_Min](MUI_Slider.md/#MUIA_Slider_Min)|V4|ISG|`LONG` **(OBSOLETE)**
[MUIA_Slider_Quiet](MUI_Slider.md/#MUIA_Slider_Quiet)|V6|I..|`BOOL`
[MUIA_Slider_Reverse](MUI_Slider.md/#MUIA_Slider_Reverse)|V4|ISG|`BOOL` **(OBSOLETE)**

## MUIA_Slider_Horiz
### NAME
[MUIA_Slider_Horiz](MUI_Slider/#MUIA_Slider_Horiz) -- V11 [ISG], `BOOL`, 0x8042fad1

### FUNCTION
Specify if you want a horizontal or vertical slider. Also understands
[MUIA_Group_Horiz](MUI_Group/#MUIA_Group_Horiz) to be compatible with previous versions of MUI.

## MUIA_Slider_Level
### NAME
[MUIA_Slider_Level](MUI_Slider/#MUIA_Slider_Level) -- V4 [ISG], `LONG`, 0x8042ae3a **(OBSOLETE)**

### FUNCTION
The current position of the slider knob. This value is guaranteed to be
between [MUIA_Slider_Min](MUI_Slider/#MUIA_Slider_Min) and [MUIA_Slider_Max](MUI_Slider/#MUIA_Slider_Max).

### EXAMPLE
```c++
/* vertical task priority slider */
SliderObject,
  MUIA_Group_Horiz, FALSE,
  MUIA_Slider_Min, -20,
  MUIA_Slider_Max, 20,
  MUIA_Slider_Level, 0,
  End;
```

### SEE ALSO
[MUIA_Slider_Min](MUI_Slider/#MUIA_Slider_Min), [MUIA_Slider_Max](MUI_Slider/#MUIA_Slider_Max)

## MUIA_Slider_Max
### NAME
[MUIA_Slider_Max](MUI_Slider/#MUIA_Slider_Max) -- V4 [ISG], `LONG`, 0x8042d78a **(OBSOLETE)**

### FUNCTION
Adjust the maximum value for a slider object.

### SEE ALSO
[MUIA_Slider_Min](MUI_Slider/#MUIA_Slider_Min), [MUIA_Slider_Level](MUI_Slider/#MUIA_Slider_Level)

## MUIA_Slider_Min
### NAME
[MUIA_Slider_Min](MUI_Slider/#MUIA_Slider_Min) -- V4 [ISG], `LONG`, 0x8042e404 **(OBSOLETE)**

### FUNCTION
Adjust the minimum value for a slider object. Of course you can use negative
number, e.g. for a slider to adjust task priority.

### SEE ALSO
[MUIA_Slider_Max](MUI_Slider/#MUIA_Slider_Max), [MUIA_Slider_Level](MUI_Slider/#MUIA_Slider_Level)

## MUIA_Slider_Quiet
### NAME
[MUIA_Slider_Quiet](MUI_Slider/#MUIA_Slider_Quiet) -- V6 [I..], `BOOL`, 0x80420b26

### FUNCTION
When set to TRUE, the slider doesn't display it's current level in a text
object.

### SEE ALSO
[MUIA_Slider_Level](MUI_Slider/#MUIA_Slider_Level)

## MUIA_Slider_Reverse
### NAME
[MUIA_Slider_Reverse](MUI_Slider/#MUIA_Slider_Reverse) -- V4 [ISG], `BOOL`, 0x8042f2a0 **(OBSOLETE)**

### FUNCTION
Setting this attribute to TRUE will reverse the direction of the slider.

### SEE ALSO
[MUIA_Slider_Min](MUI_Slider/#MUIA_Slider_Min), [MUIA_Slider_Max](MUI_Slider/#MUIA_Slider_Max), [MUIA_Slider_Level](MUI_Slider/#MUIA_Slider_Level)

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
