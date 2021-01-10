# Filepanel.mui
## Super class
[Panel.mui](MUI_Panel.md)
## Background
Filepanel class offers a full featured replacement for ASL file requesters.
As a replacement it understands most of ASL's file requester attributes or
it offers suitable own attributes.

In addition to ASL requesters it offers a directory history and additional
navigation buttons to quickly jump from one directory to a parent or
previously child directory.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Filepanel_AcceptPattern](MUI_Filepanel.md/#MUIA_Filepanel_AcceptPattern)|V20|I.G|`STRPTR`
[MUIA_Filepanel_DoMultiSelect](MUI_Filepanel.md/#MUIA_Filepanel_DoMultiSelect)|V20|I.G|`BOOL`
[MUIA_Filepanel_DoPatterns](MUI_Filepanel.md/#MUIA_Filepanel_DoPatterns)|V20|I.G|`BOOL`
[MUIA_Filepanel_DoSaveMode](MUI_Filepanel.md/#MUIA_Filepanel_DoSaveMode)|V20|I.G|`BOOL`
[MUIA_Filepanel_Drawer](MUI_Filepanel.md/#MUIA_Filepanel_Drawer)|V20|ISG|`STRPTR`
[MUIA_Filepanel_DrawersOnly](MUI_Filepanel.md/#MUIA_Filepanel_DrawersOnly)|V20|I.G|`BOOL`
[MUIA_Filepanel_File](MUI_Filepanel.md/#MUIA_Filepanel_File)|V20|ISG|`STRPTR`
[MUIA_Filepanel_FilterDrawers](MUI_Filepanel.md/#MUIA_Filepanel_FilterDrawers)|V20|I.G|`BOOL`
[MUIA_Filepanel_FilterFunc](MUI_Filepanel.md/#MUIA_Filepanel_FilterFunc)|V20|I.G|`struct Hook *`
[MUIA_Filepanel_Pattern](MUI_Filepanel.md/#MUIA_Filepanel_Pattern)|V20|ISG|`STRPTR`
[MUIA_Filepanel_RejectIcons](MUI_Filepanel.md/#MUIA_Filepanel_RejectIcons)|V20|I.G|`BOOL`
[MUIA_Filepanel_RejectPattern](MUI_Filepanel.md/#MUIA_Filepanel_RejectPattern)|V20|I.G|`STRPTR`

## MUIA_Filepanel_AcceptPattern
### NAME
[MUIA_Filepanel_AcceptPattern](MUI_Filepanel.md/#MUIA_Filepanel_AcceptPattern) -- V20 [I.G], `STRPTR`, 0x80426f3b

### FUNCTION
Entries not matching this pattern are rejected. Note that the pattern has to
be parsed with dos.library/ParsePatternNoCase(). Empty strings are handled
like no pattern string.

### SEE ALSO
[MUIA_Filepanel_RejectPattern](MUI_Filepanel.md/#MUIA_Filepanel_RejectPattern), [MUIA_Filepanel_FilterDrawers](MUI_Filepanel.md/#MUIA_Filepanel_FilterDrawers)

## MUIA_Filepanel_DoMultiSelect
### NAME
[MUIA_Filepanel_DoMultiSelect](MUI_Filepanel.md/#MUIA_Filepanel_DoMultiSelect) -- V20 [I.G], `BOOL`, 0x8042fd78

### FUNCTION
Set this attribute to TRUE to let the user select multiple files at once.
This attribute excludes [MUIA_Filepanel_DoSaveMode](MUI_Filepanel.md/#MUIA_Filepanel_DoSaveMode).

Defaults to FALSE.

## MUIA_Filepanel_DoPatterns
### NAME
[MUIA_Filepanel_DoPatterns](MUI_Filepanel.md/#MUIA_Filepanel_DoPatterns) -- V20 [I.G], `BOOL`, 0x80420b3b

### FUNCTION
Set this attribute to TRUE to case a pattern gadget to be displays.

Defaults to FALSE.

## MUIA_Filepanel_DoSaveMode
### NAME
[MUIA_Filepanel_DoSaveMode](MUI_Filepanel.md/#MUIA_Filepanel_DoSaveMode) -- V20 [I.G], `BOOL`, 0x80429022

### FUNCTION
Set this attribute to TRUE when the file panel is being used for saving.

Defaults to FALSE.

## MUIA_Filepanel_Drawer
### NAME
[MUIA_Filepanel_Drawer](MUI_Filepanel.md/#MUIA_Filepanel_Drawer) -- V20 [ISG], `STRPTR`, 0x8042e802

### FUNCTION
Initial contents of the panel's Drawer string object.

### SEE ALSO
[MUIA_Filepanel_File](MUI_Filepanel.md/#MUIA_Filepanel_File)

## MUIA_Filepanel_DrawersOnly
### NAME
[MUIA_Filepanel_DrawersOnly](MUI_Filepanel.md/#MUIA_Filepanel_DrawersOnly) -- V20 [I.G], `BOOL`, 0x80427726

### FUNCTION
Indicate whether you only want drawers to be displayed.

## MUIA_Filepanel_File
### NAME
[MUIA_Filepanel_File](MUI_Filepanel.md/#MUIA_Filepanel_File) -- V20 [ISG], `STRPTR`, 0x80427acf

### FUNCTION
Initial contents of the panel's File string object.

### SEE ALSO
[MUIA_Filepanel_Drawer](MUI_Filepanel.md/#MUIA_Filepanel_Drawer)

## MUIA_Filepanel_FilterDrawers
### NAME
[MUIA_Filepanel_FilterDrawers](MUI_Filepanel.md/#MUIA_Filepanel_FilterDrawers) -- V20 [I.G], `BOOL`, 0x804298a1

### FUNCTION
Set this attribute to TRUE if you want the [MUIA_Filepanel_AcceptPattern](MUI_Filepanel.md/#MUIA_Filepanel_AcceptPattern),
[MUIA_Filepanel_RejectPattern](MUI_Filepanel.md/#MUIA_Filepanel_RejectPattern) and the Pattern string object to apply to
drawer names as well. Normally drawers are always displayed.

Defaults to FALSE.

### SEE ALSO
[MUIA_Filepanel_AcceptPattern](MUI_Filepanel.md/#MUIA_Filepanel_AcceptPattern), [MUIA_Filepanel_RejectPattern](MUI_Filepanel.md/#MUIA_Filepanel_RejectPattern),
[MUIA_Filepanel_Pattern](MUI_Filepanel.md/#MUIA_Filepanel_Pattern)

## MUIA_Filepanel_FilterFunc
### NAME
[MUIA_Filepanel_FilterFunc](MUI_Filepanel.md/#MUIA_Filepanel_FilterFunc) -- V20 [I.G], `struct Hook *`, 0x80429c9d

### FUNCTION
A hook to call for each file encountered. If the hook function returns TRUE,
the file is included in the file list, otherwise it is rejected and not
displayed. The function receives the following parameters:

**`struct Hook *hook (in A0)`**
     the hook itself.

**`Object *obj (in A2)`**
     a pointer to an ASL FileRequester structure.

**`struct AnchorPath *ap (in A1)`**
     a pointer to an initialized AnchorPath structure.

All other filter attributes are ignored when a [MUIA_Filepanel_FilterFunc](MUI_Filepanel.md/#MUIA_Filepanel_FilterFunc) is
set.

### SEE ALSO
[MUIA_Filepanel_AcceptPattern](MUI_Filepanel.md/#MUIA_Filepanel_AcceptPattern), [MUIA_Filepanel_RejectPattern](MUI_Filepanel.md/#MUIA_Filepanel_RejectPattern),
[MUIA_Filepanel_Pattern](MUI_Filepanel.md/#MUIA_Filepanel_Pattern)

## MUIA_Filepanel_Pattern
### NAME
[MUIA_Filepanel_Pattern](MUI_Filepanel.md/#MUIA_Filepanel_Pattern) -- V20 [ISG], `STRPTR`, 0x8042c330

### FUNCTION
Set a DOS pattern to match all found file names against. The given pattern
string will be used in a case insensitive way if neither the accept nor the
reject pattern excluded the file from exclusion.

### EXAMPLE
```c++
set(panel, MUIA_Filepanel_Pattern, "#?.png");
```

### SEE ALSO
[MUIA_Filepanel_AcceptPattern](MUI_Filepanel.md/#MUIA_Filepanel_AcceptPattern), [MUIA_Filepanel_RejectPattern](MUI_Filepanel.md/#MUIA_Filepanel_RejectPattern)

## MUIA_Filepanel_RejectIcons
### NAME
[MUIA_Filepanel_RejectIcons](MUI_Filepanel.md/#MUIA_Filepanel_RejectIcons) -- V20 [I.G], `BOOL`, 0x80423450

### FUNCTION
Indicate whether you want icons (*.info files) to be rejected.

## MUIA_Filepanel_RejectPattern
### NAME
[MUIA_Filepanel_RejectPattern](MUI_Filepanel.md/#MUIA_Filepanel_RejectPattern) -- V20 [I.G], `STRPTR`, 0x804281ab

### FUNCTION
Entries matching this pattern are rejected. Note that the pattern has to be
parsed with dos.library/ParsePatternNoCase(). Empty strings are handled like
no pattern string.

### SEE ALSO
[MUIA_Filepanel_AcceptPattern](MUI_Filepanel.md/#MUIA_Filepanel_AcceptPattern), [MUIA_Filepanel_FilterDrawers](MUI_Filepanel.md/#MUIA_Filepanel_FilterDrawers)

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
