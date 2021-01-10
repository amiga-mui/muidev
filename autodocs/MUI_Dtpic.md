# Dtpic.mui
## Super class
[Area.mui](MUI_Area.md)
## Background
The Dtpic class allows including arbitrary images loadable using
datatypes.library in MUI applications. One just as to provide the file name
of an image. Everything else is handled by the Dtpic class. Full
transparency and alpha channel is supported.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Dtpic_Alpha](MUI_Dtpic.md/#MUIA_Dtpic_Alpha)|V20|ISG|`LONG`
[MUIA_Dtpic_DarkenSelState](MUI_Dtpic.md/#MUIA_Dtpic_DarkenSelState)|V20|I.G|`BOOL`
[MUIA_Dtpic_Fade](MUI_Dtpic.md/#MUIA_Dtpic_Fade)|V20|ISG|`LONG`
[MUIA_Dtpic_LightenOnMouse](MUI_Dtpic.md/#MUIA_Dtpic_LightenOnMouse)|V20|I.G|`BOOL`
[MUIA_Dtpic_Name](MUI_Dtpic.md/#MUIA_Dtpic_Name)|V18|ISG|`STRPTR`

## MUIA_Dtpic_Alpha
### NAME
[MUIA_Dtpic_Alpha](MUI_Dtpic/#MUIA_Dtpic_Alpha) -- V20 [ISG], `LONG`, 0x8042b4db

### FUNCTION
Specify an additional alpha value to be applied when blitting the loaded
image onto the screen. The value of [MUIA_Dtpic_Alpha](MUI_Dtpic/#MUIA_Dtpic_Alpha) is an 8bit value
specifying the intensity of the alpha blitting. You usually want to specify
0xff. Alpha blitting won't work on CLUT (i.e. depth <= 8 bit) screens.

## MUIA_Dtpic_DarkenSelState
### NAME
[MUIA_Dtpic_DarkenSelState](MUI_Dtpic/#MUIA_Dtpic_DarkenSelState) -- V20 [I.G], `BOOL`, 0x80423247

### FUNCTION
If set to TRUE the image's brightness will decreased by 50% whenever the
left mouse button is pressed on the object.

### SEE ALSO
[MUIA_Dtpic_LightenOnMouse](MUI_Dtpic/#MUIA_Dtpic_LightenOnMouse)

## MUIA_Dtpic_Fade
### NAME
[MUIA_Dtpic_Fade](MUI_Dtpic/#MUIA_Dtpic_Fade) -- V20 [ISG], `LONG`, 0x80420429

### FUNCTION
Setting this attribute to a positive value while also changing the image's alpha
value will let Dtpic class do a fade between the previous and the new alpha
value. This allows images to be faded in our out. Depending on the fading
direction between the current and the final alpha value the specified value will
be repeatedly added or subtracted respectively to the current alpha value with a
delay of 20ms until the final alpha value has been reached.

For negative values the fading process will be stopped and the final alpha value
will be set immediately.

### EXAMPLE
```c++
// fade out the image within approx. half a second
SetAttrs(obj,
  MUIA_Dtpic_Fade, 255/20,
  MUIA_Dtpic_Alpha, 0x00,
  TAG_DONE);
```

### SEE ALSO
[MUIA_Dtpic_Alpha](MUI_Dtpic/#MUIA_Dtpic_Alpha)

## MUIA_Dtpic_LightenOnMouse
### NAME
[MUIA_Dtpic_LightenOnMouse](MUI_Dtpic/#MUIA_Dtpic_LightenOnMouse) -- V20 [I.G], `BOOL`, 0x8042966a

### FUNCTION
If set to TRUE the image's brightness will increased by 20% whenever the
mouse is moved over the object.

### SEE ALSO
[MUIA_Dtpic_DarkenSelState](MUI_Dtpic/#MUIA_Dtpic_DarkenSelState)

## MUIA_Dtpic_Name
### NAME
[MUIA_Dtpic_Name](MUI_Dtpic/#MUIA_Dtpic_Name) -- V18 [ISG], `STRPTR`, 0x80423d72

### FUNCTION
Specify the name of the image file to be loaded using datatypes.library. This
attribute is absolutely required.

Dtpic class will remember the passed string pointer during OM_NEW and OM_SET,
but the string will NOT be copied. Thus the pointer must stay valid as long as
the object lives. To change the image later you MUST use a different string
buffer as Dtpic class will refuse to accept the old string buffer a second time.
Finally, NULL is NO valid value for this attribute.

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
