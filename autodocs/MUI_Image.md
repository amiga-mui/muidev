# Image.mui
## Super class
[Area.mui](MUI_Area.md)
## Background
Image class is used to display one of MUI's standard images or some selfmade
image data.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Image_BuiltinSpec](MUI_Image.md/#MUIA_Image_BuiltinSpec)|V21|I..|`ULONG`
[MUIA_Image_CopySpec](MUI_Image.md/#MUIA_Image_CopySpec)|V20|I..|`BOOL`
[MUIA_Image_FontMatch](MUI_Image.md/#MUIA_Image_FontMatch)|V4|IS.|`BOOL`
[MUIA_Image_FontMatchHeight](MUI_Image.md/#MUIA_Image_FontMatchHeight)|V4|IS.|`BOOL`
[MUIA_Image_FontMatchString](MUI_Image.md/#MUIA_Image_FontMatchString)|V20|IS.|`CONST_STRPTR`
[MUIA_Image_FontMatchWidth](MUI_Image.md/#MUIA_Image_FontMatchWidth)|V4|IS.|`BOOL`
[MUIA_Image_FreeHoriz](MUI_Image.md/#MUIA_Image_FreeHoriz)|V4|IS.|`BOOL`
[MUIA_Image_FreeVert](MUI_Image.md/#MUIA_Image_FreeVert)|V4|IS.|`BOOL`
[MUIA_Image_OldImage](MUI_Image.md/#MUIA_Image_OldImage)|V4|I..|`struct Image *`
[MUIA_Image_Spec](MUI_Image.md/#MUIA_Image_Spec)|V4|ISG|`STRPTR`
[MUIA_Image_State](MUI_Image.md/#MUIA_Image_State)|V4|IS.|`LONG`

## MUIA_Image_BuiltinSpec
### NAME
[MUIA_Image_BuiltinSpec](MUI_Image.md/#MUIA_Image_BuiltinSpec) -- V21 [I..], `ULONG`, 0x8042b907

### FUNCTION
Specify the builtin image type to be used as fallback image in case loading the
normal image specified by [MUIA_Image_Spec](MUI_Image.md/#MUIA_Image_Spec) fails for some reason. Even if the
builtin image is not the desired one it is still better to get this fallback
image displayed instead of no image at all.

### SEE ALSO
[MUIA_Image_Spec](MUI_Image.md/#MUIA_Image_Spec)

## MUIA_Image_CopySpec
### NAME
[MUIA_Image_CopySpec](MUI_Image.md/#MUIA_Image_CopySpec) -- V20 [I..], `BOOL`, 0x8042a784

### FUNCTION
Let MUI copy the image spec string internally instead of using the spec
literally. This attribute MUST be set to TRUE if a temporary string is to be
used for [MUIA_Image_Spec](MUI_Image.md/#MUIA_Image_Spec).

Defaults to FALSE.

### SEE ALSO
[MUIA_Image_Spec](MUI_Image.md/#MUIA_Image_Spec)

## MUIA_Image_FontMatch
### NAME
[MUIA_Image_FontMatch](MUI_Image.md/#MUIA_Image_FontMatch) -- V4 [IS.], `BOOL`, 0x8042815d

### FUNCTION
If TRUE, width and height of the given image will be scaled to match the
current font. Images are always defined with a reference font of topaz/8,
bigger fonts will make the image grow (as long as its maximum size is big
enough).

### EXAMPLE
The arrows of a scroll bar are e.g. defined with [MUIA_Image_FontMatch](MUI_Image.md/#MUIA_Image_FontMatch).

### SEE ALSO
[MUIA_Image_FontMatch](MUI_Image.md/#MUIA_Image_FontMatch), [MUIA_Image_FontMatchString](MUI_Image.md/#MUIA_Image_FontMatchString), [MUIA_Image_FontMatchWidth](MUI_Image.md/#MUIA_Image_FontMatchWidth)

## MUIA_Image_FontMatchHeight
### NAME
[MUIA_Image_FontMatchHeight](MUI_Image.md/#MUIA_Image_FontMatchHeight) -- V4 [IS.], `BOOL`, 0x80429f26

### FUNCTION
If TRUE, the height of the given image will be scaled to match the current
font. Images are always defined with a reference font of topaz/8, bigger
fonts will make the image grow (as long as its maximum size is big enough).

### SEE ALSO
[MUIA_Image_FontMatch](MUI_Image.md/#MUIA_Image_FontMatch), [MUIA_Image_FontMatchString](MUI_Image.md/#MUIA_Image_FontMatchString), [MUIA_Image_FontMatchWidth](MUI_Image.md/#MUIA_Image_FontMatchWidth)

## MUIA_Image_FontMatchString
### NAME
[MUIA_Image_FontMatchString](MUI_Image.md/#MUIA_Image_FontMatchString) -- V20 [IS.], `CONST_STRPTR`, 0x804263c1

### FUNCTION
By default the font size matching happens against the dimensions of the single
letter 'n'. In case this does not result in sensible dimension the attribute can
be set to valid string to be used for the dimsension calculation instead, i.e.
"W" to use a usually quite "large" letter.

### SEE ALSO
[MUIA_Image_FontMatch](MUI_Image.md/#MUIA_Image_FontMatch), [MUIA_Image_FontMatchHeight](MUI_Image.md/#MUIA_Image_FontMatchHeight), [MUIA_Image_FontMatchWidth](MUI_Image.md/#MUIA_Image_FontMatchWidth)

## MUIA_Image_FontMatchWidth
### NAME
[MUIA_Image_FontMatchWidth](MUI_Image.md/#MUIA_Image_FontMatchWidth) -- V4 [IS.], `BOOL`, 0x804239bf

### FUNCTION
If TRUE, the width of the given image will be scaled to match the current
font. Images are always defined with a reference font of topaz/8, bigger
fonts will make the image grow (as long as its maximum size is big enough).

### SEE ALSO
[MUIA_Image_FontMatch](MUI_Image.md/#MUIA_Image_FontMatch), [MUIA_Image_FontMatchHeight](MUI_Image.md/#MUIA_Image_FontMatchHeight), [MUIA_Image_FontMatchString](MUI_Image.md/#MUIA_Image_FontMatchString)

## MUIA_Image_FreeHoriz
### NAME
[MUIA_Image_FreeHoriz](MUI_Image.md/#MUIA_Image_FreeHoriz) -- V4 [IS.], `BOOL`, 0x8042da84

### FUNCTION
Tell the image if its allowed to get scaled horizontally.

Defaults to FALSE.

### SEE ALSO
[MUIA_Image_FreeVert](MUI_Image.md/#MUIA_Image_FreeVert), [MUIA_Image_FontMatch](MUI_Image.md/#MUIA_Image_FontMatch)

## MUIA_Image_FreeVert
### NAME
[MUIA_Image_FreeVert](MUI_Image.md/#MUIA_Image_FreeVert) -- V4 [IS.], `BOOL`, 0x8042ea28

### FUNCTION
Tell the image if its allowed to get scaled vertically.

Defaults to FALSE.

### SEE ALSO
[MUIA_Image_FreeHoriz](MUI_Image.md/#MUIA_Image_FreeHoriz), [MUIA_Image_FontMatch](MUI_Image.md/#MUIA_Image_FontMatch)

## MUIA_Image_OldImage
### NAME
[MUIA_Image_OldImage](MUI_Image.md/#MUIA_Image_OldImage) -- V4 [I..], `struct Image *`, 0x80424f3d

### FUNCTION
Allows you to use any conventional image structure within a MUI window. The
resulting object is always as big as the image and not resizable.

## MUIA_Image_Spec
### NAME
[MUIA_Image_Spec](MUI_Image.md/#MUIA_Image_Spec) -- V4 [ISG], `STRPTR`, 0x804233d5

### FUNCTION
Specify the type of your image. Usually, you will use one of the predefined
standard images here (one of the MUII_xxx definitions from mui.h), but you
also can supply a string containing a MUI image specification. Image
specifications always starts with a digit, followed by a ':', followed by
some parameters. Currently, the following things are defined (all numeric
parameters need to be ASCII values!):

**`0:<x>`**
     where <x> is between MUII_BACKGROUND and MUII_FILLBACK2 identifying
     a builtin pattern.

**`1:<x>`**
     where <x> identifies a builtin standard image.
     Don't use this, use "6:<x>" instead.

 2:<r>,<g>,<b>:
 where <r>, <g> and <b> are 32-bit RGB color values specified
 as 8-digit hex string (e.g. 00000000 or ffffffff).

**`3:<n>`**
     where <n> is the name of an external BOOPSI image class.

**`4:<n>`**
     where <n> is the name of an external MUI brush.

**`5:<n>`**
     where <n> is the name of an external picture file that should be
     loaded with datatypes.

**`6:<x>`**
     where <x> is between MUII_WindowBack and MUII_Count-1 identifying a
     preconfigured image/background.

The supplied string pointer will be stored internally. Hence you MUST make
sure that the pointer stays valid as long as the object lives. If you cannot
avoid passing a temporary string then you MUST use the [MUIA_Image_CopySpec](MUI_Image.md/#MUIA_Image_CopySpec)
attribute to enforce an internal copy of the string.

### NOTES
If the image is loaded by datatypes (i.e. "5:image.png") the image file will
remain Lock()'d by datatypes.library as long as the image is kept in MUI's
internal image cache. Use the FlushImagespace tool to flush all currently
unused images from the cache.

### SEE ALSO
[MUIA_Image_OldImage](MUI_Image.md/#MUIA_Image_OldImage), [MUIA_Image_CopySpec](MUI_Image.md/#MUIA_Image_CopySpec)

## MUIA_Image_State
### NAME
[MUIA_Image_State](MUI_Image.md/#MUIA_Image_State) -- V4 [IS.], `LONG`, 0x8042a3ad

### FUNCTION
Some MUI images offer different states, you can select one of the by setting
this attribute. Simply use one of the IDS_NORMAL, IDS_SELECTED, ... values
defined in "intuition/imageclass.h".

### NOTES
Objects that respond to user input will automatically toggle their state
between IDS_NORMAL to IDS_SELECTED depending on their [MUIA_Selected](MUI_Area.md/#MUIA_Selected)
attribute.

### SEE ALSO
[MUIA_Image_Spec](MUI_Image.md/#MUIA_Image_Spec)

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
