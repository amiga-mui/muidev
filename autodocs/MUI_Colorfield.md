# Colorfield.mui
## Super class
[Area.mui](MUI_Area.md)
## Background
Colorfield class creates a rectangle filled with a specific color, useful
e.g. within a palette requester. You can change the color of the field at
any time by setting its RGB attributes.

The field will try to obtain an exclusive pen on the current screen. When
none is available, it just displays some kind of rastered background. Maybe
it will get a little more intelligent and try to display the color by mixing
together some other colors, but thats a future topic.

Needless to say that Colorfield only works with Kickstart 3.x and above,
since lower operating systems don't support pen sharing. When using this
class with a lower OS, you will also get some kind of (boring) raster.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Colorfield_Blue](MUI_Colorfield.md/#MUIA_Colorfield_Blue)|V4|ISG|`ULONG`
[MUIA_Colorfield_Green](MUI_Colorfield.md/#MUIA_Colorfield_Green)|V4|ISG|`ULONG`
[MUIA_Colorfield_Pen](MUI_Colorfield.md/#MUIA_Colorfield_Pen)|V4|..G|`ULONG`
[MUIA_Colorfield_Red](MUI_Colorfield.md/#MUIA_Colorfield_Red)|V4|ISG|`ULONG`
[MUIA_Colorfield_RGB](MUI_Colorfield.md/#MUIA_Colorfield_RGB)|V4|ISG|`ULONG *`

## MUIA_Colorfield_Blue
### NAME
[MUIA_Colorfield_Blue](MUI_Colorfield/#MUIA_Colorfield_Blue) -- V4 [ISG], `ULONG`, 0x8042d3b0

### FUNCTION
Set or get the 32-bit blue component of the fields color. Values range from
0 (no blue) to $ffffffff (full blue).

### SEE ALSO
[MUIA_Colorfield_Green](MUI_Colorfield/#MUIA_Colorfield_Green), [MUIA_Colorfield_Red](MUI_Colorfield/#MUIA_Colorfield_Red), [MUIA_Colorfield_RGB](MUI_Colorfield/#MUIA_Colorfield_RGB)

## MUIA_Colorfield_Green
### NAME
[MUIA_Colorfield_Green](MUI_Colorfield/#MUIA_Colorfield_Green) -- V4 [ISG], `ULONG`, 0x80424466

### FUNCTION
Set or get the 32-bit green component of the fields color. Values range from
0 (no green) to $ffffffff (full green).

### SEE ALSO
[MUIA_Colorfield_Red](MUI_Colorfield/#MUIA_Colorfield_Red), [MUIA_Colorfield_Blue](MUI_Colorfield/#MUIA_Colorfield_Blue), [MUIA_Colorfield_RGB](MUI_Colorfield/#MUIA_Colorfield_RGB)

## MUIA_Colorfield_Pen
### NAME
[MUIA_Colorfield_Pen](MUI_Colorfield/#MUIA_Colorfield_Pen) -- V4 [..G], `ULONG`, 0x8042713a

### FUNCTION
When specified, the colorfield uses exactly this pen instead of trying to
obtain a new one.

### SEE ALSO
[MUIA_Colorfield_RGB](MUI_Colorfield/#MUIA_Colorfield_RGB)

## MUIA_Colorfield_Red
### NAME
[MUIA_Colorfield_Red](MUI_Colorfield/#MUIA_Colorfield_Red) -- V4 [ISG], `ULONG`, 0x804279f6

### FUNCTION
Set or get the 32-bit red component of the fields color. Values range from 0
(no red) to $ffffffff (full red).

### SEE ALSO
[MUIA_Colorfield_Green](MUI_Colorfield/#MUIA_Colorfield_Green), [MUIA_Colorfield_Blue](MUI_Colorfield/#MUIA_Colorfield_Blue), [MUIA_Colorfield_RGB](MUI_Colorfield/#MUIA_Colorfield_RGB)

## MUIA_Colorfield_RGB
### NAME
[MUIA_Colorfield_RGB](MUI_Colorfield/#MUIA_Colorfield_RGB) -- V4 [ISG], `ULONG *`, 0x8042677a

### FUNCTION
Set or get the red/green/blue values of a colorfield all at once. You pass
in/receive a pointer to three longwords containing the 32-bit red, green and
blue values.

### EXAMPLE
```c++
ULONG rgb[3] = { 0xa000000, 0xdeadbeaf, 0x42424242 };
set(field, MUIA_Colorfield_RGB, rgb);

ULONG *rgb;
get(field, MUIA_Colorfield_RGB, &rgb);
printf("red=%08lx green=%08lx blue=%08lx\n", rgb[0], rgb[1], rgb[2]);
```

### SEE ALSO
[MUIA_Colorfield_Green](MUI_Colorfield/#MUIA_Colorfield_Green), [MUIA_Colorfield_Blue](MUI_Colorfield/#MUIA_Colorfield_Blue), [MUIA_Colorfield_Red](MUI_Colorfield/#MUIA_Colorfield_Red)

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
