# Keyadjust.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
Keyadjust class provides a standardized way to let the user enter keyboard
shortcuts for specific actions. The shortcut is checked for consistency and
correctness to able to parse it using system functions. Such shortcuts can even
be used outside MUI if they are parsed using utility/ParseIX().

It is also possible to define more than a single shortcut for an action. Several
shortcuts will be separated by commas. The popup button will open a menu to let
the user remove single shortcuts or add additional ones.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Keyadjust_AllowDoubleClick](MUI_Keyadjust.md/#MUIA_Keyadjust_AllowDoubleClick)|V20|ISG|`BOOL`
[MUIA_Keyadjust_AllowMouseEvents](MUI_Keyadjust.md/#MUIA_Keyadjust_AllowMouseEvents)|V20|ISG|`BOOL`
[MUIA_Keyadjust_AllowMultipleKeys](MUI_Keyadjust.md/#MUIA_Keyadjust_AllowMultipleKeys)|V20|ISG|`BOOL`
[MUIA_Keyadjust_AllowTripleClick](MUI_Keyadjust.md/#MUIA_Keyadjust_AllowTripleClick)|V20|ISG|`BOOL`
[MUIA_Keyadjust_Key](MUI_Keyadjust.md/#MUIA_Keyadjust_Key)|V20|ISG|`STRPTR`

## MUIA_Keyadjust_AllowDoubleClick
### NAME
[MUIA_Keyadjust_AllowDoubleClick](MUI_Keyadjust/#MUIA_Keyadjust_AllowDoubleClick) -- V20 [ISG], `BOOL`, 0x8042be82

### FUNCTION
Setting this attribute to FALSE will disable double click handling for the
embedded string object.

### SEE ALSO
[MUIA_Keyadjust_AllowTripleClick](MUI_Keyadjust/#MUIA_Keyadjust_AllowTripleClick)

## MUIA_Keyadjust_AllowMouseEvents
### NAME
[MUIA_Keyadjust_AllowMouseEvents](MUI_Keyadjust/#MUIA_Keyadjust_AllowMouseEvents) -- V20 [ISG], `BOOL`, 0x8042b61c

### FUNCTION
Also allow mouse events for shortcuts. By default only keyboard events are
allowed and mouse events are used for Keyadjust class' own GUI handling.

## MUIA_Keyadjust_AllowMultipleKeys
### NAME
[MUIA_Keyadjust_AllowMultipleKeys](MUI_Keyadjust/#MUIA_Keyadjust_AllowMultipleKeys) -- V20 [ISG], `BOOL`, 0x8042890b

### FUNCTION
Settings this attribute to FALSE will forbid several shortcuts to be handled
by one object. This will also hide the "Add another key" popup menu item.

Defaults to TRUE.

## MUIA_Keyadjust_AllowTripleClick
### NAME
[MUIA_Keyadjust_AllowTripleClick](MUI_Keyadjust/#MUIA_Keyadjust_AllowTripleClick) -- V20 [ISG], `BOOL`, 0x8042fd79

### FUNCTION
Setting this attribute to FALSE will disable triple click handling for the
embedded string object.

### SEE ALSO
[MUIA_Keyadjust_AllowDoubleClick](MUI_Keyadjust/#MUIA_Keyadjust_AllowDoubleClick)

## MUIA_Keyadjust_Key
### NAME
[MUIA_Keyadjust_Key](MUI_Keyadjust/#MUIA_Keyadjust_Key) -- V20 [ISG], `STRPTR`, 0x8042e161

### FUNCTION
Set or get the complete shortcut description string. Multiple shortcuts will
be separated by commas.

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
