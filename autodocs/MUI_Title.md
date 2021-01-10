# Title.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
Title class is the new replacement class for the old register class. It
offers much more flexibility regarding dynamic page adding/removal as well
as improved handling of many tabs and possibilities for the tab titles
itself.

The most basic way to make use of Title class looks like this:

```c++
VGroup,
  Child, TitleObject,
    Child, TextObject, MUIA_Text_Contents, "page 1", End,
    Child, TextObject, MUIA_Text_Contents, "page 2", End,
    Child, TextObject, MUIA_Text_Contents, "page 3", End,
  End,

  Child, [page 1 contents],
  Child, [page 2 contents],
  Child, [page 3 contents],
End
```

The title class object always must be the very first object within the
surrounding group. All following children of the surrounding group
correspond to the individual pages. Unlike Register class the tabs titles
are no longer simple texts but true objects now. This means that an
application can use any combination of groups, texts and images with
arbitrary layout instead of just plain texts. In addition to Register class
Title class can handle an infinite amount of tabs. If there is not enough
space to display all tabs only a few tabs will be displayed along with
scroll buttons to make the currently invisible tabs visible. These scroll
buttons also feature a context menu to let the user choose the active page
from all available pages.

The Title demo implements a custom class as subclass of Title class to show
how dynamic adding/removal of tabs/pages is to be done.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Title_Clickable](MUI_Title.md/#MUIA_Title_Clickable)|V20|I..|`LONG`
[MUIA_Title_Closable](MUI_Title.md/#MUIA_Title_Closable)|V20|ISG|`BOOL`
[MUIA_Title_EventHandlerPriority](MUI_Title.md/#MUIA_Title_EventHandlerPriority)|V20|I..|`LONG`
[MUIA_Title_Newable](MUI_Title.md/#MUIA_Title_Newable)|V20|ISG|`BOOL`
[MUIA_Title_OnLastClose](MUI_Title.md/#MUIA_Title_OnLastClose)|V21|IS.|`LONG`
[MUIA_Title_Position](MUI_Title.md/#MUIA_Title_Position)|V20|ISG|`LONG`
[MUIA_Title_Sortable](MUI_Title.md/#MUIA_Title_Sortable)|V20|ISG|`BOOL`

## Methods
Method|Version
------|-------
[MUIM_Title_Close](MUI_Title.md/#MUIM_Title_Close)|V20
[MUIM_Title_FindPage](MUI_Title.md/#MUIM_Title_FindPage)|V22
[MUIM_Title_New](MUI_Title.md/#MUIM_Title_New)|V20

## MUIA_Title_Clickable
### NAME
[MUIA_Title_Clickable](MUI_Title.md/#MUIA_Title_Clickable) -- V20 [I..], `LONG`, 0x80425959

### FUNCTION
Setting this attribute to FALSE will let the Title object ignore all clicks
on its tabs and hence prevent page changes.

Defaults to TRUE.

## MUIA_Title_Closable
### NAME
[MUIA_Title_Closable](MUI_Title.md/#MUIA_Title_Closable) -- V20 [ISG], `BOOL`, 0x80420402

### FUNCTION
Setting this attribute to TRUE will add a close button to each tab object.
Clicking the close button will invoke the [MUIM_Title_Close](MUI_Title.md/#MUIM_Title_Close) method with a pointer
to the tab object the close buttons corresponds to. Title class will **NOT**
close the tab itself. This task remains the responsibility of the implementing
class and hence also requires the developer to implement a subclass of Title
class to handle the method.

Defaults to FALSE.

### EXAMPLE
See supplied Title demo.

### SEE ALSO
[MUIM_Title_Close](MUI_Title.md/#MUIM_Title_Close)

## MUIA_Title_EventHandlerPriority
### NAME
[MUIA_Title_EventHandlerPriority](MUI_Title.md/#MUIA_Title_EventHandlerPriority) -- V20 [I..], `LONG`, 0x804286bc

### SPECIAL INPUTS
  * MUIV_Title_EventHandlerPriority_Default

### FUNCTION
Defines the priority of the internal eventhandler. This attribute is of use
only if you need to do something **before** the internal eventhandler and
eventually might eat the events you are interested in.

Defaults to MUIV_Title_EventHandlerPriority_Default.

## MUIA_Title_Newable
### NAME
[MUIA_Title_Newable](MUI_Title.md/#MUIA_Title_Newable) -- V20 [ISG], `BOOL`, 0x80424145

### FUNCTION
Setting this attribute to TRUE will add a "+" button after the rightmost tab
object. Clicking the "+" button will invoke the [MUIM_Title_New](MUI_Title.md/#MUIM_Title_New) method to let the
application add a new title button object and a new page object. Title class
will **NOT** add the new tab itself. This task remains the responsibility of
the implementing class and hence also requires the developer to implement a
subclass of Title class to handle the method.

Defaults to FALSE.

### EXAMPLE
See supplied Title demo.

### SEE ALSO
[MUIM_Title_New](MUI_Title.md/#MUIM_Title_New)

## MUIA_Title_OnLastClose
### NAME
[MUIA_Title_OnLastClose](MUI_Title.md/#MUIA_Title_OnLastClose) -- V21 [IS.], `LONG`, 0x804253cf

### SPECIAL INPUTS
  * MUIV_Title_OnLastClose_Remove
  * MUIV_Title_OnLastClose_WindowAction

### FUNCTION
This attribute defines how the object will react when the last tab is to be
closed.
Setting this attribute to MUIV_Title_OnLastClose_Remove will invoke the
usual [MUIM_Title_Close](MUI_Title.md/#MUIM_Title_Close) method on the object. Setting the attribute to
MUIV_Title_OnLastClose_WindowAction will trigger a close request on the
object's window.

Defaults to MUIV_Title_OnLastClose_Remove.

### SEE ALSO
[MUIM_Title_Close](MUI_Title.md/#MUIM_Title_Close)

## MUIA_Title_Position
### NAME
[MUIA_Title_Position](MUI_Title.md/#MUIA_Title_Position) -- V20 [ISG], `LONG`, 0x804273a3

### SPECIAL INPUTS
  * MUIV_Title_Position_Top
  * MUIV_Title_Position_Bottom
  * MUIV_Title_Position_Left
  * MUIV_Title_Position_Right

### FUNCTION
Defines the position of the tab titles. Currently only top and bottom
placement is implemented. Left and right placement will hopefully be
implemented in near future.

Defaults to MUIV_Title_Position_Top.

## MUIA_Title_Sortable
### NAME
[MUIA_Title_Sortable](MUI_Title.md/#MUIA_Title_Sortable) -- V20 [ISG], `BOOL`, 0x804211f1

### FUNCTION
Define whether the individual tabs can be rearranged by drag'n'drop
operations. Title class will rearrange both the tab title objects as well
as the page objects after a drag'n'drop operation.

Defaults to FALSE.

## MUIM_Title_Close
### NAME
[MUIM_Title_Close](MUI_Title.md/#MUIM_Title_Close) -- V20, 0x8042303a

### SYNOPSIS
`DoMethod(obj, MUIM_Title_Close, Object *tito);`

### FUNCTION
This method will be invoked with a pointer to the to be closed tab object
when [MUIA_Title_Closable](MUI_Title.md/#MUIA_Title_Closable) is set to TRUE and the user clicks the close
button. The tab object as well as its corresponding page object will be
removed and disposed.

### NOTES
This method will actually be pushed onto the application's method stack
instead of being invoked directly to avoid possible crashes due to how MUI
handles input stuff internally. So don't be surprised if the method is
eventually invoked a tiny little bit later as you might expect it.

### EXAMPLE
See supplied Titles demo.

### SEE ALSO
[MUIA_Title_Closable](MUI_Title.md/#MUIA_Title_Closable)

## MUIM_Title_FindPage
### NAME
[MUIM_Title_FindPage](MUI_Title.md/#MUIM_Title_FindPage) -- V22, 0x80423d0d

### SYNOPSIS
`DoMethod(obj, MUIM_Title_FindPage, Object *titlebutton);`

### FUNCTION
This method will find the page object to the given title button object.

### INPUTS
**`Object *titlebutton`**
     a ponter to a valid title button object

### RESULT
A pointer to the found page object or NULL if the title button object points to
no valid page object.

## MUIM_Title_New
### NAME
[MUIM_Title_New](MUI_Title.md/#MUIM_Title_New) -- V20, 0x804247a6

### SYNOPSIS
`DoMethod(obj, MUIM_Title_New);`

### FUNCTION
This method will be invoked whenever a new page is to be created when
[MUIA_Title_Newable](MUI_Title.md/#MUIA_Title_Newable) is set to TRUE and the user clicked on the "New" button.
This method must add a new title button object to the Title object and a new
page object to the surrounding Group object.

### NOTES
This method is actually not yet fully implemented.

### SEE ALSO
[MUIA_Title_Newable](MUI_Title.md/#MUIA_Title_Newable)

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
