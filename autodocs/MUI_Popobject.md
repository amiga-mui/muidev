# Popobject.mui
## Super class
[Popstring.mui](MUI_Popstring.md)
## Inherited by
* [Poplist.mui](MUI_Poplist.md)
* [Popscreen.mui](MUI_Popscreen.md)
## Background
Popobject class takes a MUI object as parameter uses this one as popup. You
can e.g. simply create a listview object with some entries and the popobject
class will create a window around it and display it when the user hits the
popup button.

Using this class instead of creating the popup windows yourself prevents you
from having lots of problems. Think twice before deciding to make you own
popups!
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Popobject_Follow](MUI_Popobject.md/#MUIA_Popobject_Follow)|V7|ISG|`BOOL`
[MUIA_Popobject_Light](MUI_Popobject.md/#MUIA_Popobject_Light)|V7|ISG|`BOOL`
[MUIA_Popobject_Object](MUI_Popobject.md/#MUIA_Popobject_Object)|V7|I.G|`Object *`
[MUIA_Popobject_ObjStrHook](MUI_Popobject.md/#MUIA_Popobject_ObjStrHook)|V7|ISG|`struct Hook *`
[MUIA_Popobject_StrObjHook](MUI_Popobject.md/#MUIA_Popobject_StrObjHook)|V7|ISG|`struct Hook *`
[MUIA_Popobject_Volatile](MUI_Popobject.md/#MUIA_Popobject_Volatile)|V7|ISG|`BOOL`
[MUIA_Popobject_WindowHook](MUI_Popobject.md/#MUIA_Popobject_WindowHook)|V9|ISG|`struct Hook *`

## MUIA_Popobject_Follow
### NAME
[MUIA_Popobject_Follow](MUI_Popobject.md/#MUIA_Popobject_Follow) -- V7 [ISG], `BOOL`, 0x80424cb5

### FUNCTION
Setting this attribute causes the popup window to follow its parent window
when its moved.

Defaults to TRUE.

### SEE ALSO
[MUIA_Popobject_Light](MUI_Popobject.md/#MUIA_Popobject_Light), [MUIA_Popobject_Volatile](MUI_Popobject.md/#MUIA_Popobject_Volatile).

## MUIA_Popobject_Light
### NAME
[MUIA_Popobject_Light](MUI_Popobject.md/#MUIA_Popobject_Light) -- V7 [ISG], `BOOL`, 0x8042a5a3

### FUNCTION
This attribute causes the popup window to be border and titleless.

Defaults to TRUE

### SEE ALSO
[MUIA_Popobject_Follow](MUI_Popobject.md/#MUIA_Popobject_Follow), [MUIA_Popobject_Volatile](MUI_Popobject.md/#MUIA_Popobject_Volatile)

## MUIA_Popobject_Object
### NAME
[MUIA_Popobject_Object](MUI_Popobject.md/#MUIA_Popobject_Object) -- V7 [I.G], `Object *`, 0x804293e3

### FUNCTION
Specify the object to pop up. Usually this is a relatively simple thing like
a single listview, but you can of course use group class here and make
rather complex popups. As with all other MUI classes, the object here gets
disposed when the popobject is disposed.

### EXAMPLE
```c++
pop = PopobjectObject,
  MUIA_Popstring_String, KeyString(0, 60, 'n'),
  MUIA_Popstring_Button, PopButton(MUII_PopUp),
  MUIA_Popobject_StrObjHook, &StrObjHook,
  MUIA_Popobject_ObjStrHook, &ObjStrHook,
  MUIA_Popobject_Object, ListviewObject,
    MUIA_Listview_List, ListObject,
      InputListFrame,
      MUIA_List_SourceArray, PopNames,
      End,
    End,
  End;
```

### SEE ALSO
[MUIA_Popobject_StrObjHook](MUI_Popobject.md/#MUIA_Popobject_StrObjHook), [MUIA_Popobject_ObjStrHook](MUI_Popobject.md/#MUIA_Popobject_ObjStrHook),
[MUIA_Popobject_Light](MUI_Popobject.md/#MUIA_Popobject_Light)

## MUIA_Popobject_ObjStrHook
### NAME
[MUIA_Popobject_ObjStrHook](MUI_Popobject.md/#MUIA_Popobject_ObjStrHook) -- V7 [ISG], `struct Hook *`, 0x8042db44

### FUNCTION
When a popup is closed, this hook is called. You can examine the state of
your [MUIA_Popobject_Object](MUI_Popobject.md/#MUIA_Popobject_Object) and set the contents of the string gadget
respectively. The hook receives a pointer to itself in A0, a pointer to your
[MUIA_Popobject_Object](MUI_Popobject.md/#MUIA_Popobject_Object) in A2 and a pointer to the embedded string object in
A1.

The hook will only be called when your popup is closed with a success value
of TRUE. Otherwise, MUI closes the popup without taking further actions,
just as if had never opened.

Since MUI doesn't know anything about your [MUIA_Popobject_Object](MUI_Popobject.md/#MUIA_Popobject_Object), it's your
task to tell when your popup is finished. You can terminate popups at
any time by sending a [MUIM_Popstring_Close](MUI_Popstring.md/#MUIM_Popstring_Close) method:

### EXAMPLE
```c++
/* A double click terminates the popping list with a successful
   return value. */

DoMethod(plist, MUIM_Notify, MUIA_Listview_DoubleClick, TRUE,
  pop, 2,
  MUIM_Popstring_Close, TRUE);

SAVEDS ASM VOID ObjStrFunc(REG(a2) Object *list,REG(a1) Object *str)
{
  char *x;

  DoMethod(list, MUIM_List_GetEntry, MUIV_List_GetEntry_Active, &x);
  set(str, MUIA_String_Contents, x);
}
```

## MUIA_Popobject_StrObjHook
### NAME
[MUIA_Popobject_StrObjHook](MUI_Popobject.md/#MUIA_Popobject_StrObjHook) -- V7 [ISG], `struct Hook *`, 0x8042fbe1

### FUNCTION
Before the popup opens, this hook is called. You can use it to prepare your
[MUIA_Popobject_Object](MUI_Popobject.md/#MUIA_Popobject_Object) according to the contents of the string gadget. The
hook receives a pointer to itself in A0, a pointer to your
[MUIA_Popobject_Object](MUI_Popobject.md/#MUIA_Popobject_Object) in A2 and a pointer to the embedded string object in
A1.

Return TRUE if you want the popup to appear, FALSE otherwise.

### EXAMPLE
```c++
SAVEDS ASM LONG StrObjFunc(REG(a2) Object *list, REG(a1) Object *str)
{
  char *x,*s;
  int i;

  get(str, MUIA_String_Contents ,&s);

  for(i=0;;i++)
  {
    DoMethod(list, MUIM_List_GetEntry, i, &x);
    if(x == NULL)
    {
      set(list, MUIA_List_Active, MUIV_List_Active_Off);
      break;
    }
    else if(stricmp(x, s) == 0)
    {
      set(list, MUIA_List_Active, i);
      break;
    }
  }

  returnTRUE;
}
```

### SEE ALSO
[MUIA_Popobject_ObjStrHook](MUI_Popobject.md/#MUIA_Popobject_ObjStrHook), [MUIA_Popobject_Object](MUI_Popobject.md/#MUIA_Popobject_Object), [MUIA_Popobject_WindowHook](MUI_Popobject.md/#MUIA_Popobject_WindowHook)

## MUIA_Popobject_Volatile
### NAME
[MUIA_Popobject_Volatile](MUI_Popobject.md/#MUIA_Popobject_Volatile) -- V7 [ISG], `BOOL`, 0x804252ec

### FUNCTION
Setting this attribute causes the popup window to disappear when the
corresponding popobject disappears, e.g. because its in a page group and the
user toggled the page. When the popobject appears again, the popup window
appears also.

Defaults to TRUE.

### SEE ALSO
[MUIA_Popobject_Light](MUI_Popobject.md/#MUIA_Popobject_Light), [MUIA_Popobject_Follow](MUI_Popobject.md/#MUIA_Popobject_Follow)

## MUIA_Popobject_WindowHook
### NAME
[MUIA_Popobject_WindowHook](MUI_Popobject.md/#MUIA_Popobject_WindowHook) -- V9 [ISG], `struct Hook *`, 0x8042f194

### FUNCTION
If specified, this hook is called immediately after the popup's window
object has been created but before this window is opened. You might e.g.
want to add a cycle chain for the popup window here.

The hook is called with a pointer to the pop object ([MUIA_Popobject_Object](MUI_Popobject.md/#MUIA_Popobject_Object))
in A2 and with a pointer to the window object that MUI generated to handle
the popup in A1.

### EXAMPLE
```c++
/* pop is a simple listview, just set the windows
** default object to this to enable keyboard control */

SAVEDS ASM VOID WindowFunc(REG(a2) Object *pop,REG(a1) Object *win)
{
  set(win, MUIA_Window_DefaultObject, pop);
}
```

### SEE ALSO
[MUIA_Popobject_ObjStrHook](MUI_Popobject.md/#MUIA_Popobject_ObjStrHook), [MUIA_Popobject_Object](MUI_Popobject.md/#MUIA_Popobject_Object)

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
