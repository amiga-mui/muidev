# Bitmap.mui
## Super class
[Area.mui](MUI_Area)
## Inherited by
* [Bodychunk.mui](MUI_Bodychunk)
## Background
The Bitmap class allows including self-made image data in MUI applications.
Usually, image class was intended to be used for this purpose but
unfortunately, its design was not very useful.

In its most simple usage, Bitmap class just display a given BitMap. However,
you can also tell it to do automatic color remapping to match the current
display context and you can define a transparent color to make the BitMap
appear on any background.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Bitmap_Alpha](MUI_Bitmap.md/#MUIA_Bitmap_Alpha)|V20|ISG|`ULONG`
[MUIA_Bitmap_Bitmap](MUI_Bitmap.md/#MUIA_Bitmap_Bitmap)|V8|ISG|`struct BitMap *`
[MUIA_Bitmap_Height](MUI_Bitmap.md/#MUIA_Bitmap_Height)|V8|ISG|`LONG`
[MUIA_Bitmap_MappingTable](MUI_Bitmap.md/#MUIA_Bitmap_MappingTable)|V8|ISG|`UBYTE *`
[MUIA_Bitmap_Precision](MUI_Bitmap.md/#MUIA_Bitmap_Precision)|V11|ISG|`LONG`
[MUIA_Bitmap_RemappedBitmap](MUI_Bitmap.md/#MUIA_Bitmap_RemappedBitmap)|V11|..G|`struct BitMap *`
[MUIA_Bitmap_SourceColors](MUI_Bitmap.md/#MUIA_Bitmap_SourceColors)|V8|ISG|`ULONG *`
[MUIA_Bitmap_Transparent](MUI_Bitmap.md/#MUIA_Bitmap_Transparent)|V8|ISG|`LONG`
[MUIA_Bitmap_UseFriend](MUI_Bitmap.md/#MUIA_Bitmap_UseFriend)|V11|I..|`BOOL`
[MUIA_Bitmap_Width](MUI_Bitmap.md/#MUIA_Bitmap_Width)|V8|ISG|`LONG`

## MUIA_Bitmap_Alpha
### NAME
[MUIA_Bitmap_Alpha](MUI_Bitmap/#MUIA_Bitmap_Alpha) -- V20 [ISG], `ULONG`, 0x80423e71

### FUNCTION
If specified, MUI will consider the BitMap to contain alpha informations.
The only supported BitMap format is 32-bit ARGB. The value of
[MUIA_Bitmap_Alpha](MUI_Bitmap/#MUIA_Bitmap_Alpha) is an ULONG specifying the intensity of the alpha
blitting. You usually want to specify 0xffffffff. Alpha blitting won't work
on CLUT screens.

### SEE ALSO
[MUIA_Bitmap_Bitmap](MUI_Bitmap/#MUIA_Bitmap_Bitmap), [MUIA_Bitmap_Height](MUI_Bitmap/#MUIA_Bitmap_Height), [MUIA_Bitmap_Width](MUI_Bitmap/#MUIA_Bitmap_Width)

## MUIA_Bitmap_Bitmap
### NAME
[MUIA_Bitmap_Bitmap](MUI_Bitmap/#MUIA_Bitmap_Bitmap) -- V8 [ISG], `struct BitMap *`, 0x804279bd

### FUNCTION
This attribute specifies a pointer to a struct BitMap. Note that specifying
only a BitMap isn't enough, you have to tell MUI about the pixel width and
height with [MUIA_Bitmap_Width](MUI_Bitmap/#MUIA_Bitmap_Width) and [MUIA_Bitmap_Height](MUI_Bitmap/#MUIA_Bitmap_Height), too.

If you plan to dynamically modify either the bitmap or any other visibile
stuff you will need to cause the surrounding group to do a full relayout by
first removing the Bitmap object, then set the new attributes and finally
readd the Bitmap object.

### SEE ALSO
[MUIA_Bitmap_Width](MUI_Bitmap/#MUIA_Bitmap_Width), [MUIA_Bitmap_Height](MUI_Bitmap/#MUIA_Bitmap_Height), [MUIA_Bitmap_Transparent](MUI_Bitmap/#MUIA_Bitmap_Transparent),
[MUIA_Bitmap_SourceColors](MUI_Bitmap/#MUIA_Bitmap_SourceColors), [MUIA_Bitmap_MappingTable](MUI_Bitmap/#MUIA_Bitmap_MappingTable)

## MUIA_Bitmap_Height
### NAME
[MUIA_Bitmap_Height](MUI_Bitmap/#MUIA_Bitmap_Height) -- V8 [ISG], `LONG`, 0x80421560

### FUNCTION
Define the pixel height of the BitMap.

Note: By default, the bitmap object has a minimum size of 1 pixel and an
unlimited maxium size. If the space is too small to hold your BitMap, it
will be clipped. Usually, you will use [MUIA_FixWidth](MUI_Area/#MUIA_FixWidth) and [MUIA_FixHeight](MUI_Area/#MUIA_FixHeight) with
BitMap objects to make them always exactly as big as the bitmap.

### SEE ALSO
[MUIA_Bitmap_Bitmap](MUI_Bitmap/#MUIA_Bitmap_Bitmap), [MUIA_Bitmap_Width](MUI_Bitmap/#MUIA_Bitmap_Width), [MUIA_Bitmap_Transparent](MUI_Bitmap/#MUIA_Bitmap_Transparent),
[MUIA_Bitmap_SourceColors](MUI_Bitmap/#MUIA_Bitmap_SourceColors), [MUIA_Bitmap_MappingTable](MUI_Bitmap/#MUIA_Bitmap_MappingTable)

## MUIA_Bitmap_MappingTable
### NAME
[MUIA_Bitmap_MappingTable](MUI_Bitmap/#MUIA_Bitmap_MappingTable) -- V8 [ISG], `UBYTE *`, 0x8042e23d

### FUNCTION
Address of an array of UBYTEs, one for each color of the source BitMap. MUI
will remap the BitMap according to the contents of the array.

Since MUI applications usually don't know about their display environment,
this tag is rarely used. Instead, [MUIA_Bitmap_SourceColors](MUI_Bitmap/#MUIA_Bitmap_SourceColors) can be used to
allow context sensitive color remapping.

### SEE ALSO
[MUIA_Bitmap_Bitmap](MUI_Bitmap/#MUIA_Bitmap_Bitmap), [MUIA_Bitmap_Height](MUI_Bitmap/#MUIA_Bitmap_Height), [MUIA_Bitmap_Width](MUI_Bitmap/#MUIA_Bitmap_Width),
[MUIA_Bitmap_Transparent](MUI_Bitmap/#MUIA_Bitmap_Transparent)

## MUIA_Bitmap_Precision
### NAME
[MUIA_Bitmap_Precision](MUI_Bitmap/#MUIA_Bitmap_Precision) -- V11 [ISG], `LONG`, 0x80420c74

### FUNCTION
Specify the precision value for remapping images. Use the same predefined
values as for ObtainBestPen() here, e.g.
  * PRECISION_EXACT
  * PRECISION_IMAGE
  * PRECISION_ICON
  * PRECISION_GUI

## MUIA_Bitmap_RemappedBitmap
### NAME
[MUIA_Bitmap_RemappedBitmap](MUI_Bitmap/#MUIA_Bitmap_RemappedBitmap) -- V11 [..G], `struct BitMap *`, 0x80423a47

### FUNCTION
Between [MUIM_Setup](MUI_Area/#MUIM_Setup) and [MUIM_Cleanup](MUI_Area/#MUIM_Cleanup), this attribute will hold a pointer to
the remapped bitmap.

## MUIA_Bitmap_SourceColors
### NAME
[MUIA_Bitmap_SourceColors](MUI_Bitmap/#MUIA_Bitmap_SourceColors) -- V8 [ISG], `ULONG *`, 0x80425360

### FUNCTION
This attribute defines the color palette of the source BitMap. If specified,
MUI will try to locate these colors on the current screen and remap the
BitMap accordingly.

You can e.g. specify some great looking 8-color images for several buttons
of your application and MUI will ensure they look fine even on 4-color
screens or on screens with completely different colors.

When running Kickstart V39 or higher, MUI will use ObtainBestPen() to find
or create your colors. Below V39, a simple color-map search is performed to
find the best matching entry, but no colors will be changed.

The source palette is specified with an array of ULONGs, three entries per
color, 32 bits per gun.

### EXAMPLE
```c++
/* MagicWB-like palette for an 8-color image */
const ULONG aboutlogo_colors[24] =
{
  0xaaaaaaaa, 0xaaaaaaaa, 0xa0a0a0a0,
  0x00000000, 0x00000000, 0x00000000,
  0xffffffff, 0xffffffff, 0xffffffff,
  0x66666666, 0x88888888, 0xbbbbbbbb,
  0x99999999, 0x99999999, 0x99999999,
  0xbbbbbbbb, 0xbbbbbbbb, 0xbbbbbbbb,
  0xbbbbbbbb, 0xaaaaaaaa, 0x99999999,
  0xffffffff, 0xbbbbbbbb, 0xaaaaaaaa
};
```

### SEE ALSO
[MUIA_Bitmap_Bitmap](MUI_Bitmap/#MUIA_Bitmap_Bitmap), [MUIA_Bitmap_Height](MUI_Bitmap/#MUIA_Bitmap_Height), [MUIA_Bitmap_Width](MUI_Bitmap/#MUIA_Bitmap_Width),
[MUIA_Bitmap_MappingTable](MUI_Bitmap/#MUIA_Bitmap_MappingTable), [MUIA_Bitmap_MappingTable](MUI_Bitmap/#MUIA_Bitmap_MappingTable)

## MUIA_Bitmap_Transparent
### NAME
[MUIA_Bitmap_Transparent](MUI_Bitmap/#MUIA_Bitmap_Transparent) -- V8 [ISG], `LONG`, 0x80422805

### FUNCTION
If specified, MUI will consider this color of the BitMap to be transparent.
A mask plane will be generated and used for blitting, the background will
shine through.

Currently, only 0 is supported, i.e. only color 0 can be made the "shine
through" color.

### SEE ALSO
[MUIA_Bitmap_Bitmap](MUI_Bitmap/#MUIA_Bitmap_Bitmap), [MUIA_Bitmap_Height](MUI_Bitmap/#MUIA_Bitmap_Height), [MUIA_Bitmap_Width](MUI_Bitmap/#MUIA_Bitmap_Width),
[MUIA_Bitmap_SourceColors](MUI_Bitmap/#MUIA_Bitmap_SourceColors), [MUIA_Bitmap_MappingTable](MUI_Bitmap/#MUIA_Bitmap_MappingTable)

## MUIA_Bitmap_UseFriend
### NAME
[MUIA_Bitmap_UseFriend](MUI_Bitmap/#MUIA_Bitmap_UseFriend) -- V11 [I..], `BOOL`, 0x804239d8

### FUNCTION
This attribute will make MUI to try to allocate the remapped bitmap in a way
that allows fastest displaying.

## MUIA_Bitmap_Width
### NAME
[MUIA_Bitmap_Width](MUI_Bitmap/#MUIA_Bitmap_Width) -- V8 [ISG], `LONG`, 0x8042eb3a

### FUNCTION
Define the pixel width of the BitMap.

Note: By default, the bitmap object has a minimum size of 1 pixel and an
unlimited maxium size. If the space is too small to hold your BitMap, it
will be clipped. Usually, you will use [MUIA_FixWidth](MUI_Area/#MUIA_FixWidth) and [MUIA_FixHeight](MUI_Area/#MUIA_FixHeight) with
BitMap objects to make them always exactly as big as the bitmap.

### SEE ALSO
[MUIA_Bitmap_Bitmap](MUI_Bitmap/#MUIA_Bitmap_Bitmap), [MUIA_Bitmap_Height](MUI_Bitmap/#MUIA_Bitmap_Height), [MUIA_Bitmap_Transparent](MUI_Bitmap/#MUIA_Bitmap_Transparent),
[MUIA_Bitmap_SourceColors](MUI_Bitmap/#MUIA_Bitmap_SourceColors), [MUIA_Bitmap_MappingTable](MUI_Bitmap/#MUIA_Bitmap_MappingTable)

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
