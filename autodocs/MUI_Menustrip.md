# Menustrip.mui
## Super class
[Family.mui](MUI_Family.md)
## Background
Menustrip class is the base class for MUI's object oriented menus. Its
children are objects of Menu class, each of them describes exactly one menu.

A Menustrip object doesn't feature many options itself, but as a subclass of
Family class, it simply acts as father for multiple Menu objects.

The Menustrip object is usually specified as a child of either Application
class or Window class with the attributes [MUIA_Application_Menustrip](MUI_Application.md/#MUIA_Application_Menustrip) or
[MUIA_Window_Menustrip](MUI_Window.md/#MUIA_Window_Menustrip).
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Menustrip_CaseSensitive](MUI_Menustrip.md/#MUIA_Menustrip_CaseSensitive)|V20|I.G|`BOOL`
[MUIA_Menustrip_Enabled](MUI_Menustrip.md/#MUIA_Menustrip_Enabled)|V8|ISG|`BOOL`

## Methods
Method|Version
------|-------
[MUIM_Menustrip_ExitChange](MUI_Menustrip.md/#MUIM_Menustrip_ExitChange)|V20
[MUIM_Menustrip_InitChange](MUI_Menustrip.md/#MUIM_Menustrip_InitChange)|V20
[MUIM_Menustrip_Popup](MUI_Menustrip.md/#MUIM_Menustrip_Popup)|V20
[MUIM_Menustrip_WillOpen](MUI_Menustrip.md/#MUIM_Menustrip_WillOpen)|V22

## MUIA_Menustrip_CaseSensitive
### NAME
[MUIA_Menustrip_CaseSensitive](MUI_Menustrip.md/#MUIA_Menustrip_CaseSensitive) -- V20 [I.G], `BOOL`, 0x8042d718

### FUNCTION
Set this attribute to TRUE in case the menu strip is using items with the
same upper and lower case shortcuts, i.e. 'a' and 'A'. Otherwise MUI will
not be able to distinguish between the two and will most probably find the
upper case shortcut only and trigger the corresponding action.

Defaults to FALSE.

## MUIA_Menustrip_Enabled
### NAME
[MUIA_Menustrip_Enabled](MUI_Menustrip.md/#MUIA_Menustrip_Enabled) -- V8 [ISG], `BOOL`, 0x8042815b

### FUNCTION
Enable or disable the complete menu strip.

## MUIM_Menustrip_ExitChange
### NAME
[MUIM_Menustrip_ExitChange](MUI_Menustrip.md/#MUIM_Menustrip_ExitChange) -- V20, 0x8042ce4d

### SYNOPSIS
`DoMethod(obj, MUIM_Menustrip_ExitChange);`

### FUNCTION
Terminates [MUIM_Menustrip_InitChange](MUI_Menustrip.md/#MUIM_Menustrip_InitChange) state.

### SEE ALSO
[MUIM_Menustrip_InitChange](MUI_Menustrip.md/#MUIM_Menustrip_InitChange)

## MUIM_Menustrip_InitChange
### NAME
[MUIM_Menustrip_InitChange](MUI_Menustrip.md/#MUIM_Menustrip_InitChange) -- V20, 0x8042dcd9

### SYNOPSIS
`DoMethod(obj, MUIM_Menustrip_InitChange);`

### FUNCTION
Prepares a menustrip for dynamic adding/removing of items. MUI 3 offers the
possibility to dynamically add/remove items from menustrips, even when the
window that contains these items is currently open. To be able to do this,
you must first put the menustrip into a special "exchange" state by using
this method. Then, you can add/remove item at will. When you're done, use
[MUIM_Menustrip_ExitChange](MUI_Menustrip.md/#MUIM_Menustrip_ExitChange) to make MUI relayout the menustrip.

### EXAMPLE
```c++
/* remove two items, add another one */
if(DoMethod(strip, MUIM_Menustrip_InitChange))
{
  DoMethod(strip, OM_REMMEMBER, someitem);
  DoMethod(strip, OM_REMMEMBER, someitem2);

  DoMethod(strip, OM_ADDMEMBER, somenewitem);

  DoMethod(strip, MUIM_Menustrip_ExitChange);
}
```

### SEE ALSO
[MUIM_Menustrip_ExitChange](MUI_Menustrip.md/#MUIM_Menustrip_ExitChange)

## MUIM_Menustrip_Popup
### NAME
[MUIM_Menustrip_Popup](MUI_Menustrip.md/#MUIM_Menustrip_Popup) -- V20, 0x80420e76

### SYNOPSIS
`DoMethod(obj, MUIM_Menustrip_Popup, Object *parent, ULONG flags, LONG x, LONG y);`

### FUNCTION
Open a menustrip for user input even without active user interaction.

### INPUTS
**`Object *parent`**
     the parent object relative to which the menustrip will be opened.

**`ULONG flags`**
     none defined yet, set to 0.

**`LONG x`**
     additional horizontal offset which will be added to
     the parent object's left coordinate.

**`LONG y`**
     additional vertical offset which will be added to
     the parent object's top coordinate.

### RESULT
Returns the [MUIA_UserData](MUI_Notify.md/#MUIA_UserData) attribute of the selected item.

## MUIM_Menustrip_WillOpen
### NAME
[MUIM_Menustrip_WillOpen](MUI_Menustrip.md/#MUIM_Menustrip_WillOpen) -- V22, 0x804230e9

### SYNOPSIS
`DoMethod(obj, MUIM_Menustrip_WillOpen);`

### FUNCTION
Inform the application about a menustrip to opened right after this method.

The key function of the method is to let the application update the menu strip
before it is actually opened.

### SEE ALSO
[MUIM_Menustrip_Popup](MUI_Menustrip.md/#MUIM_Menustrip_Popup)

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
