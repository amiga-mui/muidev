# Rectangle.mui
## Super class
[Area.mui](MUI_Area.md)
## Background
Rectangle class seems kind of useless since it doesn't define any attributes
or methods itself. However, objects of this type are frequently used in
every application. They allow insertion of space to control MUI's layout
process.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Rectangle_BarTitle](MUI_Rectangle.md/#MUIA_Rectangle_BarTitle)|V11|I.G|`STRPTR`
[MUIA_Rectangle_HBar](MUI_Rectangle.md/#MUIA_Rectangle_HBar)|V7|I.G|`BOOL`
[MUIA_Rectangle_VBar](MUI_Rectangle.md/#MUIA_Rectangle_VBar)|V7|I.G|`BOOL`

## MUIA_Rectangle_BarTitle
### NAME
[MUIA_Rectangle_BarTitle](MUI_Rectangle.md/#MUIA_Rectangle_BarTitle) -- V11 [I.G], `STRPTR`, 0x80426689

### FUNCTION
This attribute describes a text string which will be displayed in group
title style centered in the rectangle. Really only makes sense for
[MUIA_Rectangle_HBar](MUI_Rectangle.md/#MUIA_Rectangle_HBar) type objects.

### SEE ALSO
[MUIA_Rectangle_HBar](MUI_Rectangle.md/#MUIA_Rectangle_HBar)

## MUIA_Rectangle_HBar
### NAME
[MUIA_Rectangle_HBar](MUI_Rectangle.md/#MUIA_Rectangle_HBar) -- V7 [I.G], `BOOL`, 0x8042c943

### FUNCTION
When set to TRUE, MUI draws a horizontal bar in the middle of the rectangle.
Such bars can be used instead of group frames to seperate objects in a
window.

### EXAMPLE
```c++
/* draw a two pixel high bar in the middle
   of an 8 pixel high rectangle */
RectangleObject, MUIA_Rectangle_HBar, TRUE, MUIA_FixHeight, 8, End;
```

### SEE ALSO
[MUIA_Rectangle_VBar](MUI_Rectangle.md/#MUIA_Rectangle_VBar)

## MUIA_Rectangle_VBar
### NAME
[MUIA_Rectangle_VBar](MUI_Rectangle.md/#MUIA_Rectangle_VBar) -- V7 [I.G], `BOOL`, 0x80422204

### FUNCTION
When set to TRUE, MUI draws a vertical bar in the middle of the rectangle.
Such bars can be used instead of group frames to seperate objects in a
window.

### EXAMPLE
```c++
/* draw a two pixel wide bar in the middle
   of an 8 pixel wide rectangle */
RectangleObject, MUIA_Rectangle_HBar, TRUE, MUIA_FixWidth, 8, End;
```

### SEE ALSO
[MUIA_Rectangle_HBar](MUI_Rectangle.md/#MUIA_Rectangle_HBar)

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
