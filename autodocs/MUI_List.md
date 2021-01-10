# List.mui
## Super class
[Area.mui](MUI_Area.md)
## Inherited by
* [Dirlist.mui](MUI_Dirlist.md)
* [Floattext.mui](MUI_Floattext.md)
* [Scrmodelist.mui](MUI_Scrmodelist.md)
* [Volumelist.mui](MUI_Volumelist.md)
## Background
MUI's list class is very powerful. It handles all types of entries, from a
simple string to a complicated structure with many associated resources.
Multi column lists are also supported, the format for a column is
adjustable.

Lists support any kind of sorting, multi selection and an active entry that
can be controlled with the mouse or the cursor keys.

Note: A list object alone doesn't make much sense, you should always use it
as child of a listview object. This one attaches a scrollbar and handles
all user input.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_List_Active](MUI_List.md/#MUIA_List_Active)|V4|ISG|`LONG`
[MUIA_List_AdjustHeight](MUI_List.md/#MUIA_List_AdjustHeight)|V4|I..|`BOOL`
[MUIA_List_AdjustWidth](MUI_List.md/#MUIA_List_AdjustWidth)|V4|I..|`BOOL`
[MUIA_List_AgainClick](MUI_List.md/#MUIA_List_AgainClick)|V20|I.G|`BOOL`
[MUIA_List_AutoLineHeight](MUI_List.md/#MUIA_List_AutoLineHeight)|V20|I..|`BOOL`
[MUIA_List_AutoVisible](MUI_List.md/#MUIA_List_AutoVisible)|V11|ISG|`BOOL`
[MUIA_List_ClickColumn](MUI_List.md/#MUIA_List_ClickColumn)|V7|..G|`LONG`
[MUIA_List_ColumnOrder](MUI_List.md/#MUIA_List_ColumnOrder)|V20|.SG|`BYTE *`
[MUIA_List_CompareHook](MUI_List.md/#MUIA_List_CompareHook)|V4|IS.|`struct Hook *`
[MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook)|V4|IS.|`struct Hook *`
[MUIA_List_DefClickColumn](MUI_List.md/#MUIA_List_DefClickColumn)|V7|ISG|`LONG`
[MUIA_List_DestructHook](MUI_List.md/#MUIA_List_DestructHook)|V4|IS.|`struct Hook *`
[MUIA_List_DisplayHook](MUI_List.md/#MUIA_List_DisplayHook)|V4|IS.|`struct Hook *`
[MUIA_List_DoubleClick](MUI_List.md/#MUIA_List_DoubleClick)|V4|I.G|`BOOL`
[MUIA_List_DragSortable](MUI_List.md/#MUIA_List_DragSortable)|V11|ISG|`BOOL`
[MUIA_List_DragType](MUI_List.md/#MUIA_List_DragType)|V11|ISG|`LONG`
[MUIA_List_DropMark](MUI_List.md/#MUIA_List_DropMark)|V11|..G|`LONG`
[MUIA_List_Editable](MUI_List.md/#MUIA_List_Editable)|V21|ISG|`BOOL`
[MUIA_List_Entries](MUI_List.md/#MUIA_List_Entries)|V4|..G|`LONG`
[MUIA_List_First](MUI_List.md/#MUIA_List_First)|V4|.SG|`LONG`
[MUIA_List_Format](MUI_List.md/#MUIA_List_Format)|V4|ISG|`CONST_STRPTR`
[MUIA_List_HideColumn](MUI_List.md/#MUIA_List_HideColumn)|V21|IS.|`LONG`
[MUIA_List_HScrollerVisibility](MUI_List.md/#MUIA_List_HScrollerVisibility)|V20|I..|`LONG`
[MUIA_List_Input](MUI_List.md/#MUIA_List_Input)|V4|I..|`BOOL`
[MUIA_List_InsertPosition](MUI_List.md/#MUIA_List_InsertPosition)|V9|..G|`LONG`
[MUIA_List_LineHeight](MUI_List.md/#MUIA_List_LineHeight)|V20|.SG|`ULONG`
[MUIA_List_MaxColumns](MUI_List.md/#MUIA_List_MaxColumns)|V21|I..|`LONG`
[MUIA_List_MinLineHeight](MUI_List.md/#MUIA_List_MinLineHeight)|V4|IS.|`LONG`
[MUIA_List_MultiSelect](MUI_List.md/#MUIA_List_MultiSelect)|V7|I..|`LONG`
[MUIA_List_MultiTestHook](MUI_List.md/#MUIA_List_MultiTestHook)|V4|IS.|`struct Hook *`
[MUIA_List_Pool](MUI_List.md/#MUIA_List_Pool)|V13|I.G|`APTR`
[MUIA_List_PoolPuddleSize](MUI_List.md/#MUIA_List_PoolPuddleSize)|V13|I..|`ULONG`
[MUIA_List_PoolThreshSize](MUI_List.md/#MUIA_List_PoolThreshSize)|V13|I..|`ULONG`
[MUIA_List_Quiet](MUI_List.md/#MUIA_List_Quiet)|V4|.SG|`BOOL`
[MUIA_List_ScrollerPos](MUI_List.md/#MUIA_List_ScrollerPos)|V10|I..|`LONG`
[MUIA_List_SelectChange](MUI_List.md/#MUIA_List_SelectChange)|V4|..G|`BOOL`
[MUIA_List_ShowColumn](MUI_List.md/#MUIA_List_ShowColumn)|V21|IS.|`LONG`
[MUIA_List_ShowDropMarks](MUI_List.md/#MUIA_List_ShowDropMarks)|V11|ISG|`BOOL`
[MUIA_List_SortColumn](MUI_List.md/#MUIA_List_SortColumn)|V21|ISG|`LONG`
[MUIA_List_SourceArray](MUI_List.md/#MUIA_List_SourceArray)|V4|I..|`APTR`
[MUIA_List_Stripes](MUI_List.md/#MUIA_List_Stripes)|V21|ISG|`BOOL`
[MUIA_List_Title](MUI_List.md/#MUIA_List_Title)|V6|ISG|`CONST_STRPTR`
[MUIA_List_TitleArray](MUI_List.md/#MUIA_List_TitleArray)|V21|ISG|`CONST_STRPTR *`
[MUIA_List_TitleClick](MUI_List.md/#MUIA_List_TitleClick)|V20|..G|`LONG`
[MUIA_List_TopPixel](MUI_List.md/#MUIA_List_TopPixel)|V4|..G|`LONG`
[MUIA_List_TotalPixel](MUI_List.md/#MUIA_List_TotalPixel)|V4|..G|`LONG`
[MUIA_List_Visible](MUI_List.md/#MUIA_List_Visible)|V4|..G|`LONG`
[MUIA_List_VisiblePixel](MUI_List.md/#MUIA_List_VisiblePixel)|V4|..G|`LONG`

## Methods
Method|Version
------|-------
[MUIM_List_Clear](MUI_List.md/#MUIM_List_Clear)|V4
[MUIM_List_Compare](MUI_List.md/#MUIM_List_Compare)|V20
[MUIM_List_Construct](MUI_List.md/#MUIM_List_Construct)|V20
[MUIM_List_CreateEditObject](MUI_List.md/#MUIM_List_CreateEditObject)|V21
[MUIM_List_CreateImage](MUI_List.md/#MUIM_List_CreateImage)|V11
[MUIM_List_DeleteImage](MUI_List.md/#MUIM_List_DeleteImage)|V11
[MUIM_List_Destruct](MUI_List.md/#MUIM_List_Destruct)|V20
[MUIM_List_Display](MUI_List.md/#MUIM_List_Display)|V20
[MUIM_List_Edit](MUI_List.md/#MUIM_List_Edit)|V21
[MUIM_List_EditDone](MUI_List.md/#MUIM_List_EditDone)|V21
[MUIM_List_EndEdit](MUI_List.md/#MUIM_List_EndEdit)|V22
[MUIM_List_Exchange](MUI_List.md/#MUIM_List_Exchange)|V4
[MUIM_List_GetEntry](MUI_List.md/#MUIM_List_GetEntry)|V4
[MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert)|V4
[MUIM_List_InsertSingle](MUI_List.md/#MUIM_List_InsertSingle)|V7
[MUIM_List_Jump](MUI_List.md/#MUIM_List_Jump)|V4
[MUIM_List_Move](MUI_List.md/#MUIM_List_Move)|V9
[MUIM_List_NextSelected](MUI_List.md/#MUIM_List_NextSelected)|V6
[MUIM_List_QueryColumnWidth](MUI_List.md/#MUIM_List_QueryColumnWidth)|V11
[MUIM_List_Redraw](MUI_List.md/#MUIM_List_Redraw)|V4
[MUIM_List_Remove](MUI_List.md/#MUIM_List_Remove)|V4
[MUIM_List_Select](MUI_List.md/#MUIM_List_Select)|V4
[MUIM_List_Sort](MUI_List.md/#MUIM_List_Sort)|V4
[MUIM_List_SortEntries](MUI_List.md/#MUIM_List_SortEntries)|V22
[MUIM_List_TestPos](MUI_List.md/#MUIM_List_TestPos)|V11

## MUIA_List_Active
### NAME
[MUIA_List_Active](MUI_List.md/#MUIA_List_Active) -- V4 [ISG], `LONG`, 0x8042391c

### SPECIAL INPUTS
  * MUIV_List_Active_Off
  * MUIV_List_Active_Top
  * MUIV_List_Active_Bottom
  * MUIV_List_Active_Up
  * MUIV_List_Active_Down
  * MUIV_List_Active_PageUp
  * MUIV_List_Active_PageDown

### FUNCTION
Reading this attribute will return the number of the active entry (the one with
the cursor on it). The result is between 0 and [MUIA_List_Entries](MUI_List.md/#MUIA_List_Entries)-1 or
MUIV_List_Active_Off, in which case there is currently no active entry.

Setting the attribute will cause the list to move the cursor to the new
position and scroll this position into the visible area.

### SEE ALSO
[MUIA_List_Entries](MUI_List.md/#MUIA_List_Entries), [MUIA_List_First](MUI_List.md/#MUIA_List_First), [MUIA_List_Visible](MUI_List.md/#MUIA_List_Visible)

## MUIA_List_AdjustHeight
### NAME
[MUIA_List_AdjustHeight](MUI_List.md/#MUIA_List_AdjustHeight) -- V4 [I..], `BOOL`, 0x8042850d

### FUNCTION
A list with [MUIA_List_AdjustHeight](MUI_List.md/#MUIA_List_AdjustHeight) set to TRUE is exactly as high as all of its
entries and not resizable. This is only possible when the list is filled
**before** the window is opened.

### SEE ALSO
[MUIA_List_AdjustWidth](MUI_List.md/#MUIA_List_AdjustWidth)

## MUIA_List_AdjustWidth
### NAME
[MUIA_List_AdjustWidth](MUI_List.md/#MUIA_List_AdjustWidth) -- V4 [I..], `BOOL`, 0x8042354a

### FUNCTION
A list with [MUIA_List_AdjustWidth](MUI_List.md/#MUIA_List_AdjustWidth) set to TRUE is exactly as wide as the widest
entry and not resizable. This is only possible when the list is filled
**before** the window is opened.

### SEE ALSO
[MUIA_List_AdjustHeight](MUI_List.md/#MUIA_List_AdjustHeight)

## MUIA_List_AgainClick
### NAME
[MUIA_List_AgainClick](MUI_List.md/#MUIA_List_AgainClick) -- V20 [I.G], `BOOL`, 0x804214c2

### FUNCTION
This attribute is set to TRUE whenever the user clicks on the same entry again,
but not necessarily within the system's double click time.

### SEE ALSO
[MUIA_List_DoubleClick](MUI_List.md/#MUIA_List_DoubleClick)

## MUIA_List_AutoLineHeight
### NAME
[MUIA_List_AutoLineHeight](MUI_List.md/#MUIA_List_AutoLineHeight) -- V20 [I..], `BOOL`, 0x8042bc08

### FUNCTION
Enables automatic line height calculation. Useful e.g. if you cannot predict a
sensible line height.

### SEE ALSO
[MUIA_List_LineHeight](MUI_List.md/#MUIA_List_LineHeight), [MUIA_List_MinLineHeight](MUI_List.md/#MUIA_List_MinLineHeight)

## MUIA_List_AutoVisible
### NAME
[MUIA_List_AutoVisible](MUI_List.md/#MUIA_List_AutoVisible) -- V11 [ISG], `BOOL`, 0x8042a445

### FUNCTION
Set this to make your lists automatically jump to the active entry when they are
displayed.

### SEE ALSO
[MUIA_List_Active](MUI_List.md/#MUIA_List_Active)

## MUIA_List_ClickColumn
### NAME
[MUIA_List_ClickColumn](MUI_List.md/#MUIA_List_ClickColumn) -- V7 [..G], `LONG`, 0x8042d1b3

### FUNCTION
When using a multi column list, this attribute contains the number of the
column where the user clicked.

### SEE ALSO
[MUIA_List_DefClickColumn](MUI_List.md/#MUIA_List_DefClickColumn)

## MUIA_List_ColumnOrder
### NAME
[MUIA_List_ColumnOrder](MUI_List.md/#MUIA_List_ColumnOrder) -- V20 [.SG], `BYTE *`, 0x9d5100f6

### FUNCTION
Use this attribute to either get or set the current column order. Useful if you
want to restore a specific column layout upon restarting an application. Make
sure to provide a large enough array when get()ing the order to hold the
numbering of all columns. Also make sure to set a full and unique column
numbering when set()ing the order.

### NOTES
Column numbering starts at zero.

### EXAMPLE
```c++
/* Take a 4 column list for example */
/* reverse the order of all columns */
const BYTE order[4] = { 3, 2, 1, 0 };
set(obj, MUIA_List_ColumnOrder, order);
```

## MUIA_List_CompareHook
### NAME
[MUIA_List_CompareHook](MUI_List.md/#MUIA_List_CompareHook) -- V4 [IS.], `struct Hook *`, 0x80425c14

### SPECIAL INPUTS
  * MUIV_List_CompareHook_String
  * MUIV_List_CompareHook_StringArray

### FUNCTION
If you plan to have the entries of your list sorted (either by inserting them
sorted or by using the [MUIM_List_Sort](MUI_List.md/#MUIM_List_Sort) method) and if the entries of your list
are not simple strings, you **MUST** supply a compare hook.

This hook will be called with one list element in A1 and another one in A2. You
should return something like

|| <0 || if e1 < e2 ||
|| 0 || if e1 == e2 ||
|| >0 || if e1 > e2 ||

These built-in compare hooks are available:
**`MUIV_List_CompareHook_String or NULL`**
     compare the strings of a single column list.

**`MUIV_List_CompareHook_StringArray`**
     compare the strings of a multi column list in respect to the column  specified
     by [MUIA_List_SortColumn](MUI_List.md/#MUIA_List_SortColumn).

### EXAMPLE
```c++
/* the builtin string compare function */
LONG SAVEDS ASM cmpfunc(REG(a1, char *s1), REG(a2, char *s2))
{
  return stricmp(s1, s2);
}
```

### SEE ALSO
[MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook), [MUIA_List_DestructHook](MUI_List.md/#MUIA_List_DestructHook)

## MUIA_List_ConstructHook
### NAME
[MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook) -- V4 [IS.], `struct Hook *`, 0x8042894f

### SPECIAL INPUTS
  * MUIV_List_ConstructHook_String
  * MUIV_List_ConstructHook_StringArray

### FUNCTION
The construct hook is called whenever you add an entry to your list. MUI will
not insert the given pointer directly, but instead call the construct hook and
add its result code.

Imagine you want to display a list of entries in a directory. You could step
through it using Examine()/ExNext() and directly use the [MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert) method
on your file info block buffer.

Your construct hook will be called with this file info block as parameter, makes
a copy of it and returns the address of that copy. That's what is actually added
to the list.

The corresponding destruct hook is called whenever an entry shall be removed.
Its task would simply be to free the memory and maybe other resources concerning
this entry that were allocated by the construct hook.

Using these two functions, you will never have to worry about freeing the memory
used by your list entries. Clearing the list or disposing the list object will
automatically remove all entries and thus free the associated resources.

The construct hook will be called with the hook in A0, the data given to
[MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert) as message in register A1 and with pointer to a standard OS3.x
memory pool in A2. If you want, you can use the exec or amiga.lib functions for
allocating memory within this pool, but this is only an option.

If the construct hook returns NULL, nothing will be added to the list.

These built-in construct hooks are available:
**`MUIV_List_ConstructHook_String`**
     this expects that you only add strings to your list and will make a local copy
     of this string to allow you destroying the original. Of course you **MUST**
     also use MUIV_List_DestructHook_String in this case.

**`MUIV_List_ConstructHook_StringArray`**
     specify an array of strings. Both the array and the strings will be copied
     internally to allow you destroying the originals. This is very useful for multi
     column lists. Of course you **MUST** also use
     MUIV_List_DestructHook_StringArray in this case. Additionally you **MUST**
     use [MUIA_List_MaxColumns](MUI_List.md/#MUIA_List_MaxColumns) to specify the number of columns to be used.

Without construct and destruct hooks you are responsible for either allocating
and freeing entries yourself or for overloading [MUIM_List_Construct](MUI_List.md/#MUIM_List_Construct) and
[MUIM_List_Destruct](MUI_List.md/#MUIM_List_Destruct).

### EXAMPLE
```c++
/* the builtin string construct and destruct functions. */
/* used when MUIV_List_ConstructHook_String is given */
APTR SAVEDS ASM consfunc(REG(a2, APTR pool), REG(a1, char *str))
{
  char *new;

  if((new = AllocPooled(pool, strlen(str)+1)) != NULL)
    strcpy(new, str);

  return new;
}

void SAVEDS ASM desfunc(REG(a2, APTR pool), REG(a1, char *entry))
{
  FreePooled(pool, entry, strlen(entry)+1);
}

/* for more sophisticated hooks see demo program WbMan.c */
```

### SEE ALSO
[MUIA_List_DestructHook](MUI_List.md/#MUIA_List_DestructHook), [MUIA_List_DisplayHook](MUI_List.md/#MUIA_List_DisplayHook), [MUIA_List_MaxColumns](MUI_List.md/#MUIA_List_MaxColumns)

## MUIA_List_DefClickColumn
### NAME
[MUIA_List_DefClickColumn](MUI_List.md/#MUIA_List_DefClickColumn) -- V7 [ISG], `LONG`, 0x8042b296

### FUNCTION
When the listview is controlled with the keyboard and the user presses RETURN,
the value given here will be used as default for [MUIA_List_ClickColumn](MUI_List.md/#MUIA_List_ClickColumn).

### SEE ALSO
[MUIA_List_ClickColumn](MUI_List.md/#MUIA_List_ClickColumn)

## MUIA_List_DestructHook
### NAME
[MUIA_List_DestructHook](MUI_List.md/#MUIA_List_DestructHook) -- V4 [IS.], `struct Hook *`, 0x804297ce

### SPECIAL INPUTS
  * MUIV_List_DestructHook_String
  * MUIV_List_DestructHook_StringArray

### FUNCTION
Set up a destruct hook for your list. For detailed explanation see
[MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook).

### SEE ALSO
[MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook), [MUIA_List_DisplayHook](MUI_List.md/#MUIA_List_DisplayHook)

## MUIA_List_DisplayHook
### NAME
[MUIA_List_DisplayHook](MUI_List.md/#MUIA_List_DisplayHook) -- V4 [IS.], `struct Hook *`, 0x8042b4d5

### SPECIAL INPUTS
  * MUIV_List_DisplayHook_String
  * MUIV_List_DisplayHook_StringArray

### FUNCTION
Since MUI's lists can handle any kind of entries, you have to supply a display
hook to specify what should actually be shown in the display.

The hook will be called with a pointer to the entry to be displayed in A1 and a
pointer to a string array containing as many entries as your list may have
columns in A2.

You must fill this array with the strings that you want to display. The strings
filled into this array MUST stay valid even when the function returns. This
means that you MUST NOT store a pointer to a local variable there, unless it is
declared "static" as in the example below. Non-static variables will cease to
exist as soon as the function is left and will be overwritten with arbitrary
garbage which in turn will cause that garbage to be displayed instead of the
intended text.

Note: You can of course use MUI's text engine facilities here to create e.g.
right aligned or centered columns.

Without a display hook, MUI expects a simple one columned string list.

See [MUIA_List_Format](MUI_List.md/#MUIA_List_Format) for details about column handling.

Note: Since version 6 of MUI, the display hook also gets the position of the
current entry as additional parameter. You can easily do e.g. some line
numbering using this feature. The number (from 0 to NumEntries-1) is stored in
the longword **preceding** the column array (see example below).

These built-in display hooks are available:
**`MUIV_List_DisplayHook_String or NULL`**
     display the strings of a single column list.

**`MUIV_List_DisplayHook_StringArray`**
     display the strings of a multi column list.

### EXAMPLE
```c++
/* list of file info blocks, three columned, row number, name and size */
LONG SAVEDS ASM dispfunc(REG(a2) char **array, REG(a1, struct FileInfoBlock *fib))
{
  // These buffers must be "static" to survive the return from this
  // function!
  static char buf1[20];
  static char buf2[20];

  if(fib->fib_EntryType < 0)
    snprintf(buf2, sizeof(buf2), "\33r%ld", fib->fib_Size);
  else
    strlcpy(buf2, "\33r(dir)", sizeof(buf2));

  snprintf(buf1, sizeof(buf1), "%ld", array[-1]);   // get the line number.

  *array++ = buf1;
  *array++ = fib->fib_FileName;
  *array   = buf2;

  return 0;
}
```

### SEE ALSO
[MUIA_List_Format](MUI_List.md/#MUIA_List_Format), [MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents)

## MUIA_List_DoubleClick
### NAME
[MUIA_List_DoubleClick](MUI_List.md/#MUIA_List_DoubleClick) -- V4 [I.G], `BOOL`, 0x80424635

### FUNCTION
This attribute is set to TRUE whenever the user double clicks on an entry in the
list.

### SEE ALSO
[MUIA_List_SelectChange](MUI_List.md/#MUIA_List_SelectChange)

## MUIA_List_DragSortable
### NAME
[MUIA_List_DragSortable](MUI_List.md/#MUIA_List_DragSortable) -- V11 [ISG], `BOOL`, 0x80426099

### FUNCTION
If you set this attribute to TRUE, the user will be able to move around entries
in the list by using drag&drop.

## MUIA_List_DragType
### NAME
[MUIA_List_DragType](MUI_List.md/#MUIA_List_DragType) -- V11 [ISG], `LONG`, 0x80425cd3

### SPECIAL INPUTS
  * MUIV_List_DragType_None
  * MUIV_List_DragType_Immediate

### FUNCTION
If you want the user to be able to drag items out of your list, you must set
this for the listview class. Currently, only one drag type is defined.

## MUIA_List_DropMark
### NAME
[MUIA_List_DropMark](MUI_List.md/#MUIA_List_DropMark) -- V11 [..G], `LONG`, 0x8042aba6

### FUNCTION
After a successfull drop operation, this attribute holds the position where we
should insert the new entry(ies).

### EXAMPLE
See DragnDrop example program

## MUIA_List_Editable
### NAME
[MUIA_List_Editable](MUI_List.md/#MUIA_List_Editable) -- V21 [ISG], `BOOL`, 0x8042f9b9

### FUNCTION
Specify whether the list object allows entries to be edited.

Defaults to FALSE.

### SEE ALSO
[MUIM_List_Edit](MUI_List.md/#MUIM_List_Edit)

## MUIA_List_Entries
### NAME
[MUIA_List_Entries](MUI_List.md/#MUIA_List_Entries) -- V4 [..G], `LONG`, 0x80421654

### FUNCTION
Get the current number of entries in the list.

### SEE ALSO
[MUIA_List_First](MUI_List.md/#MUIA_List_First), [MUIA_List_Visible](MUI_List.md/#MUIA_List_Visible), [MUIA_List_Active](MUI_List.md/#MUIA_List_Active)

## MUIA_List_First
### NAME
[MUIA_List_First](MUI_List.md/#MUIA_List_First) -- V4 [.SG], `LONG`, 0x804238d4

### FUNCTION
Get the number of the entry displayed on top of the list. You have to be
prepared to get a result of -1, which means that the list is not visible at all
(e.g. when the window is iconifed).

### SEE ALSO
[MUIA_List_Visible](MUI_List.md/#MUIA_List_Visible), [MUIA_List_Entries](MUI_List.md/#MUIA_List_Entries), [MUIA_List_Active](MUI_List.md/#MUIA_List_Active)

## MUIA_List_Format
### NAME
[MUIA_List_Format](MUI_List.md/#MUIA_List_Format) -- V4 [ISG], `CONST_STRPTR`, 0x80423c0a

### FUNCTION
MUI has the ability to handle multi column lists. To define how many columns
should be displayed and how they should be formatted, you specify a format
string.

This format string must contain one entry for each column you want to see.
Entries are separated by commas, each single entry is parsed via
dos.library/ReadArgs().

The template for a single entry looks like this:

```c++
COL=C/K/N,DELTA=D/K/N,PREPARSE=P/K,WEIGHT=W/K/N,MINWIDTH=MIW/K,
MAXWIDTH=MAW/K,BAR/S,ISOBJECT/S,H=HIDDEN/S,SORTABLE/S,ORDER/K,ELIDE=E/K
```

**`COL`**
     Set number of the current column. This allows you to adjust the order of your
     columns without having to change your display hook. See example for details.
     Defaults to current entry number (0,1,...).

**`DELTA`**
     Space in pixel between this column and the next. The last displayed column
     ignores this setting. Defaults to 4.

**`PREPARSE`**
     A preparse value for this column. Setting this e.g. to "\33c" would make the
     column centered. See [MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents) for other control codes.

**`WEIGHT`**
     The weight of the column. As with MUI's group class, columns are layouted with
     a minimum size, a maximum size and weight. A column with a weight of 200 would
     gain twice the space than a column with a weight of 100.
     Defaults to 100.

**`MINWIDTH`**
     Minimum percentage width for the current column. If your list is 200 pixels
     wide and you set this to 25, your column will at least be 50 pixels. The
     special value -1 for this parameter means that the minimum width is as wide as
     the widest entry in this column. This ensures that every entry will be
     completely visible (as long as the list is wide enough). Defaults to -1.
     Appending "px" to the width (i.e. MINWIDTH=100px) will make it an absolute
     minimum width in pixels. (V21)

**`MAXWIDTH`**
     Maximum percentage width for the current column. If your list is 200 pixels
     wide and you set this to 25, your column will not be wider than 50 pixels.
     The special value -1 for this parameter means that the maximum width is as wide
     as the widest entry in this column. Defaults to -1.
     Appending "px" to the width (i.e. MAXWIDTH=100px) will make it an absolute
     maximum width in pixels. (V21)

**`BAR`**
     Since muimaster.library V11, you can enable a vertical bar between this and the
     next column by using this switch.

**`ISOBJECT`**
     The column's contents are no text but a real MUI object.

**`HIDDEN`**
     Hide this column. It can be made visible via the context menu.

**`SORTABLE`**
     This column can be sorted alphabetically by clicking its title button. This
     will also set the attribute [MUIA_List_SortColumn](MUI_List.md/#MUIA_List_SortColumn) accordingly. (V21)

**`ORDER`**
     Define the column sorting order. Valid orders are ASC or ASCENDING and DESC or
     DESCENDING. Defaults to ascending order. (V21)

**`ELIDE`**
     Shorten the text by replacing as many characters as necessary by an ellipsis
     ("...") at the given position (left, center, right). Any other position value
     will be treated like a simple cutoff at the right side.

If your list object gets so small that there is not enough place for the
minwidth of a column, this column will be hidden completely and the remaining
space is distributed between the remaining columns. This is not true if the
column is the first column, in this case the entries will simply be clipped.

Note: You will have as many columns in your list as entries in the format string
(i.e. number of commas + 1). Empty entries, e.g. with a format string of ",,,,"
are perfectly ok.

The default list format is an empty string (""), this means a one column list
without special formatting.

### NOTES
By the default a list can handle 64 columns, unless a different number was set
by [MUIA_List_MaxColumns](MUI_List.md/#MUIA_List_MaxColumns).

With MUI4 the argument FIXWIDTH to set a fixed width was introduced. Although
this argument is still supported it is recommended to use equal MINWIDTH and
MAXWIDTH values with "px" appended instead. Therefore it is considered obsolete.

### EXAMPLE
```c++
/* Three column list without further formatting: */
MUIA_List_Format: ",,"

/* Three column list, middle column centered: */
MUIA_List_Format: ",P=\33c,"

/* Three column list, display order 2 1 0: */
MUIA_List_Format: "COL=2,COL=1,COL=0"

/* now something more complex.           */
/* the display hook defines six entries: */
dispfunc(_a2 char **array, _a1 struct Article *at)
{
   *array++ = at->FromName; // col 0
   *array++ = at->FromPath; // col 1
   *array++ = at->ToName;   // col 2
   *array++ = at->ToPath;   // col 3
   *array++ = at->Date;     // col 4
   *array   = at->Subject;  // col 5
}

/* but we only want to have fromname, date and subject
/* actually displayed, subject shoud be centered: */
MUIA_List_Format, "COL=0,COL=4,COL=5 P=\33c"

/* maybe this looks kind of silly, why not make our  */
/* display hook only fill in these three columns.    */
/* well, if you would e.g. make the format string    */
/* user configurable and document what your display  */
/* hook puts into the array, the user could decide   */
/* what columns he actually wants to see.            */
/* The supplied example DFView does something like   */
/* that.                                             */

/* two column list:   ! Eye    1234 !
                      ! Foot     22 !
                      ! Nose  22331 ! */

MUIA_List_Format, "MAW=100,P=\33r"

/* Four column list with no, left, center and right */
/* text eliding: */
MUIA_List_Format: "E=none,E=left,E=center,E=right"
```

### SEE ALSO
[MUIA_List_DisplayHook](MUI_List.md/#MUIA_List_DisplayHook), [MUIA_List_MaxColumns](MUI_List.md/#MUIA_List_MaxColumns), [MUIA_List_SortColumn](MUI_List.md/#MUIA_List_SortColumn),
[MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents)

## MUIA_List_HideColumn
### NAME
[MUIA_List_HideColumn](MUI_List.md/#MUIA_List_HideColumn) -- V21 [IS.], `LONG`, 0x80428052

### FUNCTION
Hide a shown column. This attribute can be used multiple times in a single
SetAttrs() call to make more than one column invisible.

### SEE ALSO
[MUIA_List_ShowColumn](MUI_List.md/#MUIA_List_ShowColumn), [MUIA_List_Format](MUI_List.md/#MUIA_List_Format)

## MUIA_List_HScrollerVisibility
### NAME
[MUIA_List_HScrollerVisibility](MUI_List.md/#MUIA_List_HScrollerVisibility) -- V20 [I..], `LONG`, 0x804280a6

### SPECIAL INPUTS
  * MUIV_List_HScrollerVisibility_Always
  * MUIV_List_HScrollerVisibility_Never
  * MUIV_List_HScrollerVisibility_Auto

### FUNCTION
Three possibilities exist for the list's horizontal scroll bar:

**`MUIV_List_HScrollerVisibility_Auto`**
     Automatically show/hide the scroll bar whenever necessary.

**`MUIV_List_HScrollerVisibility_Always`**
     Never hide the scroll bar, even if it is not required.

**`MUIV_List_HScrollerVisibility_Never`**
     Never show the scroll bar, even if it would be required.

Please do **NOT** override the user's prefs unless you have a good reason!

## MUIA_List_Input
### NAME
[MUIA_List_Input](MUI_List.md/#MUIA_List_Input) -- V4 [I..], `BOOL`, 0x8042682d

### FUNCTION
Setting this to FALSE will result in a read only list view.

Defaults to TRUE.

### SEE ALSO
[MUIA_List_MultiSelect](MUI_List.md/#MUIA_List_MultiSelect)

## MUIA_List_InsertPosition
### NAME
[MUIA_List_InsertPosition](MUI_List.md/#MUIA_List_InsertPosition) -- V9 [..G], `LONG`, 0x8042d0cd

### FUNCTION
After insertion of an element with [MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert), you can query the position
of the new entry by getting this attribute.

## MUIA_List_LineHeight
### NAME
[MUIA_List_LineHeight](MUI_List.md/#MUIA_List_LineHeight) -- V20 [.SG], `ULONG`, 0x80425880

### FUNCTION
Sets the absolute line height for lists in pixels. Useful e.g. if you need to
enforce a specific height.

### SEE ALSO
[MUIA_List_AutoLineHeight](MUI_List.md/#MUIA_List_AutoLineHeight), [MUIA_List_MinLineHeight](MUI_List.md/#MUIA_List_MinLineHeight)

## MUIA_List_MaxColumns
### NAME
[MUIA_List_MaxColumns](MUI_List.md/#MUIA_List_MaxColumns) -- V21 [I..], `LONG`, 0x8042a98b

### FUNCTION
Specify the number of columns the list can handle at most.

Defaults to 64.

### NOTES
This attribute MUST be used to specify the number of available columns if
MUIV_List_ConstructHook_StringArray is used as construct hook. Otherwise MUI
will assume the wrong number of columns.

### SEE ALSO
[MUIA_List_Format](MUI_List.md/#MUIA_List_Format)

## MUIA_List_MinLineHeight
### NAME
[MUIA_List_MinLineHeight](MUI_List.md/#MUIA_List_MinLineHeight) -- V4 [IS.], `LONG`, 0x8042d1c3

### FUNCTION
Sets the minimum line height for lists in pixels. Useful e.g. if you have custom
images.

### SEE ALSO
[MUIA_List_AutoLineHeight](MUI_List.md/#MUIA_List_AutoLineHeight), [MUIA_List_LineHeight](MUI_List.md/#MUIA_List_LineHeight)

## MUIA_List_MultiSelect
### NAME
[MUIA_List_MultiSelect](MUI_List.md/#MUIA_List_MultiSelect) -- V7 [I..], `LONG`, 0x80427e08

### SPECIAL INPUTS
  * MUIV_List_MultiSelect_None
  * MUIV_List_MultiSelect_Default
  * MUIV_List_MultiSelect_Shifted
  * MUIV_List_MultiSelect_Always

### FUNCTION
Four possibilities exist for a listviews multi select capabilities:

**`MUIV_List_MultiSelect_None`**
     The listview cannot multiselect at all.

**`MUIV_List_MultiSelect_Default`**
     The multi select type (with or without shift) depends on the user's
     preferences setting.

**`MUIV_List_MultiSelect_Shifted`**
     Overrides the users prefs, multi selecting only together with shift key.

**`MUIV_List_MultiSelect_Always`**
     Overrides the users prefs, multi selecting without shift key.

Please do **NOT** override the user's prefs unless you have a good reason!

### SEE ALSO
[MUIA_List_MultiTestHook](MUI_List.md/#MUIA_List_MultiTestHook)

## MUIA_List_MultiTestHook
### NAME
[MUIA_List_MultiTestHook](MUI_List.md/#MUIA_List_MultiTestHook) -- V4 [IS.], `struct Hook *`, 0x8042c2c6

### FUNCTION
If you plan to have a multi selecting list but not all of your entries are
actually multi selectable (e.g. in a file requester), you can supply a
[MUIA_List_MultiTestHook](MUI_List.md/#MUIA_List_MultiTestHook).

It will be called with a pointer to an entry in A1 and should return TRUE if the
entry is multi selectable, FALSE otherwise.

### EXAMPLE
```c++
/* multi test func for a list of file info blocks */
LONG SAVEDS ASM mtfunc(REG(a1, struct FileInfoBlock *fib))
{
  if(fib->fib_DirEntryType < 0)
    return TRUE;
  else
    return FALSE;
}
```

### SEE ALSO
[MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook), [MUIA_List_DestructHook](MUI_List.md/#MUIA_List_DestructHook)

## MUIA_List_Pool
### NAME
[MUIA_List_Pool](MUI_List.md/#MUIA_List_Pool) -- V13 [I.G], `APTR`, 0x80423431

### FUNCTION
Pass something from CreatePool() here if you don't want the list to create its
own memory pool but use this one instead. Note that list class does **NOT**
use semaphore protection when accessing the pool, you must **NOT** use pools
which are accessed from other tasks than the application's main task.

### SEE ALSO
[MUIA_List_PoolPuddleSize](MUI_List.md/#MUIA_List_PoolPuddleSize), [MUIA_List_PoolThreshSize](MUI_List.md/#MUIA_List_PoolThreshSize)

## MUIA_List_PoolPuddleSize
### NAME
[MUIA_List_PoolPuddleSize](MUI_List.md/#MUIA_List_PoolPuddleSize) -- V13 [I..], `ULONG`, 0x8042a4eb

### FUNCTION
Specify the puddle size for the lists memory pool. This value is ignored if you
specify your own pool with [MUIA_List_Pool](MUI_List.md/#MUIA_List_Pool).

Defaults to 2048.

### SEE ALSO
[MUIA_List_PoolThreshSize](MUI_List.md/#MUIA_List_PoolThreshSize), [MUIA_List_Pool](MUI_List.md/#MUIA_List_Pool)

## MUIA_List_PoolThreshSize
### NAME
[MUIA_List_PoolThreshSize](MUI_List.md/#MUIA_List_PoolThreshSize) -- V13 [I..], `ULONG`, 0x8042c48c

### FUNCTION
Specify the thresh size for the lists memory pool. This value is ignored if you
specify your own pool with [MUIA_List_Pool](MUI_List.md/#MUIA_List_Pool).

Defaults to 1024.

### SEE ALSO
[MUIA_List_PoolPuddleSize](MUI_List.md/#MUIA_List_PoolPuddleSize), [MUIA_List_Pool](MUI_List.md/#MUIA_List_Pool)

## MUIA_List_Quiet
### NAME
[MUIA_List_Quiet](MUI_List.md/#MUIA_List_Quiet) -- V4 [.SG], `BOOL`, 0x8042d8c7

### FUNCTION
If you add/remove lots of entries to/from a currently visible list, this will
cause lots of screen action and slow down the operation. Setting [MUIA_List_Quiet](MUI_List.md/#MUIA_List_Quiet)
to TRUE will temporarily prevent the list from being refreshed, this refresh
will take place only once when you set it back to FALSE again.

### EXAMPLE
```c++
set(list, MUIA_List_Quiet, TRUE);
AddThousandEntries(list);
set(list, MUIA_List_Quiet, FALSE);
```

### SEE ALSO
[MUIM_List_Clear](MUI_List.md/#MUIM_List_Clear), [MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert), [MUIM_List_Remove](MUI_List.md/#MUIM_List_Remove)

## MUIA_List_ScrollerPos
### NAME
[MUIA_List_ScrollerPos](MUI_List.md/#MUIA_List_ScrollerPos) -- V10 [I..], `LONG`, 0x8042b1b4

### SPECIAL INPUTS
  * MUIV_List_ScrollerPos_Default
  * MUIV_List_ScrollerPos_Left
  * MUIV_List_ScrollerPos_Right
  * MUIV_List_ScrollerPos_None

### FUNCTION
Specifies the position of a listviews scrollbar. Don't use this tag unless it is
absolutely required!

If you specify MUIV_List_ScrollerPos_None, your listview won't get a scroller at
all and look much like a list object alone. However, listviews without scroller
are still more powerful than list objects as they feature e.g. drag&drop
possibilities.

Creating listviews without a scrollbar makes sense if you want to have the
scrollbar somewhere else, e.g. outside of a horizontal virtual group where the
listview resides. This technique allows the creation of horizontally scrollable
listviews.

When you create the scrollbar on your own, connect it to the list object (not
listview object!) like this:

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

## MUIA_List_SelectChange
### NAME
[MUIA_List_SelectChange](MUI_List.md/#MUIA_List_SelectChange) -- V4 [..G], `BOOL`, 0x8042178f

### FUNCTION
This attribute is set to TRUE whenever the selection state of one or more items
in the list is changing. You can use this e.g. if you want to display the number
of selected items in a status line.

### SEE ALSO
[MUIA_List_MultiSelect](MUI_List.md/#MUIA_List_MultiSelect)

## MUIA_List_ShowColumn
### NAME
[MUIA_List_ShowColumn](MUI_List.md/#MUIA_List_ShowColumn) -- V21 [IS.], `LONG`, 0x8042c840

### FUNCTION
Show a hidden column. This attribute can be used multiple times in a single
SetAttrs() call make more than one column visible.

### SEE ALSO
[MUIA_List_HideColumn](MUI_List.md/#MUIA_List_HideColumn), [MUIA_List_Format](MUI_List.md/#MUIA_List_Format)

## MUIA_List_ShowDropMarks
### NAME
[MUIA_List_ShowDropMarks](MUI_List.md/#MUIA_List_ShowDropMarks) -- V11 [ISG], `BOOL`, 0x8042c6f3

### FUNCTION
If a list supports Drag & Drop, it usually indicates the place where a new line
would be inserted with some horizontal lines.

Showing this place doesn't make much sense if you don't care about the drop
position anyway, e.g. because your list is always alphabetically sorted. You
should set this attribute to FALSE in these cases.

### SEE ALSO
[MUIA_List_DropMark](MUI_List.md/#MUIA_List_DropMark)

## MUIA_List_SortColumn
### NAME
[MUIA_List_SortColumn](MUI_List.md/#MUIA_List_SortColumn) -- V21 [ISG], `LONG`, 0x8042cafb

### FUNCTION
When using a multi column list, this attribute contains the number of the
current sorting column.

### SEE ALSO
[MUIA_List_ClickColumn](MUI_List.md/#MUIA_List_ClickColumn)

## MUIA_List_SourceArray
### NAME
[MUIA_List_SourceArray](MUI_List.md/#MUIA_List_SourceArray) -- V4 [I..], `APTR`, 0x8042c0a0

### FUNCTION
The NULL terminated array given here is immediately inserted into the list after
object creation time.

### EXAMPLE
```c++
static const char *KeyList[] =
{
  "Cursor Up",
  "Cursor Down",
  "Cursor Left",
  "Cursor Right",
  NULL;
};

LV_Keys = ListviewObject,
  MUIA_Listview_List, ListObject,
    InputListFrame,
    MUIA_List_AdjustWidth, TRUE,
    MUIA_List_SourceArray, KeyList,
    End,
  End;
```

## MUIA_List_Stripes
### NAME
[MUIA_List_Stripes](MUI_List.md/#MUIA_List_Stripes) -- V21 [ISG], `BOOL`, 0x8042a308

### FUNCTION
Set this attribute to TRUE to enable the user configurable row striping effect.

## MUIA_List_Title
### NAME
[MUIA_List_Title](MUI_List.md/#MUIA_List_Title) -- V6 [ISG], `CONST_STRPTR`, 0x80423e66

### FUNCTION
Specify a title for the list. The title is displayed at the very first line and
doesn't scroll away when the list's top position moves.

Usually, the title is just a string. However, if you have a multi column list
with a custom display hook and you want to have seperate titles for each of your
columns, you can set this attribute to TRUE. In this case, whenever MUI feels
that the list title has to be drawn, it will call your display hook with a NULL
entry pointer. Your hook has to check for this NULL entry and fill the given
string array with your column titles. Layout of the column titles follows the
same rules as layout of the lists entries.

### EXAMPLE
```c++
/* display function for a multi columned file list with titles */
LONG SAVEDS ASM DisplayFunc(REG(a2, char **array), REG(a1, struct Entry *e))
{
  struct Data *data = hook->h_Data;

  if(e != NULL)
  {
    *array++ = e->Name;
    *array++ = e->Size;
    *array++ = e->Date;
    *array++ = e->Time;
    *array++ = e->Flags;
    *array   = e->Comment;
  }
  else
  {
    *array++ = "Name";
    *array++ = "Size";
    *array++ = "Date";
    *array++ = "Time";
    *array++ = "Flags";
    *array   = "Comment";
  }

  return 0;
}
```

### SEE ALSO
[MUIA_List_DisplayHook](MUI_List.md/#MUIA_List_DisplayHook)

## MUIA_List_TitleArray
### NAME
[MUIA_List_TitleArray](MUI_List.md/#MUIA_List_TitleArray) -- V21 [ISG], `CONST_STRPTR *`, 0x80427d95

### FUNCTION
Specify an array of title strings for the list. The titles are displayed at the
very first line and doesn't scroll away when the list's top position moves.

This attribute is preferred over [MUIA_List_Title](MUI_List.md/#MUIA_List_Title). Neither the list's display
hook nor the [MUIM_List_Display](MUI_List.md/#MUIM_List_Display) method will be called to obtain the column title
strings in case a valid array is specified.

### NOTES
The array pointer is copied internally, but the string pointers are not and must
remain valid as long as the list object lives.

### EXAMPLE
```c++
/* set the list titles with an array of strings */
CONST_STRPTR titles[] =
{
  "first name",
  "last name"
};

Object *list = ListObject,
  MUIA_List_TitleArray, titles,
  MUIA_List_MaxColumns, 2,
End;
```

### SEE ALSO
[MUIA_List_DisplayHook](MUI_List.md/#MUIA_List_DisplayHook), [MUIA_List_Title](MUI_List.md/#MUIA_List_Title), [MUIM_List_Display](MUI_List.md/#MUIM_List_Display)

## MUIA_List_TitleClick
### NAME
[MUIA_List_TitleClick](MUI_List.md/#MUIA_List_TitleClick) -- V20 [..G], `LONG`, 0x80422fd9

### FUNCTION
This attribute is set to the column index number whenever the user clicks on a
column title button.

## MUIA_List_TopPixel
### NAME
[MUIA_List_TopPixel](MUI_List.md/#MUIA_List_TopPixel) -- V4 [..G], `LONG`, 0x80429df3

### FUNCTION
Specifies the top position of a list's scrollbar in terms of pixels. Setting
this attribute will scroll the list to the given positions.

When you create the scrollbar on your own, connect it to the list object like
this:

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

### SEE ALSO
[MUIA_List_TotalPixel](MUI_List.md/#MUIA_List_TotalPixel), [MUIA_List_VisiblePixel](MUI_List.md/#MUIA_List_VisiblePixel)

## MUIA_List_TotalPixel
### NAME
[MUIA_List_TotalPixel](MUI_List.md/#MUIA_List_TotalPixel) -- V4 [..G], `LONG`, 0x8042a8f5

### FUNCTION
Returns the number of pixels that all list items do require to be displayed
completely. Use this value in combination with [MUIA_List_VisiblePixel](MUI_List.md/#MUIA_List_VisiblePixel) and
[MUIA_List_TopPixel](MUI_List.md/#MUIA_List_TopPixel) if you need to connect a custom scrollbar with the list.

### SEE ALSO
[MUIA_List_TopPixel](MUI_List.md/#MUIA_List_TopPixel), [MUIA_List_VisiblePixel](MUI_List.md/#MUIA_List_VisiblePixel)

## MUIA_List_Visible
### NAME
[MUIA_List_Visible](MUI_List.md/#MUIA_List_Visible) -- V4 [..G], `LONG`, 0x8042191f

### FUNCTION
Get the current number of visible entries in the list. You have to be prepared
to get a result of -1, which means that the list is not visible at all (e.g.
when the window is iconifed).

### SEE ALSO
[MUIA_List_First](MUI_List.md/#MUIA_List_First), [MUIA_List_Entries](MUI_List.md/#MUIA_List_Entries), [MUIA_List_Active](MUI_List.md/#MUIA_List_Active)

## MUIA_List_VisiblePixel
### NAME
[MUIA_List_VisiblePixel](MUI_List.md/#MUIA_List_VisiblePixel) -- V4 [..G], `LONG`, 0x804273e9

### FUNCTION
Returns the list size as number of currently visible vertical pixels. Use this
value in combination with [MUIA_List_TopPixel](MUI_List.md/#MUIA_List_TopPixel) and [MUIA_List_TotalPixel](MUI_List.md/#MUIA_List_TotalPixel) if you
need to connect a custom scrollbar with the list.

### SEE ALSO
[MUIA_List_TopPixel](MUI_List.md/#MUIA_List_TopPixel), [MUIA_List_TotalPixel](MUI_List.md/#MUIA_List_TotalPixel)

## MUIM_List_Clear
### NAME
[MUIM_List_Clear](MUI_List.md/#MUIM_List_Clear) -- V4, 0x8042ad89

### SYNOPSIS
`DoMethod(obj, MUIM_List_Clear);`

### FUNCTION
Clear the list, all entries are removed. If a destruct hook is set it will be
called for every entry.

Setting [MUIA_List_Quiet](MUI_List.md/#MUIA_List_Quiet) to TRUE before clearing the list will defer the visual
update of the list until [MUIA_List_Quiet](MUI_List.md/#MUIA_List_Quiet) is set back to FALSE again.

### SEE ALSO
[MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert), [MUIA_List_DestructHook](MUI_List.md/#MUIA_List_DestructHook), [MUIA_List_Quiet](MUI_List.md/#MUIA_List_Quiet)

## MUIM_List_Compare
### NAME
[MUIM_List_Compare](MUI_List.md/#MUIM_List_Compare) -- V20, 0x80421b68

### SYNOPSIS
`DoMethod(obj, MUIM_List_Compare, APTR entry1, APTR entry2, LONG column);`

### FUNCTION
Compare two list items. This method is meant to replace [MUIA_List_CompareHook](MUI_List.md/#MUIA_List_CompareHook)
for subclasses of List class.

### INPUTS
**`APTR entry1`**
     first entry to be compared.

**`APTR entry2`**
     second entry to be compared.

**`LONG column`**
     column for comparison (V21).

### RESULT
|| <0 || if e1 < e2 ||
|| 0 || if e1 == e2 ||
|| >0 || if e1 > e2 ||

### EXAMPLE
```c++
LONG myListCompare(struct IClass *cl, Object *obj,
    struct MUIP_List_Compare *msg)
{
  LONG rc = 0;

  switch(msg->column)
  {
    struct myEntry *e1 = msg->entry1;
    struct myEntry *e2 = msg->entry2;

    case 0:
      rc = strcmp(e1->firstName, e2->firstName);
    break;

    case 1:
      rc = strcmp(e1->lastName, e2->lastName);
    break;

    case 2:
      rc = compareBirthdays(e1->birthday, e2->birthday);
    break;
  }

  return rc;
}
```

### SEE ALSO
[MUIA_List_CompareHook](MUI_List.md/#MUIA_List_CompareHook)

## MUIM_List_Construct
### NAME
[MUIM_List_Construct](MUI_List.md/#MUIM_List_Construct) -- V20, 0x8042d662

### SYNOPSIS
`DoMethod(obj, MUIM_List_Construct, APTR entry, APTR pool);`

### FUNCTION
Construct a new list item. This method is meant to replace
[MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook) for subclasses of List class.

### INPUTS
**`APTR entry`**
     source entry to construct new entry from.

**`APTR pool`**
     memory pool pointer.

### RESULT
Return a pointer to the newly created list item, or NULL upon failure.

### SEE ALSO
[MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook), [MUIA_List_DestructHook](MUI_List.md/#MUIA_List_DestructHook), [MUIM_List_Destruct](MUI_List.md/#MUIM_List_Destruct)

## MUIM_List_CreateEditObject
### NAME
[MUIM_List_CreateEditObject](MUI_List.md/#MUIM_List_CreateEditObject) -- V21, 0x804219ae

### SYNOPSIS
`DoMethod(obj, MUIM_List_CreateEditObject, LONG row, LONG column, APTR entry);`

### FUNCTION
Create an object for inline editing. This method must be overloaded by a
subclass of List class. The supplied row and column values are the same as the
ones passed to [MUIM_List_Edit](MUI_List.md/#MUIM_List_Edit) while "entry" points to the to be edited list
entry.

NEVER dispose the created object on your own. This will be done by List class
automatically whenever the object is no longer required. You also don't need to
take care of adding/removing the edit object to the GUI. All this is done by
List class internally already.

### INPUTS
**`LONG row`**
     row of the entry to be edited.

**`LONG column`**
     column of the entry to be edited.

**`APTR entry`**
     a pointer to the entry to be edited.

### RESULT
A pointer to the created edit object or NULL to cancel editing.

### EXAMPLE
```c++
ULONG myListCreateEditObject(struct IClass *cl, Object *obj,
    struct MUIP_List_CreateEditObject *msg)
{
  Object *editobj;

  /* create the edit object here which suits your needs */
  editobj = StringObject, ..., End;

  return (ULONG)editobj;
}
```

### SEE ALSO
[MUIA_List_Editable](MUI_List.md/#MUIA_List_Editable), [MUIM_List_Edit](MUI_List.md/#MUIM_List_Edit), [MUIM_List_EditDone](MUI_List.md/#MUIM_List_EditDone), List1 demo source

## MUIM_List_CreateImage
### NAME
[MUIM_List_CreateImage](MUI_List.md/#MUIM_List_CreateImage) -- V11, 0x80429804

### SYNOPSIS
`DoMethod(obj, MUIM_List_CreateImage, Object *obj, ULONG flags);`

### FUNCTION
If you want to have custom images in a listview (e.g. like the little monitor
icons in PSI), you should create them as Bitmap objects (or Bodychunk objects)
in the setup method of your list class (use a subclass!).

After that, pass the newly created object pointer to [MUIM_List_CreateImage](MUI_List.md/#MUIM_List_CreateImage) and
use the result in your display hook with

\33O[%08lx]

where %08lx must be replaced by the pointer you got from [MUIM_List_CreateImage](MUI_List.md/#MUIM_List_CreateImage).

When your list is done (i.e. in the Cleanup method), kill your image with
[MUIM_List_DeleteImage](MUI_List.md/#MUIM_List_DeleteImage) and dispose your object.

### INPUTS
**`Object *obj`**
     image object to be inserted into the list.

**`ULONG flags`**
     none defined yet, set to 0.

### RESULT
The result you get is a black box pointer, it's not valid to assume anything
about it. The only useful thing you can do is to include it in \33O[%08lx]. The
result may be NULL in which case MUI was unable to create the image, but the
\33O[] combination simply draws nothing when receiving a NULL so it should not
be considered an error.

### EXAMPLE
See ScreenList class in screen inspector source code psi.c

### SEE ALSO
[MUIM_List_DeleteImage](MUI_List.md/#MUIM_List_DeleteImage)

## MUIM_List_DeleteImage
### NAME
[MUIM_List_DeleteImage](MUI_List.md/#MUIM_List_DeleteImage) -- V11, 0x80420f58

### SYNOPSIS
`DoMethod(obj, MUIM_List_DeleteImage, APTR listimg);`

### FUNCTION
Delete the image pointer returned from [MUIM_List_CreateImage](MUI_List.md/#MUIM_List_CreateImage).

### INPUTS
**`APTR listimg`**
     the image pointer returned from [MUIM_List_CreateImage](MUI_List.md/#MUIM_List_CreateImage).

### SEE ALSO
[MUIM_List_DeleteImage](MUI_List.md/#MUIM_List_DeleteImage)

## MUIM_List_Destruct
### NAME
[MUIM_List_Destruct](MUI_List.md/#MUIM_List_Destruct) -- V20, 0x80427d51

### SYNOPSIS
`DoMethod(obj, MUIM_List_Destruct, APTR entry, APTR pool);`

### FUNCTION
Destruct a list item. This method is meant to replace [MUIA_List_DestructHook](MUI_List.md/#MUIA_List_DestructHook) for
subclasses of List class.

### INPUTS
**`APTR entry`**
     entry to destruct.

**`APTR pool`**
     memory pool pointer.

### SEE ALSO
[MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook), [MUIA_List_DestructHook](MUI_List.md/#MUIA_List_DestructHook), [MUIM_List_Construct](MUI_List.md/#MUIM_List_Construct)

## MUIM_List_Display
### NAME
[MUIM_List_Display](MUI_List.md/#MUIM_List_Display) -- V20, 0x80425377

### SYNOPSIS
`DoMethod(obj, MUIM_List_Display, APTR entry, CONST_STRPTR *array, LONG row);`

### FUNCTION
Display a list item on the screen. This method is meant to replace
[MUIA_List_DisplayHook](MUI_List.md/#MUIA_List_DisplayHook) for subclasses of List class.

### INPUTS
**`APTR entry`**
     entry to be displayed.

**`CONST_STRPTR *array`**
     pointer to array of string pointers, to be filled with the individual column
     entries.

**`LONG row`**
     current row number (V21).

If entry is NULL you are supposed to return strings for the list's title, unless
they are supplied by [MUIA_List_TitleArray](MUI_List.md/#MUIA_List_TitleArray) already.

### SEE ALSO
[MUIA_List_DisplayHook](MUI_List.md/#MUIA_List_DisplayHook), [MUIA_List_Format](MUI_List.md/#MUIA_List_Format), [MUIA_List_MaxColumns](MUI_List.md/#MUIA_List_MaxColumns),
[MUIA_List_TitleArray](MUI_List.md/#MUIA_List_TitleArray)

## MUIM_List_Edit
### NAME
[MUIM_List_Edit](MUI_List.md/#MUIM_List_Edit) -- V21, 0x8042843d

### SYNOPSIS
`DoMethod(obj, MUIM_List_Edit, LONG row, LONG column);`

### FUNCTION
Edit a list item "inline" withing the list. The supplied row and column numbers
will be propagated to the methods [MUIM_List_CreateEditObject](MUI_List.md/#MUIM_List_CreateEditObject) and
[MUIM_List_EditDone](MUI_List.md/#MUIM_List_EditDone). Internally [MUIM_List_Edit](MUI_List.md/#MUIM_List_Edit) will call
[MUIM_List_CreateEditObject](MUI_List.md/#MUIM_List_CreateEditObject) whenever it is necessary to create a new object for
editing. Eventually [MUIM_List_EditDone](MUI_List.md/#MUIM_List_EditDone) will be called to signal the end of the
editing action.

Custom classes should call DoSuperMethod() in case editing is allowed for the
specified entry. This will let List class do all necessary actions for inline
editing.

### INPUTS
**`LONG row`**
     row of the entry to be edited. Use MUIV_List_Edit_Active to edit the currently
     active entry.

**`LONG column`**
     column of the entry to be edited.

### RESULT
A boolean value indicating whether the inline editing is possible or not.

### EXAMPLE
```c++
/* edit the 2nd column of the active item */
DoMethod(list, MUIM_List_Edit, MUIV_List_Edit_Active, 1);
[...]

ULONG myListEdit(struct IClass *cl, Object *obj,
    struct MUIP_List_Edit *msg)
{
  /* call the super class' method for all editable columns or return FALSE
     for non-editable columns */
  if(msg->column != 2)
    return DoSuperMethodA(cl, obj, (Msg)msg);
  else
    return FALSE;
}
```

### SEE ALSO
[MUIA_List_Editable](MUI_List.md/#MUIA_List_Editable), [MUIM_List_CreateEditObject](MUI_List.md/#MUIM_List_CreateEditObject), [MUIM_List_EditDone](MUI_List.md/#MUIM_List_EditDone),
List1 demo source

## MUIM_List_EditDone
### NAME
[MUIM_List_EditDone](MUI_List.md/#MUIM_List_EditDone) -- V21, 0x80423ab3

### SYNOPSIS
`DoMethod(obj, MUIM_List_EditDone, LONG row, LONG column, APTR entry, Object *editobj);`

### FUNCTION
This method is called whenever the editing action is about to be finished.

### INPUTS
**`LONG row`**
     row of the edited entry.

**`LONG column`**
     column of the edited entry.

**`APTR entry`**
     a pointer to the entry to be edited.

**`Object *editobj`**
     a pointer to the edit object.

### NOTES
This method is supposed to return TRUE in case the supplied "entry" pointer is
NULL to indicate an abortion of the edit action.

### RESULT
A boolean value indicating whether editing is allowed to be finished.

### EXAMPLE
```c++
ULONG myListEditDone(struct IClass *cl, Object *obj,
    struct MUIP_List_EditDone *msg)
{
  if(msg->entry != NULL)
  {
    /* editing was finished successfully
       the new contents can be taken from msg->editobj to transfer them into
       msg->entry, possibly depending on the to be edited column. */
  }
  else
  {
    /* editing was aborted */
  }

  /* let List class do its cleanup job */
  return TRUE;
}
```

### SEE ALSO
[MUIA_List_Editable](MUI_List.md/#MUIA_List_Editable), [MUIM_List_Edit](MUI_List.md/#MUIM_List_Edit), List1 demo source

## MUIM_List_EndEdit
### NAME
[MUIM_List_EndEdit](MUI_List.md/#MUIM_List_EndEdit) -- V22, 0x804203ee

### SYNOPSIS
`DoMethod(obj, MUIM_List_EndEdit, ULONG mode);`

### FUNCTION
This method can be called whenever the editing action is to be finished by the
application.

### INPUTS
**`ULONG mode`**
     that way to end the editing process. Use MUIV_List_EndEdit_Abort to abort the
     editing or use any other of the MUIV_List_EndEdit_XXX modes to successfully
     finish the editing.

### RESULT
A boolean value indicating whether editing really ended or not.

### SEE ALSO
[MUIA_List_Editable](MUI_List.md/#MUIA_List_Editable), [MUIM_List_Edit](MUI_List.md/#MUIM_List_Edit), List1 demo source

## MUIM_List_Exchange
### NAME
[MUIM_List_Exchange](MUI_List.md/#MUIM_List_Exchange) -- V4, 0x8042468c

### SYNOPSIS
`DoMethod(obj, MUIM_List_Exchange, LONG pos1, LONG pos2);`

### FUNCTION
Exchange two entries in a list.

### INPUTS
**`LONG pos1`**
     number of the first entry.

**`LONG pos2`**
     number of the second entry.

Possible special values since muimaster.library V9:

  * MUIV_List_Exchange_Top       0
  * MUIV_List_Exchange_Active   -1
  * MUIV_List_Exchange_Bottom   -2
  * MUIV_List_Exchange_Next     -3 /* only valid for second parameter */
  * MUIV_List_Exchange_Previous -4 /* only valid for second parameter */

### SEE ALSO
[MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert), [MUIM_List_Remove](MUI_List.md/#MUIM_List_Remove), [MUIM_List_Move](MUI_List.md/#MUIM_List_Move)

## MUIM_List_GetEntry
### NAME
[MUIM_List_GetEntry](MUI_List.md/#MUIM_List_GetEntry) -- V4, 0x804280ec

### SYNOPSIS
`DoMethod(obj, MUIM_List_GetEntry, LONG pos, APTR *entry);`

### FUNCTION
Get an entry of a list.

### INPUTS
**`LONG pos`**
     number of entry, MUIV_List_GetEntry_Active can be used to get the active entry.

**`APTR *entry`**
     pointer to a longword where the entry will be stored. If the entry is not
     available (either because you are out of bounds or because there is no active
     entry), you will receive a NULL pointer.

### RESULT
The pointer to the obtained entry or NULL in case of a failure.

### EXAMPLE
```c++
/* iterate through a list containing file info blocks */
for(i=0;;i++)
{
  struct FileInfoBlock *fib;

  DoMethod(list, MUIM_List_GetEntry, i, &fib);
  if (!fib) break;

  printf("%s\n", fib->fib_FileName);
}
```

### SEE ALSO
[MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert), [MUIM_List_Remove](MUI_List.md/#MUIM_List_Remove)

## MUIM_List_Insert
### NAME
[MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert) -- V4, 0x80426c87

### SYNOPSIS
`DoMethod(obj, MUIM_List_Insert, APTR *entries, LONG count, LONG pos);`

### FUNCTION
Insert new entries into a list. When the list has a construct hook, the given
pointers won't be inserted directly but instead passed through to the construct
hook.

### INPUTS
**`APTR *entries`**
     pointer to an array of pointers to be inserted.
     WARNING: This is a pointer to a pointer. See example for details.

**`LONG count`**
     number of elements to be inserted. If count==-1, entries will be inserted until
     a NULL pointer in the entries array is found.

**`LONG pos`**
     new entries will be added in front of this entry.
       * MUIV_List_Insert_Top: insert as first entry.
       * MUIV_List_Insert_Active: insert in front of the active entry.
       * MUIV_List_Insert_Sorted: insert sorted.
       * MUIV_List_Insert_Bottom: insert as last entry.

If pos is bigger or equal to the number of entries in the list, it is treated
like MUIV_List_Insert_Bottom.

### EXAMPLE
```c++
/* insert a string */
char *str = "New entry";
DoMethod(list, MUIM_List_Insert, &str, 1, MUIV_List_Insert_Bottom);

/* insert an array */
const char *str[] =
{
  "Entry 1",
  "Entry 2",
  "Entry 3",
  "Entry 4",
  NULL
};
DoMethod(list, MUIM_List_Insert, str, -1, MUIV_List_Insert_Bottom);
```

### SEE ALSO
[MUIM_List_Remove](MUI_List.md/#MUIM_List_Remove), [MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook)

## MUIM_List_InsertSingle
### NAME
[MUIM_List_InsertSingle](MUI_List.md/#MUIM_List_InsertSingle) -- V7, 0x804254d5

### SYNOPSIS
`DoMethod(obj, MUIM_List_InsertSingle, APTR entry, LONG pos);`

### FUNCTION
Insert one new entry into a list. Using [MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert) has caused some
confusion since it takes an array to items instead a single item. To insert
single items, [MUIM_List_InsertSingle](MUI_List.md/#MUIM_List_InsertSingle) is the better choice.

When the list has a construct hook, the given pointer won't be inserted directly
but instead passed through to the construct hook.

### INPUTS
**`APTR entry`**
     item to insert.

**`LONG pos`**
     new entry will be added in front of this entry.
       * MUIV_List_Insert_Top: insert as first entry.
       * MUIV_List_Insert_Active: insert in front of the active entry.
       * MUIV_List_Insert_Sorted: insert sorted.
       * MUIV_List_Insert_Bottom: insert as last entry.

If pos is bigger or equal to the number of entries in the list, it is treated
like MUIV_List_Insert_Bottom.

### EXAMPLE
```c++
/* insert a string */
DoMethod(list, MUIM_List_InsertSingle, "foobar", MUIV_List_Insert_Bottom);
```

### SEE ALSO
[MUIM_List_Remove](MUI_List.md/#MUIM_List_Remove), [MUIA_List_ConstructHook](MUI_List.md/#MUIA_List_ConstructHook), [MUIM_List_InsertSingle](MUI_List.md/#MUIM_List_InsertSingle)

## MUIM_List_Jump
### NAME
[MUIM_List_Jump](MUI_List.md/#MUIM_List_Jump) -- V4, 0x8042baab

### SYNOPSIS
`DoMethod(obj, MUIM_List_Jump, LONG pos);`

### FUNCTION
Scroll any entry into the visible part of a list.

Note: Jumping to an entry doesn't mean to make this entry the active one. This
can be done by setting the [MUIA_List_Active](MUI_List.md/#MUIA_List_Active) attribute.

### INPUTS
**`LONG pos`**
     number of the entry that should be made visible. Use MUIV_List_Jump_Active to
     jump to the active entry.

### EXAMPLE
```c++
/* line 42 is interesting, so make it visible */
DoMethod(list, MUIM_List_Jump, 42);
```

### SEE ALSO
[MUIA_List_Active](MUI_List.md/#MUIA_List_Active)

## MUIM_List_Move
### NAME
[MUIM_List_Move](MUI_List.md/#MUIM_List_Move) -- V9, 0x804253c2

### SYNOPSIS
`DoMethod(obj, MUIM_List_Move, LONG from, LONG to);`

### FUNCTION
Move an entry from one position to another.

### INPUTS
**`LONG from`**
     number of the first entry.

**`LONG to`**
     number of the second entry.

Possible special values since muimaster.library V9:

  * MUIV_List_Move_Top       0
  * MUIV_List_Move_Active   -1
  * MUIV_List_Move_Bottom   -2
  * MUIV_List_Move_Next     -3 /* only valid for second parameter */
  * MUIV_List_Move_Previous -4 /* only valid for second parameter */

### SEE ALSO
[MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert), [MUIM_List_Remove](MUI_List.md/#MUIM_List_Remove), [MUIM_List_Exchange](MUI_List.md/#MUIM_List_Exchange)

## MUIM_List_NextSelected
### NAME
[MUIM_List_NextSelected](MUI_List.md/#MUIM_List_NextSelected) -- V6, 0x80425f17

### SYNOPSIS
`DoMethod(obj, MUIM_List_NextSelected, LONG *pos);`

### FUNCTION
Iterate through the selected entries of a list. This method steps through the
contents of a (multi select) list and returns every entry that is currently
selected. When no entry is selected, but an entry is active, only the active
entry will be returned.

This behaviour will result in not returning the active entry when you have some
other selected entries somewhere in your list. Since the active entry just acts
as some kind of cursor mark, this seems to be the only sensible possibility to
handle multi selection together with keyboard control.

### INPUTS
**`LONG *pos`**
     a pointer to longword that will hold the number of the returned entry. Must be
     set to MUIV_List_NextSelected_Start at start of iteration. Is set to
     MUIV_List_NextSelected_End when iteration is finished.

### EXAMPLE
```c++
/* Iterate through a list with FileInfoBlocks */
struct FileInfoBlock *fib;
LONG id = MUIV_List_NextSelected_Start;

for (;;)
{
  DoMethod(list, MUIM_List_NextSelected, &id);
  if (id == MUIV_List_NextSelected_End) break;

  DoMethod(list, MUIM_List_GetEntry, id, &fib);
  printf("selected: %s\n", fib->fib_FileName);
}
```

### SEE ALSO
[MUIM_List_Select](MUI_List.md/#MUIM_List_Select)

## MUIM_List_QueryColumnWidth
### NAME
[MUIM_List_QueryColumnWidth](MUI_List.md/#MUIM_List_QueryColumnWidth) -- V11, 0x8042e09e

### SYNOPSIS
`DoMethod(obj, MUIM_List_QueryColumnWidth, LONG colnr);`

### FUNCTION
Determine the graphical widths a list column.

### INPUTS
**`LONG colnr`**
     number of the column to be queried.

### RESULT
The pixel width of the column, or -1 if the column is invisible, or -2 if the
column does not exist.

## MUIM_List_Redraw
### NAME
[MUIM_List_Redraw](MUI_List.md/#MUIM_List_Redraw) -- V4, 0x80427993

### SYNOPSIS
`DoMethod(obj, MUIM_List_Redraw, LONG pos, APTR entry);`

### FUNCTION
If you made some changes to an entry of your list and want these changes to be
shown in the display, you will have to call this method.

### INPUTS
**`LONG pos`**
     number of the line to redraw. When the line is not currently visible, nothing
     will happen. Specials:
       * MUIV_List_Redraw_Active: redraw the active line (if any),
       * MUIV_List_Redraw_All: redraw all lines.
       * MUIV_List_Redraw_Entry: redraw a specific entry (see below).

**`APTR entry`**
     address of the entry to be redrawn if pos is MUIV_List_Redraw_Entry.

### EXAMPLE
```c++
/* do a complete refresh: */
DoMethod(list, MUIM_List_Redraw, MUIV_List_Redraw_All, NULL);
```

## MUIM_List_Remove
### NAME
[MUIM_List_Remove](MUI_List.md/#MUIM_List_Remove) -- V4, 0x8042647e

### SYNOPSIS
`DoMethod(obj, MUIM_List_Remove, LONG pos);`

### FUNCTION
Remove an entry from a list.

### INPUTS
**`LONG pos`**
     number of the entry to be removed or one of
       * MUIV_List_Remove_First,
       * MUIV_List_Remove_Active,
       * MUIV_List_Remove_Last,
       * MUIV_List_Remove_Selected.

When the active entry is removed, the following entry will become active.

### EXAMPLE
```c++
/* when delete is pressed, remove the active entry */
DoMethod(btdel, MUIM_Notify, MUIA_Pressed, FALSE,
  list, 2, MUIM_List_Remove, MUIV_List_Remove_Active);
```

### SEE ALSO
[MUIM_List_Insert](MUI_List.md/#MUIM_List_Insert), [MUIA_List_DestructHook](MUI_List.md/#MUIA_List_DestructHook)

## MUIM_List_Select
### NAME
[MUIM_List_Select](MUI_List.md/#MUIM_List_Select) -- V4, 0x804252d8

### SYNOPSIS
`DoMethod(obj, MUIM_List_Select, LONG pos, LONG seltype, LONG *state);`

### FUNCTION
Select/deselect a list entry or ask an entry if it is selected.

### INPUTS
**`LONG pos`**
     Number of the entry or
       * MUIV_List_Select_Active: for the active entry.
       * MUIV_List_Select_All: for all entries.

**`LONG seltype`**
       * MUIV_List_Select_Off: unselect entry.
       * MUIV_List_Select_On: select entry.
       * MUIV_List_Select_Toggle: toggle entry.
       * MUIV_List_Select_Ask: just ask about the state.

**`LONG *state`**
     pointer to a longword. If not NULL, this will be filled with the current
     selection state.

### NOTES
Since version V9 of muimaster.library:
If pos==MUIV_List_Select_All and seltype==MUIV_List_Select_Ask, state will be
filled with the total number of selected entries.

Only list objects with [MUIA_List_MultiSelect](MUI_List.md/#MUIA_List_MultiSelect)=TRUE can have more than one entry
selected. Selecting multiple entries for non-multiselection list will keep the
last selected entry in selected state only.

### EXAMPLE
```c++
/* toggle selection state of active entry */
DoMethod(list, MUIM_List_Select, MUIV_List_Select_Active,
  MUIV_List_Select_Toggle, NULL);

/* select all entries */
DoMethod(list, MUIM_List_Select, MUIV_List_Select_All,
  MUIV_List_Select_On, NULL);
```

### SEE ALSO
[MUIA_List_MultiTestHook](MUI_List.md/#MUIA_List_MultiTestHook)

## MUIM_List_Sort
### NAME
[MUIM_List_Sort](MUI_List.md/#MUIM_List_Sort) -- V4, 0x80422275

### SYNOPSIS
`DoMethod(obj, MUIM_List_Sort);`

### FUNCTION
Sort the list. MUI uses an iterative quicksort algorithm, no stack problems will
occur.

### SEE ALSO
[MUIA_List_CompareHook](MUI_List.md/#MUIA_List_CompareHook), [MUIM_List_Compare](MUI_List.md/#MUIM_List_Compare)

## MUIM_List_SortEntries
### NAME
[MUIM_List_SortEntries](MUI_List.md/#MUIM_List_SortEntries) -- V22, 0x80429e32

### SYNOPSIS
`DoMethod(obj, MUIM_List_SortEntries, APTR *entries);`

### FUNCTION
Sort an arbitrary list of entries according to the List object's sorting order.
The list MUST be terminated by a NULL entry.

### INPUTS
**`APTR entries`**
     pointer to a NULL terminated array of entries to be sorted.

### RESULT
A boolean value indicating whether the sorting succeeded or not.

### SEE ALSO
[MUIA_List_CompareHook](MUI_List.md/#MUIA_List_CompareHook), [MUIM_List_Compare](MUI_List.md/#MUIM_List_Compare), [MUIM_List_Sort](MUI_List.md/#MUIM_List_Sort)

## MUIM_List_TestPos
### NAME
[MUIM_List_TestPos](MUI_List.md/#MUIM_List_TestPos) -- V11, 0x80425f48

### SYNOPSIS
`DoMethod(obj, MUIM_List_TestPos, LONG x, LONG y, struct MUI_List_TestPos_Result *res);`

### FUNCTION
Find out which line/column of a listview is currently displayed at a certain
position.

### INPUTS
**`LONG x`**
     X coordinate to test.

**`LONG y`**
     Y coordinate to test.

**`struct MUI_List_TestPos_Result *res`**
     pointer to a MUI_List_TestPos_Result structure to be filled with the
     result of the test.

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
