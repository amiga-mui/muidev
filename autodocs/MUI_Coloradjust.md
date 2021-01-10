# Coloradjust.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
Coloradjust class creates some gadgets that allow adjusting a single color.
Depending on the operating system, different kinds of gadgets are be used.
Kickstart 2.x users might only receive an RGB slider triple, Kickstart 3.x
users could get an additional colorwheel if available.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Coloradjust_Blue](MUI_Coloradjust.md/#MUIA_Coloradjust_Blue)|V4|ISG|`ULONG`
[MUIA_Coloradjust_Green](MUI_Coloradjust.md/#MUIA_Coloradjust_Green)|V4|ISG|`ULONG`
[MUIA_Coloradjust_ModeID](MUI_Coloradjust.md/#MUIA_Coloradjust_ModeID)|V4|ISG|`ULONG`
[MUIA_Coloradjust_Red](MUI_Coloradjust.md/#MUIA_Coloradjust_Red)|V4|ISG|`ULONG`
[MUIA_Coloradjust_RGB](MUI_Coloradjust.md/#MUIA_Coloradjust_RGB)|V4|ISG|`ULONG *`

## MUIA_Coloradjust_Blue
### NAME
[MUIA_Coloradjust_Blue](MUI_Coloradjust.md/#MUIA_Coloradjust_Blue) -- V4 [ISG], `ULONG`, 0x8042b8a3

### FUNCTION
Set or get the 32-bit blue component of the adjusted color. Values range
from 0 (no blue) to $ffffffff (full blue).

### SEE ALSO
[MUIA_Coloradjust_Green](MUI_Coloradjust.md/#MUIA_Coloradjust_Green), [MUIA_Coloradjust_Red](MUI_Coloradjust.md/#MUIA_Coloradjust_Red), [MUIA_Coloradjust_RGB](MUI_Coloradjust.md/#MUIA_Coloradjust_RGB),
[MUIA_Coloradjust_ModeID](MUI_Coloradjust.md/#MUIA_Coloradjust_ModeID)

## MUIA_Coloradjust_Green
### NAME
[MUIA_Coloradjust_Green](MUI_Coloradjust.md/#MUIA_Coloradjust_Green) -- V4 [ISG], `ULONG`, 0x804285ab

### FUNCTION
Set or get the 32-bit green component of the adjusted color. Values range
from 0 (no green) to $ffffffff (full green).

### SEE ALSO
[MUIA_Coloradjust_Red](MUI_Coloradjust.md/#MUIA_Coloradjust_Red), [MUIA_Coloradjust_Blue](MUI_Coloradjust.md/#MUIA_Coloradjust_Blue), [MUIA_Coloradjust_RGB](MUI_Coloradjust.md/#MUIA_Coloradjust_RGB),
[MUIA_Coloradjust_ModeID](MUI_Coloradjust.md/#MUIA_Coloradjust_ModeID)

## MUIA_Coloradjust_ModeID
### NAME
[MUIA_Coloradjust_ModeID](MUI_Coloradjust.md/#MUIA_Coloradjust_ModeID) -- V4 [ISG], `ULONG`, 0x8042ec59

### FUNCTION
This attribute tells the coloradjust object for which screen mode the color
shall be adjusted. The object queries the display data base for some mode
attributes (such as supported number of red/green/blue bits) and adjusts its
display accordingly, giving the user an idea of what colors are supported.

Omitting this attribute does not affect the functionality of a Coloradjust
object. The user will still be able to adjust a color. However, if you know
the ModeID, you should supply it.

### SEE ALSO
[MUIA_Coloradjust_RGB](MUI_Coloradjust.md/#MUIA_Coloradjust_RGB)

### EXAMPLE
```c++
set(cadj, MUIA_Coloradjust_ModeID, GetVPModeID(viewport));
```

## MUIA_Coloradjust_Red
### NAME
[MUIA_Coloradjust_Red](MUI_Coloradjust.md/#MUIA_Coloradjust_Red) -- V4 [ISG], `ULONG`, 0x80420eaa

### FUNCTION
Set or get the 32-bit red component of the adjusted color. Values range from
0 (no red) to $ffffffff (full red).

### SEE ALSO
[MUIA_Coloradjust_Green](MUI_Coloradjust.md/#MUIA_Coloradjust_Green), [MUIA_Coloradjust_Blue](MUI_Coloradjust.md/#MUIA_Coloradjust_Blue), [MUIA_Coloradjust_RGB](MUI_Coloradjust.md/#MUIA_Coloradjust_RGB),
[MUIA_Coloradjust_ModeID](MUI_Coloradjust.md/#MUIA_Coloradjust_ModeID)

## MUIA_Coloradjust_RGB
### NAME
[MUIA_Coloradjust_RGB](MUI_Coloradjust.md/#MUIA_Coloradjust_RGB) -- V4 [ISG], `ULONG *`, 0x8042f899

### FUNCTION
Set or get the red/green/blue values all at once. You pass in/receive a
pointer to three longwords containing the 32-bit red, green and blue values.

### EXAMPLE
```c++
ULONG rgb[3] = { 0xa000000, 0xdeadbeaf, 0x42424242 };
set(cadj, MUIA_Coloradjust_RGB, rgb);

ULONG *rgb;
get(cadj, MUIA_Coloradjust_RGB, &rgb);
printf("red=%08lx green=%08lx blue=%08lx\n", rgb[0], rgb[1], rgb[2]);
```

### SEE ALSO
[MUIA_Coloradjust_Green](MUI_Coloradjust.md/#MUIA_Coloradjust_Green), [MUIA_Coloradjust_Blue](MUI_Coloradjust.md/#MUIA_Coloradjust_Blue), [MUIA_Coloradjust_Red](MUI_Coloradjust.md/#MUIA_Coloradjust_Red),
[MUIA_Coloradjust_ModeID](MUI_Coloradjust.md/#MUIA_Coloradjust_ModeID)

----
<table class='compact' style='border: none; border-spacing: 0px; margin: 0px' width='100%'>
<tr>
<td style='text-align: left; vertical-align: top' width='33%'>Copyright &copy 1992-2006 by Stefan Stuntz<br>Copyright &copy 2006-2021 by Thore B&ouml;ckelmann, Jens Maus</TD>
<td style='text-align: center; vertical-align: top' width='33%'>
<a href=http://github.com/amiga-mui/muidev>MUI for AmigaOS Homepage</a><br>
<a href=http://github.com/amiga-mui/muidev/autodocs/autodocs.md>MUI Autodocs Index</a>
</td>
<td style='text-align: right; vertical-align: top' width='33%'>Updated: 10-Jan-2021</td>
</tr>
</table>
