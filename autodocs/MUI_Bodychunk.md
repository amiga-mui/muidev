# Bodychunk.mui
## Super class
[Bitmap.mui](MUI_Bitmap.md)
## Background
Big and colorful images (e.g. About-Logos) usually take lots of space when
stored in a traditional BitMap structure. To save memory, you can decide to
have the picture compressed in your code and use the Bodychunk class instead
of the Bitmap class for displaying. MUI will then automatically decompress
your image when its about to appear in a window.

Since Bodychunk class is a subclass of Bitmap class, you can of course use
all the Bitmaps remapping and transparency features.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Bodychunk_Body](MUI_Bodychunk.md/#MUIA_Bodychunk_Body)|V8|ISG|`UBYTE *`
[MUIA_Bodychunk_Compression](MUI_Bodychunk.md/#MUIA_Bodychunk_Compression)|V8|ISG|`UBYTE`
[MUIA_Bodychunk_Depth](MUI_Bodychunk.md/#MUIA_Bodychunk_Depth)|V8|ISG|`LONG`
[MUIA_Bodychunk_Masking](MUI_Bodychunk.md/#MUIA_Bodychunk_Masking)|V8|ISG|`UBYTE`

## MUIA_Bodychunk_Body
### NAME
[MUIA_Bodychunk_Body](MUI_Bodychunk/#MUIA_Bodychunk_Body) -- V8 [ISG], `UBYTE *`, 0x8042ca67

### FUNCTION
Specify a pointer to the BODY data of your picture. This BODY data must
follow normal IFF/ILBM conventions.

You have to supply [MUIA_Bitmap_Width](MUI_Bitmap/#MUIA_Bitmap_Width), [MUIA_Bitmap_Height](MUI_Bitmap/#MUIA_Bitmap_Height) and
[MUIA_Bodychunk_Depth](MUI_Bodychunk/#MUIA_Bodychunk_Depth) to describe the contents of the BODY data, otherwise
MUI will fail to decompress it.

Body data may be shared between different Bodychunk objects and does not
need to be in chip ram.

### SEE ALSO
[MUIA_Bodychunk_Depth](MUI_Bodychunk/#MUIA_Bodychunk_Depth), [MUIA_Bodychunk_Compression](MUI_Bodychunk/#MUIA_Bodychunk_Compression), [MUIA_Bodychunk_Masking](MUI_Bodychunk/#MUIA_Bodychunk_Masking)

## MUIA_Bodychunk_Compression
### NAME
[MUIA_Bodychunk_Compression](MUI_Bodychunk/#MUIA_Bodychunk_Compression) -- V8 [ISG], `UBYTE`, 0x8042de5f

### FUNCTION
MUI is able to uncompress byte&run compressed BODY chunks automatically. If
your data is compressed, you must supply a value of cmpByteRun1 (==1) for
this tag. Other compression techniques are not supported.

Omitting this tag or setting it to 0 indicates that the BODY data is
uncompressed. Using the Bodychunk class doesn't make much sense in this case
since its main purpose is to save memory for big images.

### SEE ALSO
[MUIA_Bodychunk_Masking](MUI_Bodychunk/#MUIA_Bodychunk_Masking), [MUIA_Bodychunk_Body](MUI_Bodychunk/#MUIA_Bodychunk_Body)

## MUIA_Bodychunk_Depth
### NAME
[MUIA_Bodychunk_Depth](MUI_Bodychunk/#MUIA_Bodychunk_Depth) -- V8 [ISG], `LONG`, 0x8042c392

### FUNCTION
Specify the depth of your picture here. This tag is required for correct
BODY chunk parsing. Also remember to use [MUIA_Bodychunk_Masking](MUI_Bodychunk/#MUIA_Bodychunk_Masking) if your BODY
data contains a masking bitplane.

### SEE ALSO
[MUIA_Bodychunk_Body](MUI_Bodychunk/#MUIA_Bodychunk_Body), [MUIA_Bodychunk_Masking](MUI_Bodychunk/#MUIA_Bodychunk_Masking)

## MUIA_Bodychunk_Masking
### NAME
[MUIA_Bodychunk_Masking](MUI_Bodychunk/#MUIA_Bodychunk_Masking) -- V8 [ISG], `UBYTE`, 0x80423b0e

### FUNCTION
You must indicate if your BODY data contains a masking plane. Currently, MUI
does not use this masking plane for any purpose, but this attribute is
required to allow correct parsing of the BODY data.

### SEE ALSO
[MUIA_Bodychunk_Body](MUI_Bodychunk/#MUIA_Bodychunk_Body), [MUIA_Bodychunk_Compression](MUI_Bodychunk/#MUIA_Bodychunk_Compression)

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
