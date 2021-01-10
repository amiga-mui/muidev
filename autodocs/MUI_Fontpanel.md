# Fontpanel.mui
## Super class
[Panel.mui](MUI_Panel.md)
## Background
Fontpanel class is MUI's replacement for ASL font requesters to provide the
extended font styles, sizing and coloring. Furthermore it offers the
possibility to sort the fonts into several font families, including user
defined families.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Fontpanel_ShowCollection](MUI_Fontpanel.md/#MUIA_Fontpanel_ShowCollection)|V20|I..|`LONG`

## MUIA_Fontpanel_ShowCollection
### NAME
[MUIA_Fontpanel_ShowCollection](MUI_Fontpanel.md/#MUIA_Fontpanel_ShowCollection) -- V20 [I..], `LONG`, 0x804225ea

### SPECIAL INPUTS
  * MUIV_Fontpanel_ShowCollection_All
  * MUIV_Fontpanel_ShowCollection_FixedWidth
  * MUIV_Fontpanel_ShowCollection_Bitmap
  * MUIV_Fontpanel_ShowCollection_TrueType
  * MUIV_Fontpanel_ShowCollection_User

### FUNCTION
Usually a font panel will allow the user to select a font from all standard
and user defined font families. However, sometimes it might be necessary
to restrict this selection to i.e. TrueType fonts when bitmap fonts cannot
be used for application specific reasons.

This attribute allows to specify the types of font families to select from.
Just pass a logical OR of the suitable MUIV_Fontpanel_ShowCollection_#?
values.

### EXAMPLE
```c++
/* let the user choose TrueType fonts only */
FontpanelObject,
  MUIA_Fontpanel_ShowCollection, MUIV_Fontpanel_ShowCollection_TrueType,
  End;
```

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
