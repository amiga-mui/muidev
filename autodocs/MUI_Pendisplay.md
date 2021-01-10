# Pendisplay.mui
## Super class
[Area.mui](MUI_Area.md)
## Inherited by
* [Poppen.mui](MUI_Poppen.md)
## Background
Pendisplay class takes a struct MUI_PenSpec and displays it. Its main use is
to be sub-classed by Poppen class which adds a popup window to adjust the
MUI_PenSpec. Poppen class should be used by every application that allows
users to configure custom drawing pens.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Pendisplay_Pen](MUI_Pendisplay.md/#MUIA_Pendisplay_Pen)|V13|..G|`ULONG`
[MUIA_Pendisplay_Reference](MUI_Pendisplay.md/#MUIA_Pendisplay_Reference)|V13|ISG|`Object *`
[MUIA_Pendisplay_RGBcolor](MUI_Pendisplay.md/#MUIA_Pendisplay_RGBcolor)|V11|ISG|`struct MUI_RGBColor *`
[MUIA_Pendisplay_Spec](MUI_Pendisplay.md/#MUIA_Pendisplay_Spec)|V11|ISG|`struct MUI_PenSpec  *`

## Methods
Method|Version
------|-------
[MUIM_Pendisplay_SetColormap](MUI_Pendisplay.md/#MUIM_Pendisplay_SetColormap)|V13
[MUIM_Pendisplay_SetMUIPen](MUI_Pendisplay.md/#MUIM_Pendisplay_SetMUIPen)|V13
[MUIM_Pendisplay_SetRGB](MUI_Pendisplay.md/#MUIM_Pendisplay_SetRGB)|V13

## MUIA_Pendisplay_Pen
### NAME
[MUIA_Pendisplay_Pen](MUI_Pendisplay.md/#MUIA_Pendisplay_Pen) -- V13 [..G], `ULONG`, 0x8042a748

### FUNCTION
Between [MUIM_Setup](MUI_Area.md/#MUIM_Setup) and [MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup), this attribute returns the pen number
MUI uses for color representation of the current pendisplay object.

This attribute returns -1 when outside of [MUIM_Setup](MUI_Area.md/#MUIM_Setup)/[MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup) or when
the Pendisplay object didn't allocate a color on its own, e.g. because of
[MUIA_Pendisplay_Reference](MUI_Pendisplay.md/#MUIA_Pendisplay_Reference).

### SEE ALSO
[MUIA_Pendisplay_Reference](MUI_Pendisplay.md/#MUIA_Pendisplay_Reference)

## MUIA_Pendisplay_Reference
### NAME
[MUIA_Pendisplay_Reference](MUI_Pendisplay.md/#MUIA_Pendisplay_Reference) -- V13 [ISG], `Object *`, 0x8042dc24

### FUNCTION
Display exactly this pen, don't allocate one on your own.

### SEE ALSO
[MUIA_Pendisplay_Pen](MUI_Pendisplay.md/#MUIA_Pendisplay_Pen)

## MUIA_Pendisplay_RGBcolor
### NAME
[MUIA_Pendisplay_RGBcolor](MUI_Pendisplay.md/#MUIA_Pendisplay_RGBcolor) -- V11 [ISG], `struct MUI_RGBColor *`, 0x8042a1a9

### FUNCTION
This attribute can be used to set a pen spec via RGB values and to get the RGB
values of the currently set pen.

### NOTES
Since MUI5.0 2020R1 every change of the color will trigger notifications on
[MUIA_Pendisplay_Pen](MUI_Pendisplay.md/#MUIA_Pendisplay_Pen) and MUI_Pendisplay_Spec with the updated values.

### SEE ALSO
[MUIA_Pendisplay_Pen](MUI_Pendisplay.md/#MUIA_Pendisplay_Pen), [MUIA_Pendisplay_Spec](MUI_Pendisplay.md/#MUIA_Pendisplay_Spec)

## MUIA_Pendisplay_Spec
### NAME
[MUIA_Pendisplay_Spec](MUI_Pendisplay.md/#MUIA_Pendisplay_Spec) -- V11 [ISG], `struct MUI_PenSpec  *`, 0x8042a204

### FUNCTION
The black box structure MUI_PenSpec specifies a drawing pen which should be
displayed by Pendisplay class. If you use Poppen class to allow your users
to configure custom drawing pens, its this attribute that you need to get()
and save in your preferences.

Use the functions MUI_ObtainPen() and MUI_ReleasePen() from
muimaster.library and the MUIPEN() macro to get a usable value for SetAPen()
from a struct MUI_PenSpec.

### NOTES
In allmost all cases you will use Poppen class which is a subclass of
Pendisplay class.

Since MUI5.0 2020R1 every change of the pen spec will trigger notifications on
[MUIA_Pendisplay_Pen](MUI_Pendisplay.md/#MUIA_Pendisplay_Pen) and MUI_Pendisplay_RGBcolor with the updated values.

### SEE ALSO
muimaster.library/MUI_ObtainPen(), muimaster.library/MUI_ReleasePen(),
[MUIA_Pendisplay_Pen](MUI_Pendisplay.md/#MUIA_Pendisplay_Pen), [MUIA_Pendisplay_RGBcolor](MUI_Pendisplay.md/#MUIA_Pendisplay_RGBcolor)

## MUIM_Pendisplay_SetColormap
### NAME
[MUIM_Pendisplay_SetColormap](MUI_Pendisplay.md/#MUIM_Pendisplay_SetColormap) -- V13, 0x80426c80

### SYNOPSIS
`DoMethod(obj, MUIM_Pendisplay_SetColormap, LONG colormap);`

### FUNCTION
Switch the pendisplay object to a specific colormap entry.

**`LONG colormap`**
     colormap number

### SEE ALSO
[MUIM_Pendisplay_SetMUIPen](MUI_Pendisplay.md/#MUIM_Pendisplay_SetMUIPen), [MUIM_Pendisplay_SetRGB](MUI_Pendisplay.md/#MUIM_Pendisplay_SetRGB)

## MUIM_Pendisplay_SetMUIPen
### NAME
[MUIM_Pendisplay_SetMUIPen](MUI_Pendisplay.md/#MUIM_Pendisplay_SetMUIPen) -- V13, 0x8042039d

### SYNOPSIS
`DoMethod(obj, MUIM_Pendisplay_SetMUIPen, LONG muipen);`

### FUNCTION
Switch the pendisplay object to a specific MUI pen (MPEN_SHINE, MPEN_SHADOW,
...)

### INPUTS
**`LONG muipen`**
     MUI pen number

### SEE ALSO
[MUIM_Pendisplay_SetColormap](MUI_Pendisplay.md/#MUIM_Pendisplay_SetColormap), [MUIM_Pendisplay_SetRGB](MUI_Pendisplay.md/#MUIM_Pendisplay_SetRGB)

## MUIM_Pendisplay_SetRGB
### NAME
[MUIM_Pendisplay_SetRGB](MUI_Pendisplay.md/#MUIM_Pendisplay_SetRGB) -- V13, 0x8042c131

### SYNOPSIS
`DoMethod(obj, MUIM_Pendisplay_SetRGB, ULONG red, ULONG green, ULONG blue);`

### FUNCTION
Switch the pendisplay object to an RGB value.

### INPUTS
**`ULONG red`**
     red color value

**`ULONG green`**
     green color value

**`ULONG blue`**
     blue color value

### SEE ALSO
[MUIM_Pendisplay_SetMUIPen](MUI_Pendisplay.md/#MUIM_Pendisplay_SetMUIPen), [MUIM_Pendisplay_SetColormap](MUI_Pendisplay.md/#MUIM_Pendisplay_SetColormap)

----
<table class='compact' style='border: none; border-spacing: 0px; margin: 0px' width='100%'>
<tr>
<td style='text-align: left; vertical-align: top' width='33%'>Copyright &copy 1992-2006 by Stefan Stuntz<br>Copyright &copy 2006-2021 by Thore B&ouml;ckelmann, Jens Maus</TD>
<td style='text-align: center; vertical-align: top' width='33%'>
<a href=https://github.com/amiga-mui/muidev>MUI for AmigaOS Homepage</a><br>
<a href=https://github.com/amiga-mui/muidev/blob/master/autodocs/autodocs.md>MUI Autodocs Index</a>
</td>
<td style='text-align: right; vertical-align: top' width='33%'>Updated: 10-Jan-2021</td>
</tr>
</table>
