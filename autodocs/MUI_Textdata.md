# Textdata.mui
## Super class
[Notify.mui](MUI_Notify.md)
## Background
Usually all text displayed in a MUI GUI is limited to ISO-8859-1 encoded
texts as this is the Amiga standard text encoding.
Before Textdata class was added it was very hard to let MUI handle text
strings with other encodings like UTF8, which are quite popular on other
systems. Using Textdata class works around this problem, at least for simple
text label objects. Textdata objects convert a given string with a specific
encoding to the system's default chartset using the conversion functions of
codesets.library.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Textdata_Contents](MUI_Textdata.md/#MUIA_Textdata_Contents)|V21|I.G|`CONST_STRPTR`
[MUIA_Textdata_Encoding](MUI_Textdata.md/#MUIA_Textdata_Encoding)|V21|I.G|`ULONG`
[MUIA_Textdata_SourceBytes](MUI_Textdata.md/#MUIA_Textdata_SourceBytes)|V21|I..|`LONG`
[MUIA_Textdata_SourceEncoding](MUI_Textdata.md/#MUIA_Textdata_SourceEncoding)|V21|I..|`ULONG`

## Methods
Method|Version
------|-------
[MUIM_Textdata_Convert](MUI_Textdata.md/#MUIM_Textdata_Convert)|V21

## MUIA_Textdata_Contents
### NAME
[MUIA_Textdata_Contents](MUI_Textdata/#MUIA_Textdata_Contents) -- V21 [I.G], `CONST_STRPTR`, 0x80420c3f

### FUNCTION
Define the object's text contents. MUI's Text class will convert this string
to whatever encoding it requires before it is finally displayed on the
screen using the [MUIM_Textdata_Convert](MUI_Textdata/#MUIM_Textdata_Convert) method.

There are some macros defined for convenience to cover the most common
encodings:

  * Textdata():  a string encoded with the system's default encoding
  * ATextdata(): a ISO-8859-1 encoded string
  * LTextdata(): a UCS-2/UTF-16 encoded string
  * UTextdata(): a UTF-8 encoded string

### SEE ALSO
[MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents)

## MUIA_Textdata_Encoding
### NAME
[MUIA_Textdata_Encoding](MUI_Textdata/#MUIA_Textdata_Encoding) -- V21 [I.G], `ULONG`, 0x8042c587

### FUNCTION
This attribute specifies the contents' encoding. It must be one of the MIB
numbers included in the mui.h header file.

Defaults to the system's default charset.

### SEE ALSO
[MUIA_Textdata_Contents](MUI_Textdata/#MUIA_Textdata_Contents)

## MUIA_Textdata_SourceBytes
### NAME
[MUIA_Textdata_SourceBytes](MUI_Textdata/#MUIA_Textdata_SourceBytes) -- V21 [I..], `LONG`, 0x804242c0

### FUNCTION

### SEE ALSO
[MUIA_Textdata_Contents](MUI_Textdata/#MUIA_Textdata_Contents)

## MUIA_Textdata_SourceEncoding
### NAME
[MUIA_Textdata_SourceEncoding](MUI_Textdata/#MUIA_Textdata_SourceEncoding) -- V21 [I..], `ULONG`, 0x80426d1a

### FUNCTION

### SEE ALSO
[MUIA_Textdata_Contents](MUI_Textdata/#MUIA_Textdata_Contents)

## MUIM_Textdata_Convert
### NAME
[MUIM_Textdata_Convert](MUI_Textdata/#MUIM_Textdata_Convert) -- V21, 0x80425988

### SYNOPSIS
`DoMethod(obj, MUIM_Textdata_Convert, ULONG encoding);`

### FUNCTION
This method converts the initially specified content string to the given
encoding.

### INPUTS
**`ULONG encoding`**
     destination encoding

### RESULT
A pointer to the converted string or NULL on failure. This string is
strictly read-only.

### SEE ALSO
[MUIA_Textdata_Contents](MUI_Textdata/#MUIA_Textdata_Contents)

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
