# Menu.mui
## Super class
[Family.mui](MUI_Family.md)
## Background
Objects of menu class describe exactly one pulldown menu. They don't feature
many options themselves, but as a subclass of Family class, they act as
father for their several menu item objects.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Menu_CopyStrings](MUI_Menu.md/#MUIA_Menu_CopyStrings)|V20|I..|`BOOL`
[MUIA_Menu_Enabled](MUI_Menu.md/#MUIA_Menu_Enabled)|V8|ISG|`BOOL`
[MUIA_Menu_Title](MUI_Menu.md/#MUIA_Menu_Title)|V8|ISG|`STRPTR`

## MUIA_Menu_CopyStrings
### NAME
[MUIA_Menu_CopyStrings](MUI_Menu.md/#MUIA_Menu_CopyStrings) -- V20 [I..], `BOOL`, 0x8042dbe2

### FUNCTION
Set to TRUE if the title string defined by [MUIA_Menu_Title](MUI_Menu.md/#MUIA_Menu_Title) is to be copied.
Otherwise the title will be used directly and must remain valid throughout
the object's life time.

Defaults to FALSE.

### SEE ALSO
[MUIA_Menu_Title](MUI_Menu.md/#MUIA_Menu_Title)

## MUIA_Menu_Enabled
### NAME
[MUIA_Menu_Enabled](MUI_Menu.md/#MUIA_Menu_Enabled) -- V8 [ISG], `BOOL`, 0x8042ed48

### FUNCTION
Enable or disable the complete menu.

## MUIA_Menu_Title
### NAME
[MUIA_Menu_Title](MUI_Menu.md/#MUIA_Menu_Title) -- V8 [ISG], `STRPTR`, 0x8042a0e3

### FUNCTION
Describe the title of the menu. Note that the string is **NOT** copied (unless
[MUIA_Menu_CopyStrings](MUI_Menu.md/#MUIA_Menu_CopyStrings) is set to TRUE) and must remain valid until the menu
object is disposed.

### SEE ALSO
[MUIA_Menu_Enabled](MUI_Menu.md/#MUIA_Menu_Enabled)

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
