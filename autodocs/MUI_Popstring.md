# Popstring.mui
## Super class
[Group.mui](MUI_Group.md)
## Inherited by
* [Popasl.mui](MUI_Popasl.md)
* [Popobject.mui](MUI_Popobject.md)
## Background
Popstring class is the base class for creating so called popup objects.
Usually, a popup consists of a string or text gadget, followed by a little
button. Pressing this button brings up a little window with a listview and
lets the user choose an entry with the mouse.

Popstring class features the basic functions for creating such objects.
Given a string object and a button object, it places them horizontally and
sets up some notification. Whenever the popup button is pressed, a hook will
be called which itself should open and prepare the popup window.

The string and the button object are not created by popstring class, they
have to be supplied as attributes during object creation time. This makes
popstring class very flexible, one could e.g. use a text object instead of a
string or a popup button with some text in it.

However, creating simple popups with popstring class would be too much
overhead. Instead of using it directly, you should have a look at one of its
subclasses. They offer a more specialized set of popups and are a lot easier
to use.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Popstring_Button](MUI_Popstring.md/#MUIA_Popstring_Button)|V7|I.G|`Object *`
[MUIA_Popstring_CloseHook](MUI_Popstring.md/#MUIA_Popstring_CloseHook)|V7|ISG|`struct Hook *`
[MUIA_Popstring_OpenHook](MUI_Popstring.md/#MUIA_Popstring_OpenHook)|V7|ISG|`struct Hook *`
[MUIA_Popstring_String](MUI_Popstring.md/#MUIA_Popstring_String)|V7|I.G|`Object *`
[MUIA_Popstring_Toggle](MUI_Popstring.md/#MUIA_Popstring_Toggle)|V7|ISG|`BOOL`

## Methods
Method|Version
------|-------
[MUIM_Popstring_Close](MUI_Popstring.md/#MUIM_Popstring_Close)|V7
[MUIM_Popstring_Open](MUI_Popstring.md/#MUIM_Popstring_Open)|V7

## MUIA_Popstring_Button
### NAME
[MUIA_Popstring_Button](MUI_Popstring.md/#MUIA_Popstring_Button) -- V7 [I.G], `Object *`, 0x8042d0b9

### FUNCTION
Specify the button object to be used in the popup. Depending on the type of
your popup, you should use an image button with MUII_PopUp, MUII_PopFile or
MUII_PopDrawer here. However, its also possible to have a button with some
text or other things in it.

When the popstring object is disposed, the string and the button objects are
disposed as well.

### EXAMPLE
```c++
pop = PopstringObject,
  MUIA_Popstring_String, KeyString(0, 60, 'n'),
  MUIA_Popstring_Button, PopButton(MUII_PopUp),
  MUIA_Popstring_OpenHook, &OpenHook,
  MUIA_Popstring_CloseHook, &CloseHook,
  End;
```

### SEE ALSO
[MUIA_Popstring_String](MUI_Popstring.md/#MUIA_Popstring_String), [MUIA_Popstring_OpenHook](MUI_Popstring.md/#MUIA_Popstring_OpenHook), [MUIA_Popstring_CloseHook](MUI_Popstring.md/#MUIA_Popstring_CloseHook)

## MUIA_Popstring_CloseHook
### NAME
[MUIA_Popstring_CloseHook](MUI_Popstring.md/#MUIA_Popstring_CloseHook) -- V7 [ISG], `struct Hook *`, 0x804256bf

### FUNCTION
Whenever the popup receives a [MUIM_Popstring_Close](MUI_Popstring.md/#MUIM_Popstring_Close) method and the popup is
currently opened, this hook will be called. It will receive a pointer to
itself in register A0, a pointer to the complete popup object in A2 and a
pointer to a struct
```c++
{
  Object *stringobject;
  LONG success;
}
```
in A1. The success parameter is a copy of the methods success parameter and
indicates whether the popup was closed successfully (e.g. with a double
click in a listview) or was just cancelled (e.g. by pressing the popup
button again for toggle popups).

Due to internal message handling issues, calling the close hook is delayed
until the next [MUIM_HandleInput](MUI_Area.md/#MUIM_HandleInput) method is called. This allows you to remove
and dispose windows without danger.

### SEE ALSO
[MUIA_Popstring_OpenHook](MUI_Popstring.md/#MUIA_Popstring_OpenHook), [MUIM_Popstring_Open](MUI_Popstring.md/#MUIM_Popstring_Open), [MUIM_Popstring_Close](MUI_Popstring.md/#MUIM_Popstring_Close)

## MUIA_Popstring_OpenHook
### NAME
[MUIA_Popstring_OpenHook](MUI_Popstring.md/#MUIA_Popstring_OpenHook) -- V7 [ISG], `struct Hook *`, 0x80429d00

### FUNCTION
Whenever the popup receives a [MUIM_Popstring_Open](MUI_Popstring.md/#MUIM_Popstring_Open) method, this hook will be
called. It will receive a pointer to itself in register A0, a pointer to the
complete popup object in A2 and a pointer to a pointer (!) to the string
object contained in the popup object in A1.

When this hook returns TRUE, MUI assumes the popup was opened succesfully
and will disabled the popup button (as long as [MUIA_Popstring_Toggle](MUI_Popstring.md/#MUIA_Popstring_Toggle) is not
set). Return FALSE to indicate that something went wrong and the popup could
not be opened.

### SEE ALSO
[MUIA_Popstring_CloseHook](MUI_Popstring.md/#MUIA_Popstring_CloseHook), [MUIM_Popstring_Open](MUI_Popstring.md/#MUIM_Popstring_Open), [MUIM_Popstring_Close](MUI_Popstring.md/#MUIM_Popstring_Close)

## MUIA_Popstring_String
### NAME
[MUIA_Popstring_String](MUI_Popstring.md/#MUIA_Popstring_String) -- V7 [I.G], `Object *`, 0x804239ea

### FUNCTION
Specify the string object to be used in the popup. This does not necessarily
need to be a real string object, using text objects or even complete groups
of other objects is perfectly ok.

When the popstring object is disposed, the string and the button objects are
disposed as well.

### EXAMPLE
```c++
pop = PopstringObject,
  MUIA_Popstring_String, KeyString(0, 60, 'n'),
  MUIA_Popstring_Button, PopButton(MUII_PopUp),
  MUIA_Popstring_OpenHook, &OpenHook,
  MUIA_Popstring_CloseHook, &CloseHook,
  End;
```

### SEE ALSO
[MUIA_Popstring_Button](MUI_Popstring.md/#MUIA_Popstring_Button), [MUIA_Popstring_OpenHook](MUI_Popstring.md/#MUIA_Popstring_OpenHook), [MUIA_Popstring_CloseHook](MUI_Popstring.md/#MUIA_Popstring_CloseHook)

## MUIA_Popstring_Toggle
### NAME
[MUIA_Popstring_Toggle](MUI_Popstring.md/#MUIA_Popstring_Toggle) -- V7 [ISG], `BOOL`, 0x80422b7a

### FUNCTION
Set/Clear the toggle mode for a popstring object. With toggling disabled,
the popup button will get disabled whenever the user hits it and the popup
opens. With toggling enabled, the popup button always stays enabled and can
be used to cancel (== close with a FALSE return value) the popup.

### SEE ALSO
[MUIA_Popstring_OpenHook](MUI_Popstring.md/#MUIA_Popstring_OpenHook)

## MUIM_Popstring_Close
### NAME
[MUIM_Popstring_Close](MUI_Popstring.md/#MUIM_Popstring_Close) -- V7, 0x8042dc52

### SYNOPSIS
`DoMethod(obj, MUIM_Popstring_Close, LONG result);`

### FUNCTION
This method closes the popup. In fact, it only calls the predefined
[MUIA_Popstring_CloseHook](MUI_Popstring.md/#MUIA_Popstring_CloseHook) with the supplied success parameter.

### EXAMPLE
```c++
DoMethod(poplist, MUIM_Notify, MUIA_Listview_DoubleClick, TRUE,
  popobj, 2,
  MUIM_Popstring_Close, TRUE);
```

## MUIM_Popstring_Open
### NAME
[MUIM_Popstring_Open](MUI_Popstring.md/#MUIM_Popstring_Open) -- V7, 0x804258ba

### SYNOPSIS
`DoMethod(obj, MUIM_Popstring_Open);`

### FUNCTION
This method opens the popup. In fact, it only calls the predefined
[MUIA_Popstring_OpenHook](MUI_Popstring.md/#MUIA_Popstring_OpenHook) and checks its return value. In case of TRUE, the
popup button object is disabled as long as [MUIA_Popstring_Toggle](MUI_Popstring.md/#MUIA_Popstring_Toggle) is unset.

If the toggle mode is enabled, using [MUIA_Popstring_Open](MUI_Popstring.md/#MUIA_Popstring_Open) on a currently
opened popup will result in closing this popup (i.e. calling the close hook)
with a success value of FALSE.

### EXAMPLE
```c++
DoMethod(popbutton, MUIM_Notify, MUIA_Pressed, FALSE,
  popobj, 1,
  MUIM_Popstring_Open);
```

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
