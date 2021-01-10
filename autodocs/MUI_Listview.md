# Listview.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
It's important to know that MUI makes a difference between a list and a
listview. A list is just a collection of some entries and is part of a
listview, which attaches a scrollbar and input handling to the list.

During object creation time, you have to be careful not specifying listview
tags for the list object or list tags for the listview object, both versions
won't work. Once the objects are setup, you can of course talk to the
listview as if it was the list directly.

Since MUI4 Listview class is just a wrapper for List class and List class
can be used directly without a surrounding Listview object. As such List
class of MUI4 understands all attributes and Methods of Listview class.
However, if your application wants to maintain compatibility to MUI3 then of
course the old Listview plus List approach must be used.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Listview_AgainClick](MUI_Listview.md/#MUIA_Listview_AgainClick)|V20|I.G|`BOOL`
[MUIA_Listview_ClickColumn](MUI_Listview.md/#MUIA_Listview_ClickColumn)|V7|..G|`LONG`
[MUIA_Listview_DefClickColumn](MUI_Listview.md/#MUIA_Listview_DefClickColumn)|V7|ISG|`LONG`
[MUIA_Listview_DoubleClick](MUI_Listview.md/#MUIA_Listview_DoubleClick)|V4|I.G|`BOOL`
[MUIA_Listview_DragType](MUI_Listview.md/#MUIA_Listview_DragType)|V11|ISG|`LONG`
[MUIA_Listview_Input](MUI_Listview.md/#MUIA_Listview_Input)|V4|I..|`BOOL`
[MUIA_Listview_List](MUI_Listview.md/#MUIA_Listview_List)|V4|I.G|`Object *`
[MUIA_Listview_MultiSelect](MUI_Listview.md/#MUIA_Listview_MultiSelect)|V7|I..|`LONG`
[MUIA_Listview_ScrollerPos](MUI_Listview.md/#MUIA_Listview_ScrollerPos)|V10|I..|`BOOL`
[MUIA_Listview_SelectChange](MUI_Listview.md/#MUIA_Listview_SelectChange)|V4|..G|`BOOL`

## MUIA_Listview_AgainClick
### NAME
[MUIA_Listview_AgainClick](MUI_Listview.md/#MUIA_Listview_AgainClick) -- V20 [I.G], `BOOL`, 0x804214c2

### FUNCTION
This attribute is set to TRUE whenever the user clicks on the same entry
again, but not necessarily within the system's double click time.

### SEE ALSO
[MUIA_Listview_DoubleClick](MUI_Listview.md/#MUIA_Listview_DoubleClick)

## MUIA_Listview_ClickColumn
### NAME
[MUIA_Listview_ClickColumn](MUI_Listview.md/#MUIA_Listview_ClickColumn) -- V7 [..G], `LONG`, 0x8042d1b3

### FUNCTION
When using a multi column list, this attribute contains the number of the
column where the user clicked.

### SEE ALSO
[MUIA_Listview_DefClickColumn](MUI_Listview.md/#MUIA_Listview_DefClickColumn)

## MUIA_Listview_DefClickColumn
### NAME
[MUIA_Listview_DefClickColumn](MUI_Listview.md/#MUIA_Listview_DefClickColumn) -- V7 [ISG], `LONG`, 0x8042b296

### FUNCTION
When the listview is controlled with the keyboard and the user presses
RETURN, the value given here will be used as default for
[MUIA_Listview_ClickColumn](MUI_Listview.md/#MUIA_Listview_ClickColumn).

### SEE ALSO
[MUIA_Listview_ClickColumn](MUI_Listview.md/#MUIA_Listview_ClickColumn)

## MUIA_Listview_DoubleClick
### NAME
[MUIA_Listview_DoubleClick](MUI_Listview.md/#MUIA_Listview_DoubleClick) -- V4 [I.G], `BOOL`, 0x80424635

### FUNCTION
This attribute is set to TRUE whenever the user double clicks on an entry in
the list.

### SEE ALSO
[MUIA_Listview_SelectChange](MUI_Listview.md/#MUIA_Listview_SelectChange)

## MUIA_Listview_DragType
### NAME
[MUIA_Listview_DragType](MUI_Listview.md/#MUIA_Listview_DragType) -- V11 [ISG], `LONG`, 0x80425cd3

### SPECIAL INPUTS
  * MUIV_Listview_DragType_None
  * MUIV_Listview_DragType_Immediate

### FUNCTION
If you want the user to be able to drag items out of your list, you must set
this for the listview class. Currently, only one drag type is defined.

## MUIA_Listview_Input
### NAME
[MUIA_Listview_Input](MUI_Listview.md/#MUIA_Listview_Input) -- V4 [I..], `BOOL`, 0x8042682d

### FUNCTION
Setting this to FALSE will result in a read only listview.

Defaults to TRUE.

### SEE ALSO
[MUIA_Listview_MultiSelect](MUI_Listview.md/#MUIA_Listview_MultiSelect)

## MUIA_Listview_List
### NAME
[MUIA_Listview_List](MUI_Listview.md/#MUIA_Listview_List) -- V4 [I.G], `Object *`, 0x8042bcce

### FUNCTION
Every listview needs a list object as child. Specify it here.

As every other child, it will get disposes when its parent object is
disposed.

### EXAMPLE
```c++
ListviewObject,
  MUIA_Listview_Input, FALSE,
  MUIA_Listview_List, ListObject,
    ReadListFrame,
    MUIA_List_Format, ",,",
    End,
  nd;
```

### SEE ALSO
[MUIA_Listview_Input](MUI_Listview.md/#MUIA_Listview_Input)

## MUIA_Listview_MultiSelect
### NAME
[MUIA_Listview_MultiSelect](MUI_Listview.md/#MUIA_Listview_MultiSelect) -- V7 [I..], `LONG`, 0x80427e08

### SPECIAL INPUTS
  * MUIV_Listview_MultiSelect_None
  * MUIV_Listview_MultiSelect_Default
  * MUIV_Listview_MultiSelect_Shifted
  * MUIV_Listview_MultiSelect_Always

### FUNCTION
Four possibilities exist for a listviews multi select capabilities:

**`MUIV_Listview_MultiSelect_None`**
     The listview cannot multiselect at all.

**`MUIV_Listview_MultiSelect_Default`**
     The multi select type (with or without shift) depends on the user's
     preferences setting.

**`MUIV_Listview_MultiSelect_Shifted`**
     Overrides the users prefs, multi selecting only together with shift key.

**`MUIV_Listview_MultiSelect_Always`**
     Overrides the users prefs, multi selecting without shift key.

Please do **NOT** override the users prefs unless you have a good reason!

### SEE ALSO
[MUIA_List_MultiTestHook](MUI_List.md/#MUIA_List_MultiTestHook)

## MUIA_Listview_ScrollerPos
### NAME
[MUIA_Listview_ScrollerPos](MUI_Listview.md/#MUIA_Listview_ScrollerPos) -- V10 [I..], `BOOL`, 0x8042b1b4

### SPECIAL INPUTS
  * MUIV_Listview_ScrollerPos_Default
  * MUIV_Listview_ScrollerPos_Left
  * MUIV_Listview_ScrollerPos_Right
  * MUIV_Listview_ScrollerPos_None

### FUNCTION
Specifies the position of a listviews scrollbar. Don't use this tag unless
it's absolutely required!

If you specify MUIV_Listview_ScrollerPos_None, your listview won't get a
scroller at all and look much like a list object alone. However, listviews
without scroller are still more powerful than list objects as they feature
e.g. drag&drop possibilities.

Creating listviews without a scrollbar makes sense if you want to have the
scrollbar somewhere else, e.g. outside of a horizontal virtual group where
the listview resides. This technique allows the creation of horizontally
scrollable listviews.

When you create the scrollbar on your own, connect it to the list object
(not listview object!) like this:

```c++
DoMethod(sbar, MUIM_Notify, MUIA_Prop_First, MUIV_EveryTime,
  list, 3, MUIM_Set,
  MUIA_List_TopPixel, MUIV_TriggerValue);

DoMethod(list, MUIM_Notify, MUIA_List_TotalPixel, MUIV_EveryTime,
  sbar, 3, MUIM_Set,
  MUIA_Prop_Entries, MUIV_TriggerValue);

DoMethod(list, MUIM_Notify, MUIA_List_VisiblePixel, MUIV_EveryTime,
  sbar, 3, MUIM_Set,
  MUIA_Prop_Visible, MUIV_TriggerValue);

DoMethod(list, MUIM_Notify, MUIA_List_TopPixel, MUIV_EveryTime,
  sbar, 3, MUIM_Set,
  MUIA_Prop_First, MUIV_TriggerValue);
```

## MUIA_Listview_SelectChange
### NAME
[MUIA_Listview_SelectChange](MUI_Listview.md/#MUIA_Listview_SelectChange) -- V4 [..G], `BOOL`, 0x8042178f

### FUNCTION
This attribute is set to TRUE whenever the selection state of one or more
items in the list is changing. You can use this e.g. if you want to display
the number of selected items in a status line.

### SEE ALSO
[MUIA_Listview_MultiSelect](MUI_Listview.md/#MUIA_Listview_MultiSelect)

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
