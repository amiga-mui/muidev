# Menuitem.mui
## Super class
[Family.mui](MUI_Family.md)
## Background
Menuitem class describes a single menu item. You can use all of the gadtools
menus features except Image menus here.

Since Menuitem class is a subclass of Family class, you can add other menu
items as children of a menu item to indicate sub menus. MUI does not limit
the level of sub menus, but the operating system currently allows a maximum
nesting level of one. Because of this, children of menu items should not
contain other menu items for now, the results are unpredictable.

Note: For handling menu items, [MUIA_UserData](MUI_Notify.md/#MUIA_UserData) and the methods [MUIM_SetUData](MUI_Notify.md/#MUIM_SetUData),
[MUIM_GetUData](MUI_Notify.md/#MUIM_GetUData) and [MUIM_FindUData](MUI_Notify.md/#MUIM_FindUData) can become quite useful. See the Menu demo
program and the accompanying documentation for details.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Menuitem_AISSName](MUI_Menuitem.md/#MUIA_Menuitem_AISSName)|V21|ISG|`STRPTR`
[MUIA_Menuitem_Checked](MUI_Menuitem.md/#MUIA_Menuitem_Checked)|V8|ISG|`BOOL`
[MUIA_Menuitem_Checkit](MUI_Menuitem.md/#MUIA_Menuitem_Checkit)|V8|ISG|`BOOL`
[MUIA_Menuitem_CommandString](MUI_Menuitem.md/#MUIA_Menuitem_CommandString)|V16|ISG|`BOOL`
[MUIA_Menuitem_CopyStrings](MUI_Menuitem.md/#MUIA_Menuitem_CopyStrings)|V16|I..|`BOOL`
[MUIA_Menuitem_Enabled](MUI_Menuitem.md/#MUIA_Menuitem_Enabled)|V8|ISG|`BOOL`
[MUIA_Menuitem_Exclude](MUI_Menuitem.md/#MUIA_Menuitem_Exclude)|V8|ISG|`LONG`
[MUIA_Menuitem_FreeImage](MUI_Menuitem.md/#MUIA_Menuitem_FreeImage)|V20|I..|`BOOL`
[MUIA_Menuitem_Image](MUI_Menuitem.md/#MUIA_Menuitem_Image)|V20|ISG|`struct Image *`
[MUIA_Menuitem_Menuitem](MUI_Menuitem.md/#MUIA_Menuitem_Menuitem)|V20|ISG|`Object *`
[MUIA_Menuitem_Shortcut](MUI_Menuitem.md/#MUIA_Menuitem_Shortcut)|V8|ISG|`STRPTR`
[MUIA_Menuitem_Title](MUI_Menuitem.md/#MUIA_Menuitem_Title)|V8|ISG|`STRPTR`
[MUIA_Menuitem_Toggle](MUI_Menuitem.md/#MUIA_Menuitem_Toggle)|V8|ISG|`BOOL`
[MUIA_Menuitem_Trigger](MUI_Menuitem.md/#MUIA_Menuitem_Trigger)|V8|.SG|`struct MenuItem *`

## MUIA_Menuitem_AISSName
### NAME
[MUIA_Menuitem_AISSName](MUI_Menuitem.md/#MUIA_Menuitem_AISSName) -- V21 [ISG], `STRPTR`, 0x804248f2

### FUNCTION
Define an optional AISS image to be placed in front of the item's text. This
name is simply the file name as it is contained in the TBIMAGES: directory, i.e.
"cut" or "copy".

The image will be displayed only if the following conditions are met:
  - AISS is installed
  - the image can be loaded via datatypes.library
  - the menu is displayed by MUI's Popmenu class
  - the user has enabled the option on the Menu page of MUI prefs

## MUIA_Menuitem_Checked
### NAME
[MUIA_Menuitem_Checked](MUI_Menuitem.md/#MUIA_Menuitem_Checked) -- V8 [ISG], `BOOL`, 0x8042562a

### FUNCTION
Set/get the checked state of a checkit menu item.

### SEE ALSO
[MUIA_Menuitem_Checkit](MUI_Menuitem.md/#MUIA_Menuitem_Checkit), [MUIA_Menuitem_Enabled](MUI_Menuitem.md/#MUIA_Menuitem_Enabled), [MUIA_Menuitem_Exclude](MUI_Menuitem.md/#MUIA_Menuitem_Exclude)

## MUIA_Menuitem_Checkit
### NAME
[MUIA_Menuitem_Checkit](MUI_Menuitem.md/#MUIA_Menuitem_Checkit) -- V8 [ISG], `BOOL`, 0x80425ace

### FUNCTION
Set to TRUE and this item will become a checkmarkable item.

### SEE ALSO
[MUIA_Menuitem_Checked](MUI_Menuitem.md/#MUIA_Menuitem_Checked), [MUIA_Menuitem_Enabled](MUI_Menuitem.md/#MUIA_Menuitem_Enabled), [MUIA_Menuitem_Exclude](MUI_Menuitem.md/#MUIA_Menuitem_Exclude)

## MUIA_Menuitem_CommandString
### NAME
[MUIA_Menuitem_CommandString](MUI_Menuitem.md/#MUIA_Menuitem_CommandString) -- V16 [ISG], `BOOL`, 0x8042b9cc

### FUNCTION
Set to TRUE if [MUIA_Menuitem_Shortcut](MUI_Menuitem.md/#MUIA_Menuitem_Shortcut) points to a command string (e.g.
"shift alt q") instead of a simple letter. Note that MUI won't check if
these keys are pressed (just like intuition), you'll have to do this
yourself.

### SEE ALSO
[MUIA_Menuitem_Shortcut](MUI_Menuitem.md/#MUIA_Menuitem_Shortcut)

## MUIA_Menuitem_CopyStrings
### NAME
[MUIA_Menuitem_CopyStrings](MUI_Menuitem.md/#MUIA_Menuitem_CopyStrings) -- V16 [I..], `BOOL`, 0x8042dc1b

### FUNCTION
Set to TRUE if the title string defined by [MUIA_Menuitem_Title](MUI_Menuitem.md/#MUIA_Menuitem_Title) is to be
copied. Otherwise the title will be used directly and must remain valid
throughout the object's life time.

Defaults to FALSE.

### SEE ALSO
[MUIA_Menuitem_Title](MUI_Menuitem.md/#MUIA_Menuitem_Title)

## MUIA_Menuitem_Enabled
### NAME
[MUIA_Menuitem_Enabled](MUI_Menuitem.md/#MUIA_Menuitem_Enabled) -- V8 [ISG], `BOOL`, 0x8042ae0f

### FUNCTION
Enabled/disable the menu item.

### SEE ALSO
[MUIA_Menuitem_Checkit](MUI_Menuitem.md/#MUIA_Menuitem_Checkit), [MUIA_Menuitem_Checked](MUI_Menuitem.md/#MUIA_Menuitem_Checked), [MUIA_Menuitem_Exclude](MUI_Menuitem.md/#MUIA_Menuitem_Exclude)

## MUIA_Menuitem_Exclude
### NAME
[MUIA_Menuitem_Exclude](MUI_Menuitem.md/#MUIA_Menuitem_Exclude) -- V8 [ISG], `LONG`, 0x80420bc6

### FUNCTION
Bitmask of menu item numbers that are to be deselected when this one is
selected.

### SEE ALSO
[MUIA_Menuitem_Checkit](MUI_Menuitem.md/#MUIA_Menuitem_Checkit), [MUIA_Menuitem_Enabled](MUI_Menuitem.md/#MUIA_Menuitem_Enabled), [MUIA_Menuitem_Checked](MUI_Menuitem.md/#MUIA_Menuitem_Checked)

## MUIA_Menuitem_FreeImage
### NAME
[MUIA_Menuitem_FreeImage](MUI_Menuitem.md/#MUIA_Menuitem_FreeImage) -- V20 [I..], `BOOL`, 0x8042f95f

### FUNCTION
Define whether the image object passed to [MUIA_Menuitem_Image](MUI_Menuitem.md/#MUIA_Menuitem_Image) will be
disposed automatically or not. If this attribute is set to FALSE it is the
responsibility of the application to dispose the image object itself.

Defaults to TRUE.

### SEE ALSO
[MUIA_Menuitem_Image](MUI_Menuitem.md/#MUIA_Menuitem_Image)

## MUIA_Menuitem_Image
### NAME
[MUIA_Menuitem_Image](MUI_Menuitem.md/#MUIA_Menuitem_Image) -- V20 [ISG], `struct Image *`, 0x8042080b

### FUNCTION
Define an optional image to be placed in front of the item's text. This MUST
be a BOOPSI image created by imageclass of intuition.library (or one of its
subclasses). The image will be disposed automatically unless
[MUIA_Menuitem_FreeImage](MUI_Menuitem.md/#MUIA_Menuitem_FreeImage) is set to FALSE. This also applies for images being
replaced by OM_SET.

For normal pull down menus such images are fully supported by AmigaOS4 only
and only if intuition.library V54.6+ is used. However, for MUI's own
internal menu class these images are supported for AmigaOS3 as well and
without any further requirements regarding intuition.library.

### SEE ALSO
[MUIA_Menuitem_FreeImage](MUI_Menuitem.md/#MUIA_Menuitem_FreeImage)

## MUIA_Menuitem_Menuitem
### NAME
[MUIA_Menuitem_Menuitem](MUI_Menuitem.md/#MUIA_Menuitem_Menuitem) -- V20 [ISG], `Object *`, 0x80424b21

### FUNCTION
During OM_NEW and OM_SET this attribute will copy all settings from the
specified Menuitem object to the current object. During OM_GET this
attribute will copy all settings from the current object to the specified
Menuitem object.
All strings and images of the destination object will be freed if required
before the new string and images are copied over from the source object.

## MUIA_Menuitem_Shortcut
### NAME
[MUIA_Menuitem_Shortcut](MUI_Menuitem.md/#MUIA_Menuitem_Shortcut) -- V8 [ISG], `STRPTR`, 0x80422030

### SPECIAL INPUTS
  * MUIV_Menuitem_Shortcut_Check

### FUNCTION
Define the shortcut for a menu item.

The special value MUIV_Menuitem_Short_Check will interpret the menu item's
title in such a way, that the first character will be used as shortcut and
must be followed by a NUL byte and finally the real title string.

### EXAMPLE
```c++
/* create a "Quit" menu item with "Q" as shortcut */
MenuitemObject,
  MUIA_Menuitem_Title, "Q\0Quit",
  MUIA_Menuitem_Shortcut, MUIV_Menuitem_Shortcut_Check,
  End;
```

### SEE ALSO
[MUIA_Menuitem_Title](MUI_Menuitem.md/#MUIA_Menuitem_Title)

## MUIA_Menuitem_Title
### NAME
[MUIA_Menuitem_Title](MUI_Menuitem.md/#MUIA_Menuitem_Title) -- V8 [ISG], `STRPTR`, 0x804218be

### FUNCTION
Define the items title. May be NM_BARLABEL to create a horizontal bar.

### SEE ALSO
[MUIA_Menuitem_Shortcut](MUI_Menuitem.md/#MUIA_Menuitem_Shortcut)

## MUIA_Menuitem_Toggle
### NAME
[MUIA_Menuitem_Toggle](MUI_Menuitem.md/#MUIA_Menuitem_Toggle) -- V8 [ISG], `BOOL`, 0x80424d5c

### FUNCTION
Define the state of the TOGGLE flag for this item.

### SEE ALSO
[MUIA_Menuitem_Checkit](MUI_Menuitem.md/#MUIA_Menuitem_Checkit), [MUIA_Menuitem_Enabled](MUI_Menuitem.md/#MUIA_Menuitem_Enabled), [MUIA_Menuitem_Checked](MUI_Menuitem.md/#MUIA_Menuitem_Checked)

## MUIA_Menuitem_Trigger
### NAME
[MUIA_Menuitem_Trigger](MUI_Menuitem.md/#MUIA_Menuitem_Trigger) -- V8 [.SG], `struct MenuItem *`, 0x80426f32

### FUNCTION
This attribute is set to a pointer to the struct MenuItem of the item object
when the item is selected. By setting up notification on this attribute with
MUIV_EveryTime, you can react on menu actions and query the MenuItems flags
immediately.

Note that menu reactions are also possible and maybe a bit easier with
[MUIA_Application_ReturnID](MUI_Application.md/#MUIA_Application_ReturnID), [MUIA_Application_MenuAction](MUI_Application.md/#MUIA_Application_MenuAction) and
[MUIA_Window_MenuAction](MUI_Window.md/#MUIA_Window_MenuAction).

### NOTES
The passed struct MenuItem pointer for a notification is strictly READ-ONLY
and no other fields than the flags field should be examined.

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
