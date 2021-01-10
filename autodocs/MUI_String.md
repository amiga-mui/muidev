# String.mui
## Super class
[Area.mui](MUI_Area.md)
## Background
String class generates standard string gadgets with all editing facilities
(clear, undo, etc.) enabled.

Common problems:
You may need a string gadget to show at least x numbers of characterss. If
you specify [MUIA_FixWidthTxt](MUI_Area/#MUIA_FixWidthTxt),"00000000" you can be sure that the width is
large enough to handle the number of chars.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_String_Accept](MUI_String.md/#MUIA_String_Accept)|V4|ISG|`STRPTR`
[MUIA_String_Acknowledge](MUI_String.md/#MUIA_String_Acknowledge)|V4|..G|`STRPTR`
[MUIA_String_AdvanceOnCR](MUI_String.md/#MUIA_String_AdvanceOnCR)|V11|ISG|`BOOL`
[MUIA_String_AttachedList](MUI_String.md/#MUIA_String_AttachedList)|V4|ISG|`Object *`
[MUIA_String_BufferPos](MUI_String.md/#MUIA_String_BufferPos)|V4|.SG|`LONG`
[MUIA_String_Contents](MUI_String.md/#MUIA_String_Contents)|V4|ISG|`STRPTR`
[MUIA_String_DisplayPos](MUI_String.md/#MUIA_String_DisplayPos)|V4|.SG|`LONG`
[MUIA_String_EditHook](MUI_String.md/#MUIA_String_EditHook)|V7|ISG|`struct Hook *`
[MUIA_String_Format](MUI_String.md/#MUIA_String_Format)|V4|I.G|`LONG`
[MUIA_String_InactiveContents](MUI_String.md/#MUIA_String_InactiveContents)|V20|ISG|`CONST_STRPTR`
[MUIA_String_Integer](MUI_String.md/#MUIA_String_Integer)|V4|ISG|`ULONG`
[MUIA_String_Integer64](MUI_String.md/#MUIA_String_Integer64)|V20|ISG|`int64 *`
[MUIA_String_LonelyEditHook](MUI_String.md/#MUIA_String_LonelyEditHook)|V11|ISG|`BOOL`
[MUIA_String_MaxLen](MUI_String.md/#MUIA_String_MaxLen)|V4|I.G|`LONG`
[MUIA_String_Placeholder](MUI_String.md/#MUIA_String_Placeholder)|V21|ISG|`CONST_STRPTR`
[MUIA_String_Reject](MUI_String.md/#MUIA_String_Reject)|V4|ISG|`STRPTR`
[MUIA_String_Secret](MUI_String.md/#MUIA_String_Secret)|V4|I.G|`BOOL`

## MUIA_String_Accept
### NAME
[MUIA_String_Accept](MUI_String/#MUIA_String_Accept) -- V4 [ISG], `STRPTR`, 0x8042e3e1

### FUNCTION
A string containing characters allowed as input for the string gadget. Whenever
the user hits a character not found in [MUIA_String_Accept](MUI_String/#MUIA_String_Accept), he will hear a beep
and gadget's contents won't be changed. The supplied string is NOT copied and
must remain valid as long as the string object lives. Pass a NULL pointer to let
String class accept all characters (the default). An empty string ("") is the
worst choice as this will let String class accept NO characters at all.

### EXAMPLE
```c++
StringObject,
  MUIA_String_Accept, "0123456789-",
  End,
```

### SEE ALSO
[MUIA_String_Reject](MUI_String/#MUIA_String_Reject)

## MUIA_String_Acknowledge
### NAME
[MUIA_String_Acknowledge](MUI_String/#MUIA_String_Acknowledge) -- V4 [..G], `STRPTR`, 0x8042026c

### FUNCTION
This attribute will be set to the contents of the string whenever the user
hits return in the gadget. An application can listen with notification and
take the appropriate action.

Using the TAB key or a mouse click to deactivate the gadget will not trigger
[MUIA_String_Acknowledge](MUI_String/#MUIA_String_Acknowledge).

### EXAMPLE
```c++
/* two string gadgets str1 and str2, the second should
/* become active after a return in the first: */

DoMethod(str1,MUIM_Notify,
  MUIA_String_Acknowledge, MUIV_EveryTime,
  windowobj, 3,
  MUIM_Set, MUIA_Window_ActiveObject, str2);
```

### SEE ALSO
[MUIA_String_Contents](MUI_String/#MUIA_String_Contents)

## MUIA_String_AdvanceOnCR
### NAME
[MUIA_String_AdvanceOnCR](MUI_String/#MUIA_String_AdvanceOnCR) -- V11 [ISG], `BOOL`, 0x804226de

### FUNCTION
Set this if you want carriage returns in string gadgets behave like the
TAB key, i.e. pressing CR will activate the next/previous gadget in the
cycle chain.

### SEE ALSO
[MUIA_CycleChain](MUI_Area/#MUIA_CycleChain)

## MUIA_String_AttachedList
### NAME
[MUIA_String_AttachedList](MUI_String/#MUIA_String_AttachedList) -- V4 [ISG], `Object *`, 0x80420fd2

### FUNCTION
This special attribute can be set to point to a valid MUI object of List or
Listview class. This enables controlling the lists cursor from within the
string gadget, all cursor key events will be forwarded.

### SEE ALSO
[MUIA_String_Contents](MUI_String/#MUIA_String_Contents), [MUIA_List_Active](MUI_List/#MUIA_List_Active)

## MUIA_String_BufferPos
### NAME
[MUIA_String_BufferPos](MUI_String/#MUIA_String_BufferPos) -- V4 [.SG], `LONG`, 0x80428b6c

### FUNCTION
[MUIA_String_BufferPos](MUI_String/#MUIA_String_BufferPos) can be used to get and set the position of the cursor
in the string gadget.
This attribute is probably not very interesting.

### SEE ALSO
[MUIA_String_Contents](MUI_String/#MUIA_String_Contents), [MUIA_String_DisplayPos](MUI_String/#MUIA_String_DisplayPos)

## MUIA_String_Contents
### NAME
[MUIA_String_Contents](MUI_String/#MUIA_String_Contents) -- V4 [ISG], `STRPTR`, 0x80428ffd

### FUNCTION
Get and set a string gadgets contents. You may not modify the returned
string.

[MUIA_String_Contents](MUI_String/#MUIA_String_Contents) gets updated every time when the contents of the string
gadget change. When you set up a notification on this attribute, you will
hear about every keystroke.

### NOTES
If you try to set contents to something larger than [MUIA_String_MaxLen](MUI_String/#MUIA_String_MaxLen)
(including the 0-byte!), MUI will silently strip the additional characters.

### EXAMPLE
```c++
/* The given hook will be called after every change */
/* in the string gadget. It receives a pointer to   */
/* a pointer to the current contents in register a1 */
/* (see MUIM_CallHook for details)                  */

DoMethod(str, MUIM_Notify,
  MUIA_String_Contents, MUIV_EveryTime,
  str, 3,
  MUIM_CallHook, &hook, MUIV_TriggerValue);
```

### SEE ALSO
[MUIA_String_Accept](MUI_String/#MUIA_String_Accept), [MUIA_String_Reject](MUI_String/#MUIA_String_Reject), [MUIA_String_MaxLen](MUI_String/#MUIA_String_MaxLen)

## MUIA_String_DisplayPos
### NAME
[MUIA_String_DisplayPos](MUI_String/#MUIA_String_DisplayPos) -- V4 [.SG], `LONG`, 0x8042ccbf

### FUNCTION
[MUIA_String_DisplayPos](MUI_String/#MUIA_String_DisplayPos) can be used to get and set the number of the first
character of the string to be displayed.
This attribute is probably not very interesting.

### SEE ALSO
[MUIA_String_Contents](MUI_String/#MUIA_String_Contents), [MUIA_String_BufferPos](MUI_String/#MUIA_String_BufferPos)

## MUIA_String_EditHook
### NAME
[MUIA_String_EditHook](MUI_String/#MUIA_String_EditHook) -- V7 [ISG], `struct Hook *`, 0x80424c33

### FUNCTION
When specified, MUI calls this hook as if it was a real string edit hook in a
real string gadget. It receives a pointer to itself in A0, a pointer to a SGWork
structure in A2 and a pointer to the message in A1.

You MUST check the EditOp field in the passed SGWork structure and act
appropriately according to Intuition's documentation (intuition/sghooks.h).

### NOTES
Since the String class of MUI4 is no longer based on a string object created by
Intuition's strgclass the supplied edit hook will be called with faked
structures. Please note that these structures might not contain exactly the
same values that one might expect for an object managed by Intuition. If
something is missing here or definitely contradicts the way how Intuition
handles a certain situation then please open an appropriate ticket in MUI's
bugtracker at https://www.muidev.de/newticket.

### SEE ALSO
intuition/sghooks.h

## MUIA_String_Format
### NAME
[MUIA_String_Format](MUI_String/#MUIA_String_Format) -- V4 [I.G], `LONG`, 0x80427484

### SPECIAL INPUTS
  * MUIV_String_Format_Left
  * MUIV_String_Format_Center
  * MUIV_String_Format_Right

### FUNCTION
Used to adjust the alignment of the input string.

### SEE ALSO
[MUIA_String_BufferPos](MUI_String/#MUIA_String_BufferPos), [MUIA_String_DisplayPos](MUI_String/#MUIA_String_DisplayPos), [MUIA_String_Contents](MUI_String/#MUIA_String_Contents)

## MUIA_String_InactiveContents
### NAME
[MUIA_String_InactiveContents](MUI_String/#MUIA_String_InactiveContents) -- V20 [ISG], `CONST_STRPTR`, 0x80427ecf

### FUNCTION
In case the string object is inactive and no text has been entered by the
user or set by the application the text specified by this attribute is
displayed instead. To improve the visual feedback the text will be displayed
with italic style and shadow color. The supplied string is NOT copied and
must remain valid as long as the string object lives.

### SEE ALSO
[MUIA_String_Contents](MUI_String/#MUIA_String_Contents), [MUIA_String_Placeholder](MUI_String/#MUIA_String_Placeholder)

## MUIA_String_Integer
### NAME
[MUIA_String_Integer](MUI_String/#MUIA_String_Integer) -- V4 [ISG], `ULONG`, 0x80426e8a

### FUNCTION
Useful for turning a string gadget into an integer gadget. Setting this
attribute puts the value with "%ld" into the gadget, getting it returns a
longword containing the string gadgets contents as number.

You should set [MUIA_String_Accept](MUI_String/#MUIA_String_Accept) to "0123456789" or something like that to
avoid wrong characters.

### EXAMPLE
```c++
StringObject,
  MUIA_String_Accept, "0123456879",
  MUIA_String_Integer, 42,
  End;
```

## MUIA_String_Integer64
### NAME
[MUIA_String_Integer64](MUI_String/#MUIA_String_Integer64) -- V20 [ISG], `int64 *`, 0x80424820

### FUNCTION
Useful for turning a string gadget into an integer gadget. Setting this
attribute puts the value with "%lld" into the gadget, getting it returns a
64bit value containing the string gadgets contents as number.

You should set [MUIA_String_Accept](MUI_String/#MUIA_String_Accept) to "0123456789" or something like that to
avoid wrong characters.

### EXAMPLE
```c++
StringObject,
  MUIA_String_Accept, "0123456879",
  MUIA_String_Integer64, 42,
  End;
```

## MUIA_String_LonelyEditHook
### NAME
[MUIA_String_LonelyEditHook](MUI_String/#MUIA_String_LonelyEditHook) -- V11 [ISG], `BOOL`, 0x80421569

### FUNCTION
If your string object has an edit hook, you can set this to TRUE to skip
MUI's private edit hook completely. Otherwise, your hook will be executed
and the private one of MUI.

## MUIA_String_MaxLen
### NAME
[MUIA_String_MaxLen](MUI_String/#MUIA_String_MaxLen) -- V4 [I.G], `LONG`, 0x80424984

### FUNCTION
Setup the maximum length for the string gadget. This attribute is only valid
at object creation time.

Defaults to 80 characters.

### NOTES
The maximum length includes the 0-byte at the end of the string. To
let the user enter e.g. 10 characters, you would have to specify a
maximum length len of 11.

### SEE ALSO
[MUIA_String_Contents](MUI_String/#MUIA_String_Contents)

## MUIA_String_Placeholder
### NAME
[MUIA_String_Placeholder](MUI_String/#MUIA_String_Placeholder) -- V21 [ISG], `CONST_STRPTR`, 0x8042ae65

### FUNCTION
In case the string object is inactive and no text has been entered by the
user or set by the application the text specified by this attribute is
displayed instead. To improve the visual feedback the text will be displayed
with italic style and shadow color. The supplied string is NOT copied and
must remain valid as long as the string object lives.

### SEE ALSO
[MUIA_String_Contents](MUI_String/#MUIA_String_Contents), [MUIA_String_InactiveContents](MUI_String/#MUIA_String_InactiveContents)

## MUIA_String_Reject
### NAME
[MUIA_String_Reject](MUI_String/#MUIA_String_Reject) -- V4 [ISG], `STRPTR`, 0x8042179c

### FUNCTION
A string containing characters that should not be accepted as input for the
string gadget. Whenever the user hits such a char, he will hear a beep and the
gadget's contents won't be changed. The supplied string is NOT copied and must
remain valid as long as the string object lives. Pass a NULL pointer to let
String class reject no characters (the default).

### SEE ALSO
[MUIA_String_Accept](MUI_String/#MUIA_String_Accept)

## MUIA_String_Secret
### NAME
[MUIA_String_Secret](MUI_String/#MUIA_String_Secret) -- V4 [I.G], `BOOL`, 0x80428769

### FUNCTION
This attribute causes the string gadget to display only dots instead of the
real contents. Useful for password requesters.

### SEE ALSO
[MUIA_String_Contents](MUI_String/#MUIA_String_Contents)

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
