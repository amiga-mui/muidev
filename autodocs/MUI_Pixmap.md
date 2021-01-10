# Pixmap.mui
## Super class
[Area.mui](MUI_Area.md)
## Background
The Pixmap class allows including self-made inlined image data in MUI
applications.

In its most simple usage, Pixmap class just displays a given inlined array
of raw image date of a certain type.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Pixmap_Alpha](MUI_Pixmap.md/#MUIA_Pixmap_Alpha)|V20|ISG|`ULONG`
[MUIA_Pixmap_CLUT](MUI_Pixmap.md/#MUIA_Pixmap_CLUT)|V20|ISG|`ULONG *`
[MUIA_Pixmap_CLUTSize](MUI_Pixmap.md/#MUIA_Pixmap_CLUTSize)|V20|ISG|`ULONG`
[MUIA_Pixmap_CompressedSize](MUI_Pixmap.md/#MUIA_Pixmap_CompressedSize)|V20|ISG|`ULONG`
[MUIA_Pixmap_Compression](MUI_Pixmap.md/#MUIA_Pixmap_Compression)|V20|ISG|`ULONG`
[MUIA_Pixmap_Data](MUI_Pixmap.md/#MUIA_Pixmap_Data)|V20|ISG|`CONST_APTR`
[MUIA_Pixmap_Format](MUI_Pixmap.md/#MUIA_Pixmap_Format)|V20|ISG|`ULONG`
[MUIA_Pixmap_Height](MUI_Pixmap.md/#MUIA_Pixmap_Height)|V20|ISG|`LONG`
[MUIA_Pixmap_TransparencyThreshold](MUI_Pixmap.md/#MUIA_Pixmap_TransparencyThreshold)|V20|ISG|`UBYTE`
[MUIA_Pixmap_UncompressedData](MUI_Pixmap.md/#MUIA_Pixmap_UncompressedData)|V20|..G|`CONST_APTR`
[MUIA_Pixmap_Width](MUI_Pixmap.md/#MUIA_Pixmap_Width)|V20|ISG|`LONG`

## Methods
Method|Version
------|-------
[MUIM_Pixmap_DrawSection](MUI_Pixmap.md/#MUIM_Pixmap_DrawSection)|V20

## MUIA_Pixmap_Alpha
### NAME
[MUIA_Pixmap_Alpha](MUI_Pixmap.md/#MUIA_Pixmap_Alpha) -- V20 [ISG], `ULONG`, 0x80421fef

### FUNCTION
This attribute specifies an additional alpha value to be applied to the
image data being drawn. The default value is 0xffffffff which will the draw
the image with full intensity. Alpha blitting won't work on CLUT screens or
with CLUT image data.

### SEE ALSO
[MUIA_Pixmap_Data](MUI_Pixmap.md/#MUIA_Pixmap_Data), [MUIA_Pixmap_Format](MUI_Pixmap.md/#MUIA_Pixmap_Format), [MUIA_Pixmap_Height](MUI_Pixmap.md/#MUIA_Pixmap_Height),
[MUIA_Pixmap_Width](MUI_Pixmap.md/#MUIA_Pixmap_Width)

## MUIA_Pixmap_CLUT
### NAME
[MUIA_Pixmap_CLUT](MUI_Pixmap.md/#MUIA_Pixmap_CLUT) -- V20 [ISG], `ULONG *`, 0x8042042a

### FUNCTION
Define the color map to be used for CLUT8 raw image data. If no color map is
given an internal default color map will be used instead.

### SEE ALSO
[MUIA_Pixmap_Data](MUI_Pixmap.md/#MUIA_Pixmap_Data), [MUIA_Pixmap_Format](MUI_Pixmap.md/#MUIA_Pixmap_Format), [MUIA_Pixmap_CLUTSize](MUI_Pixmap.md/#MUIA_Pixmap_CLUTSize)

## MUIA_Pixmap_CLUTSize
### NAME
[MUIA_Pixmap_CLUTSize](MUI_Pixmap.md/#MUIA_Pixmap_CLUTSize) -- V20 [ISG], `ULONG`, 0x8042bde3

### FUNCTION
Define the number of colors in the color map given by [MUIA_Pixmap_CLUT](MUI_Pixmap.md/#MUIA_Pixmap_CLUT).

Defaults to 256.

### SEE ALSO
[MUIA_Pixmap_Data](MUI_Pixmap.md/#MUIA_Pixmap_Data), [MUIA_Pixmap_Format](MUI_Pixmap.md/#MUIA_Pixmap_Format), [MUIA_Pixmap_CLUT](MUI_Pixmap.md/#MUIA_Pixmap_CLUT)

## MUIA_Pixmap_CompressedSize
### NAME
[MUIA_Pixmap_CompressedSize](MUI_Pixmap.md/#MUIA_Pixmap_CompressedSize) -- V20 [ISG], `ULONG`, 0x8042e7e4

### FUNCTION
This attribute specifies the size of the compressed raw image data. It is
only required if the raw image data are compressed at all.

### SEE ALSO
[MUIA_Pixmap_Compression](MUI_Pixmap.md/#MUIA_Pixmap_Compression)

## MUIA_Pixmap_Compression
### NAME
[MUIA_Pixmap_Compression](MUI_Pixmap.md/#MUIA_Pixmap_Compression) -- V20 [ISG], `ULONG`, 0x8042ce74

### SPECIAL INPUTS
  * MUIV_Pixmap_Compression_None
  * MUIV_Pixmap_Compression_RLE
  * MUIV_Pixmap_Compression_BZip2
  * MUIV_Pixmap_Compression_Z
  * MUIV_Pixmap_Compression_LZMA

### FUNCTION
This attribute specifies the compression method being used for the raw image
data.

Defaults to MUIV_Pixmap_Compression_None (uncompressed data)

### SEE ALSO
[MUIA_Pixmap_CompressedSize](MUI_Pixmap.md/#MUIA_Pixmap_CompressedSize)

## MUIA_Pixmap_Data
### NAME
[MUIA_Pixmap_Data](MUI_Pixmap.md/#MUIA_Pixmap_Data) -- V20 [ISG], `CONST_APTR`, 0x80429ea0

### FUNCTION
This attribute specifies a pointer to an array of the raw image data. Note
that specifying only the raw data isn't enough, you have to tell MUI about
the pixel width and height with [MUIA_Pixmap_Width](MUI_Pixmap.md/#MUIA_Pixmap_Width) and [MUIA_Pixmap_Height](MUI_Pixmap.md/#MUIA_Pixmap_Height),
too, as well as the format of data with [MUIA_Pixmap_Format](MUI_Pixmap.md/#MUIA_Pixmap_Format). For color mapped
raw image data the palette must be given with [MUIA_Pixmap_CLUT](MUI_Pixmap.md/#MUIA_Pixmap_CLUT).

### SEE ALSO
[MUIA_Pixmap_Width](MUI_Pixmap.md/#MUIA_Pixmap_Width), [MUIA_Pixmap_Height](MUI_Pixmap.md/#MUIA_Pixmap_Height), [MUIA_Pixmap_Format](MUI_Pixmap.md/#MUIA_Pixmap_Format), [MUIA_Pixmap_CLUT](MUI_Pixmap.md/#MUIA_Pixmap_CLUT)

## MUIA_Pixmap_Format
### NAME
[MUIA_Pixmap_Format](MUI_Pixmap.md/#MUIA_Pixmap_Format) -- V20 [ISG], `ULONG`, 0x8042ab14

### SPECIAL INPUTS
  * MUIV_Pixmap_Format_CLUT8
  * MUIV_Pixmap_Format_RGB24
  * MUIV_Pixmap_Format_ARGB32

### FUNCTION
This attribute specifies the format of the raw image data. It is possible to
use color mapped (CLUT8), 24bit RGB and 32bit ARGB image data. For CLUT8
images the palette can be specified with [MUIA_Pixmap_CLUT](MUI_Pixmap.md/#MUIA_Pixmap_CLUT), otherwise the
screen's palette will be used.

### SEE ALSO
[MUIA_Pixmap_Data](MUI_Pixmap.md/#MUIA_Pixmap_Data), [MUIA_Pixmap_CLUT](MUI_Pixmap.md/#MUIA_Pixmap_CLUT)

## MUIA_Pixmap_Height
### NAME
[MUIA_Pixmap_Height](MUI_Pixmap.md/#MUIA_Pixmap_Height) -- V20 [ISG], `LONG`, 0x804288be

### FUNCTION
Define the pixel height of the raw image data.

### NOTES
By default, the image object has a minimum size of 1 pixel and an unlimited
maxium size. If the space is too small to hold your image, it will be
clipped. Usually, you will use [MUIA_FixWidth](MUI_Area.md/#MUIA_FixWidth) and [MUIA_FixHeight](MUI_Area.md/#MUIA_FixHeight) with Pixmap
objects to make them always exactly as big as the image.

### SEE ALSO
[MUIA_Pixmap_Data](MUI_Pixmap.md/#MUIA_Pixmap_Data), [MUIA_Pixmap_Width](MUI_Pixmap.md/#MUIA_Pixmap_Width)

## MUIA_Pixmap_TransparencyThreshold
### NAME
[MUIA_Pixmap_TransparencyThreshold](MUI_Pixmap.md/#MUIA_Pixmap_TransparencyThreshold) -- V20 [ISG], `UBYTE`, 0x8042437c

### FUNCTION
Define the transparency threshold when dithering ARGB data.

Pixels with an alpha value larger than the threshold value will be treated
as non-transparent. This attribute has no effect on hi/truecolor screens.
Defaults to 0x7f (50%).

## MUIA_Pixmap_UncompressedData
### NAME
[MUIA_Pixmap_UncompressedData](MUI_Pixmap.md/#MUIA_Pixmap_UncompressedData) -- V20 [..G], `CONST_APTR`, 0x8042b085

### FUNCTION
A pointer to the uncompressed data is returned, or NULL if decompression
failed. The returned data are strictly read-only!

### SEE ALSO
[MUIA_Pixmap_Data](MUI_Pixmap.md/#MUIA_Pixmap_Data), [MUIA_Pixmap_Compression](MUI_Pixmap.md/#MUIA_Pixmap_Compression)

## MUIA_Pixmap_Width
### NAME
[MUIA_Pixmap_Width](MUI_Pixmap.md/#MUIA_Pixmap_Width) -- V20 [ISG], `LONG`, 0x8042ccb8

### FUNCTION
Define the pixel width of the raw image data.

### NOTES
By default, the image object has a minimum size of 1 pixel and an unlimited
maxium size. If the space is too small to hold your image, it will be
clipped. Usually, you will use [MUIA_FixWidth](MUI_Area.md/#MUIA_FixWidth) and [MUIA_FixHeight](MUI_Area.md/#MUIA_FixHeight) with Pixmap
objects to make them always exactly as big as the image.

### SEE ALSO
[MUIA_Pixmap_Data](MUI_Pixmap.md/#MUIA_Pixmap_Data), [MUIA_Pixmap_Height](MUI_Pixmap.md/#MUIA_Pixmap_Height)

## MUIM_Pixmap_DrawSection
### NAME
[MUIM_Pixmap_DrawSection](MUI_Pixmap.md/#MUIM_Pixmap_DrawSection) -- V20, 0x8042ce0f

### SYNOPSIS
`DoMethod(obj, MUIM_Pixmap_DrawSection, LONG sx, LONG sy, LONG sw, LONG sh, struct MUI_RenderInfo *mri, LONG dx, LONG dy, ULONG alpha);`

### FUNCTION
Call this method instead of MUI_Redraw() to draw just a section of the
complete pixmap with a definite alpha transparency which might be different
from the globally set alpha transparency.

### INPUTS
**`LONG sx`**
     source left coordinate of the section

**`LONG sy`**
     source top coordinate of the section

**`LONG sw`**
     source width of the section

**`LONG sh`**
     source height of the section

**`struct MUI_RenderInfo *mri`**
     MUI_RenderInfo structure to draw the pixmap section to

**`LONG dx`**
     destination left coordinate

**`LONG dy`**
     destination top coordinate

**`ULONG alpha`**
     transparency

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
