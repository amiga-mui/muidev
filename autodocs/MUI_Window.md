# Window.mui
## Super class
[Notify.mui](MUI_Notify.md)
## Inherited by
* [Aboutmui.mui](MUI_Aboutmui.md)
## Background
Objects of window class are used to generate windows and supply a place
where MUI gadgets feel well. It handles the complicated task of window
resizing fully automatic, you don't need to worry about that.

Windows are children of an application, you cannot use a window object
without having a parent application object. On the other side, the gadgets
in a window are children of the window, you cannot use MUI gadgets without
having a parent MUI window.

Creating a window object does not mean to open it instantly. This is done
later by setting the window's [MUIA_Window_Open](MUI_Window.md/#MUIA_Window_Open) attribute. If your
application has several windows, the usual way is to create them all at once
at startup time and open/close it later just by setting [MUIA_Window_Open](MUI_Window.md/#MUIA_Window_Open).

There is no difference in talking to gadgets whether their parent window is
open or not. If you e.g. set the contents of a string gadget in an open
window, the gadget will refresh immediately. If the window is closed, the
gadget just remembers its new setting and displays it later.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Window_Activate](MUI_Window.md/#MUIA_Window_Activate)|V4|ISG|`BOOL`
[MUIA_Window_ActiveObject](MUI_Window.md/#MUIA_Window_ActiveObject)|V4|.SG|`Object *`
[MUIA_Window_AltHeight](MUI_Window.md/#MUIA_Window_AltHeight)|V4|I.G|`LONG`
[MUIA_Window_AltLeftEdge](MUI_Window.md/#MUIA_Window_AltLeftEdge)|V4|I.G|`LONG`
[MUIA_Window_AltTopEdge](MUI_Window.md/#MUIA_Window_AltTopEdge)|V4|I.G|`LONG`
[MUIA_Window_AltWidth](MUI_Window.md/#MUIA_Window_AltWidth)|V4|I.G|`LONG`
[MUIA_Window_AppWindow](MUI_Window.md/#MUIA_Window_AppWindow)|V5|I..|`BOOL`
[MUIA_Window_Backdrop](MUI_Window.md/#MUIA_Window_Backdrop)|V4|I..|`BOOL`
[MUIA_Window_Borderless](MUI_Window.md/#MUIA_Window_Borderless)|V4|I..|`BOOL`
[MUIA_Window_CloseGadget](MUI_Window.md/#MUIA_Window_CloseGadget)|V4|I..|`BOOL`
[MUIA_Window_CloseRequest](MUI_Window.md/#MUIA_Window_CloseRequest)|V4|.SG|`BOOL`
[MUIA_Window_DefaultObject](MUI_Window.md/#MUIA_Window_DefaultObject)|V4|ISG|`Object *`
[MUIA_Window_DepthGadget](MUI_Window.md/#MUIA_Window_DepthGadget)|V4|I..|`BOOL`
[MUIA_Window_DisableKeys](MUI_Window.md/#MUIA_Window_DisableKeys)|V15|ISG|`ULONG`
[MUIA_Window_DragBar](MUI_Window.md/#MUIA_Window_DragBar)|V4|I..|`BOOL`
[MUIA_Window_DrawInfo](MUI_Window.md/#MUIA_Window_DrawInfo)|V4|..G|`struct DrawInfo *`
[MUIA_Window_FancyDrawing](MUI_Window.md/#MUIA_Window_FancyDrawing)|V8|ISG|`BOOL` **(OBSOLETE)**
[MUIA_Window_Height](MUI_Window.md/#MUIA_Window_Height)|V4|ISG|`LONG`
[MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)|V4|ISG|`ULONG`
[MUIA_Window_InputEvent](MUI_Window.md/#MUIA_Window_InputEvent)|V4|..G|`struct InputEvent *`
[MUIA_Window_IsSubWindow](MUI_Window.md/#MUIA_Window_IsSubWindow)|V4|ISG|`BOOL`
[MUIA_Window_LeftEdge](MUI_Window.md/#MUIA_Window_LeftEdge)|V4|ISG|`LONG`
[MUIA_Window_Menu](MUI_Window.md/#MUIA_Window_Menu)|V4|I..|`struct NewMenu *` **(OBSOLETE)**
[MUIA_Window_MenuAction](MUI_Window.md/#MUIA_Window_MenuAction)|V8|ISG|`ULONG`
[MUIA_Window_Menustrip](MUI_Window.md/#MUIA_Window_Menustrip)|V8|ISG|`Object *`
[MUIA_Window_MouseObject](MUI_Window.md/#MUIA_Window_MouseObject)|V10|..G|`Object *`
[MUIA_Window_NeedsMouseObject](MUI_Window.md/#MUIA_Window_NeedsMouseObject)|V10|I..|`BOOL` **(OBSOLETE)**
[MUIA_Window_NoMenus](MUI_Window.md/#MUIA_Window_NoMenus)|V4|ISG|`BOOL`
[MUIA_Window_Opacity](MUI_Window.md/#MUIA_Window_Opacity)|V20|ISG|`LONG`
[MUIA_Window_Open](MUI_Window.md/#MUIA_Window_Open)|V4|.SG|`BOOL`
[MUIA_Window_PublicScreen](MUI_Window.md/#MUIA_Window_PublicScreen)|V6|ISG|`STRPTR`
[MUIA_Window_RefWindow](MUI_Window.md/#MUIA_Window_RefWindow)|V4|IS.|`Object *`
[MUIA_Window_RootObject](MUI_Window.md/#MUIA_Window_RootObject)|V4|ISG|`Object *`
[MUIA_Window_Screen](MUI_Window.md/#MUIA_Window_Screen)|V4|ISG|`struct Screen *`
[MUIA_Window_ScreenTitle](MUI_Window.md/#MUIA_Window_ScreenTitle)|V5|ISG|`STRPTR`
[MUIA_Window_SizeGadget](MUI_Window.md/#MUIA_Window_SizeGadget)|V4|I..|`BOOL`
[MUIA_Window_SizeRight](MUI_Window.md/#MUIA_Window_SizeRight)|V4|I..|`BOOL`
[MUIA_Window_Sleep](MUI_Window.md/#MUIA_Window_Sleep)|V4|.SG|`BOOL`
[MUIA_Window_Title](MUI_Window.md/#MUIA_Window_Title)|V4|ISG|`STRPTR`
[MUIA_Window_TopEdge](MUI_Window.md/#MUIA_Window_TopEdge)|V4|ISG|`LONG`
[MUIA_Window_UseBottomBorderScroller](MUI_Window.md/#MUIA_Window_UseBottomBorderScroller)|V13|ISG|`BOOL`
[MUIA_Window_UseLeftBorderScroller](MUI_Window.md/#MUIA_Window_UseLeftBorderScroller)|V13|ISG|`BOOL`
[MUIA_Window_UseRightBorderScroller](MUI_Window.md/#MUIA_Window_UseRightBorderScroller)|V13|ISG|`BOOL`
[MUIA_Window_Width](MUI_Window.md/#MUIA_Window_Width)|V4|ISG|`LONG`
[MUIA_Window_Window](MUI_Window.md/#MUIA_Window_Window)|V4|..G|`struct Window *`

## Methods
Method|Version
------|-------
[MUIM_Window_AddEventHandler](MUI_Window.md/#MUIM_Window_AddEventHandler)|V16
[MUIM_Window_Cleanup](MUI_Window.md/#MUIM_Window_Cleanup)|V18
[MUIM_Window_GetMenuCheck](MUI_Window.md/#MUIM_Window_GetMenuCheck)|V4 **(OBSOLETE)**
[MUIM_Window_GetMenuState](MUI_Window.md/#MUIM_Window_GetMenuState)|V4 **(OBSOLETE)**
[MUIM_Window_RemEventHandler](MUI_Window.md/#MUIM_Window_RemEventHandler)|V16
[MUIM_Window_ScreenToBack](MUI_Window.md/#MUIM_Window_ScreenToBack)|V4
[MUIM_Window_ScreenToFront](MUI_Window.md/#MUIM_Window_ScreenToFront)|V4
[MUIM_Window_SetCycleChain](MUI_Window.md/#MUIM_Window_SetCycleChain)|V4 **(OBSOLETE)**
[MUIM_Window_SetMenuCheck](MUI_Window.md/#MUIM_Window_SetMenuCheck)|V4 **(OBSOLETE)**
[MUIM_Window_SetMenuState](MUI_Window.md/#MUIM_Window_SetMenuState)|V4 **(OBSOLETE)**
[MUIM_Window_Setup](MUI_Window.md/#MUIM_Window_Setup)|V18
[MUIM_Window_Snapshot](MUI_Window.md/#MUIM_Window_Snapshot)|V11
[MUIM_Window_ToBack](MUI_Window.md/#MUIM_Window_ToBack)|V4
[MUIM_Window_ToFront](MUI_Window.md/#MUIM_Window_ToFront)|V4

## MUIA_Window_Activate
### NAME
[MUIA_Window_Activate](MUI_Window.md/#MUIA_Window_Activate) -- V4 [ISG], `BOOL`, 0x80428d2f

### FUNCTION
Setting this to TRUE will activate the window. Setting this to FALSE has no
effect. The attribute will change whenever the user activates/deactivates
the window.

Specifying FALSE at object creation time will make the window open in an
inactive state.

## MUIA_Window_ActiveObject
### NAME
[MUIA_Window_ActiveObject](MUI_Window.md/#MUIA_Window_ActiveObject) -- V4 [.SG], `Object *`, 0x80427925

### SPECIAL INPUTS
  * MUIV_Window_ActiveObject_None
  * MUIV_Window_ActiveObject_Next
  * MUIV_Window_ActiveObject_Prev
  * MUIV_Window_ActiveObject_Left
  * MUIV_Window_ActiveObject_Right
  * MUIV_Window_ActiveObject_Up
  * MUIV_Window_ActiveObject_Down

### FUNCTION
Set the active object in a window as if the user would have activated it
with the tab key. The object has to be in the cycle chain for this command
to work.

### EXAMPLE
```c++
set(window, MUIA_Window_ActiveObject, okaybutton);
```

### SEE ALSO
[MUIM_Window_SetCycleChain](MUI_Window.md/#MUIM_Window_SetCycleChain)

## MUIA_Window_AltHeight
### NAME
[MUIA_Window_AltHeight](MUI_Window.md/#MUIA_Window_AltHeight) -- V4 [I.G], `LONG`, 0x8042cce3

### SPECIAL INPUTS
  * MUIV_Window_AltHeight_MinMax(p)
  * MUIV_Window_AltHeight_Visible(p)
  * MUIV_Window_AltHeight_Screen(p)
  * MUIV_Window_AltHeight_Scaled

### FUNCTION
Specify the alternate (zoomed) height of a window. If not present, the
alternate height will be the minimum height.

### SEE ALSO
[MUIA_Window_Height](MUI_Window.md/#MUIA_Window_Height), [MUIA_Window_AltWidth](MUI_Window.md/#MUIA_Window_AltWidth)

## MUIA_Window_AltLeftEdge
### NAME
[MUIA_Window_AltLeftEdge](MUI_Window.md/#MUIA_Window_AltLeftEdge) -- V4 [I.G], `LONG`, 0x80422d65

### SPECIAL INPUTS
  * MUIV_Window_AltLeftEdge_Centered
  * MUIV_Window_AltLeftEdge_Moused
  * MUIV_Window_AltLeftEdge_NoChange

### FUNCTION
Specify the alternate (zoomed) left position of a window. This defaults to
the standard left position.

### SEE ALSO
[MUIA_Window_LeftEdge](MUI_Window.md/#MUIA_Window_LeftEdge), [MUIA_Window_AltTopEdge](MUI_Window.md/#MUIA_Window_AltTopEdge)

## MUIA_Window_AltTopEdge
### NAME
[MUIA_Window_AltTopEdge](MUI_Window.md/#MUIA_Window_AltTopEdge) -- V4 [I.G], `LONG`, 0x8042e99b

### SPECIAL INPUTS
  * MUIV_Window_AltTopEdge_Centered
  * MUIV_Window_AltTopEdge_Moused
  * MUIV_Window_AltTopEdge_Delta(p)
  * MUIV_Window_AltTopEdge_NoChange

### FUNCTION
Specify the alternate (zoomed) top position of a window. This defaults to
the standard top position.

### SEE ALSO
[MUIA_Window_TopEdge](MUI_Window.md/#MUIA_Window_TopEdge), [MUIA_Window_AltLeftEdge](MUI_Window.md/#MUIA_Window_AltLeftEdge)

## MUIA_Window_AltWidth
### NAME
[MUIA_Window_AltWidth](MUI_Window.md/#MUIA_Window_AltWidth) -- V4 [I.G], `LONG`, 0x804260f4

### SPECIAL INPUTS
  * MUIV_Window_AltWidth_MinMax(p)
  * MUIV_Window_AltWidth_Visible(p)
  * MUIV_Window_AltWidth_Screen(p)
  * MUIV_Window_AltWidth_Scaled

### FUNCTION
Specify the alternate (zoomed) width of a window. If not present, the
alternate width will be the minimum width.

### SEE ALSO
[MUIA_Window_Width](MUI_Window.md/#MUIA_Window_Width), [MUIA_Window_AltHeight](MUI_Window.md/#MUIA_Window_AltHeight)

## MUIA_Window_AppWindow
### NAME
[MUIA_Window_AppWindow](MUI_Window.md/#MUIA_Window_AppWindow) -- V5 [I..], `BOOL`, 0x804280cf

### FUNCTION
Setting this attribute to TRUE will make this window an AppWindow, the user
will be able to drop icons on it. You can hear about these events by
listening to the [MUIA_AppMessage](MUI_Notify.md/#MUIA_AppMessage) attribute.

### SEE ALSO
[MUIA_AppMessage](MUI_Notify.md/#MUIA_AppMessage), [MUIA_Application_DropObject](MUI_Application.md/#MUIA_Application_DropObject)

## MUIA_Window_Backdrop
### NAME
[MUIA_Window_Backdrop](MUI_Window.md/#MUIA_Window_Backdrop) -- V4 [I..], `BOOL`, 0x8042c0bb

### FUNCTION
Make the window a backdrop window.

## MUIA_Window_Borderless
### NAME
[MUIA_Window_Borderless](MUI_Window.md/#MUIA_Window_Borderless) -- V4 [I..], `BOOL`, 0x80429b79

### FUNCTION
Make the window borderless.

## MUIA_Window_CloseGadget
### NAME
[MUIA_Window_CloseGadget](MUI_Window.md/#MUIA_Window_CloseGadget) -- V4 [I..], `BOOL`, 0x8042a110

### FUNCTION
Set this to FALSE and your window will not have a close gadget.

## MUIA_Window_CloseRequest
### NAME
[MUIA_Window_CloseRequest](MUI_Window.md/#MUIA_Window_CloseRequest) -- V4 [.SG], `BOOL`, 0x8042e86e

### FUNCTION
When the user hits a windows close gadget, the window isn't closed
immediately. Instead MUI only sets this attribute to TRUE to allow your
application to react.

Usually, you will setup a notification that automatically closes the window
when a close request appears, but you could e.g. pop up a confirmation
requester or do some other things first.

### EXAMPLE
```c++
/* automagically close a window     */
/* when the close gadget is pressed */

DoMethod(window, MUIM_Notify,
  MUIA_Window_CloseRequest, TRUE,
  window, 3,
  MUIM_Set, MUIA_Window_Open, FALSE);
```

### SEE ALSO
[MUIA_Window_Open](MUI_Window.md/#MUIA_Window_Open)

## MUIA_Window_DefaultObject
### NAME
[MUIA_Window_DefaultObject](MUI_Window.md/#MUIA_Window_DefaultObject) -- V4 [ISG], `Object *`, 0x804294d7

### FUNCTION
The default object in a window receives keyboard input as long as no other
object is active. Good candidates for default objects are e.g. lonely
listviews. Making such a listview the default object will allow the user to
control it immediately without the need of several tab strokes for
activation.

### SEE ALSO
[MUIA_Window_ActiveObject](MUI_Window.md/#MUIA_Window_ActiveObject)

## MUIA_Window_DepthGadget
### NAME
[MUIA_Window_DepthGadget](MUI_Window.md/#MUIA_Window_DepthGadget) -- V4 [I..], `BOOL`, 0x80421923

### FUNCTION
Enable or disable the depth gadget. Defaults to TRUE.

There is no good reason to use this tag.

## MUIA_Window_DisableKeys
### NAME
[MUIA_Window_DisableKeys](MUI_Window.md/#MUIA_Window_DisableKeys) -- V15 [ISG], `ULONG`, 0x80424c36

### FUNCTION
Disable internal handling of certain predefined keys. The keys to be
disabled must be supplied as a mask being build from the MUIKEY_#?
definitions.

Think twice before disabling any standard keys! It is never a good idea to
disable keys the user expects to work in any situation.

Don't forget to reset the disabled keys back to 0, otherwise the keys will
stay disabled until the window object is eventually disposed.

### EXAMPLE
```c++
/* disable handling of up and down cursor keys */
set(window, MUIA_Window_DisableKeys, (1 << MUIKEY_UP)|(1 << MUIKEY_DOWN));
/* reset any disabled keys */
set(window, MUIA_Window_DisableKeys, 0);
```

## MUIA_Window_DragBar
### NAME
[MUIA_Window_DragBar](MUI_Window.md/#MUIA_Window_DragBar) -- V4 [I..], `BOOL`, 0x8042045d

### FUNCTION
Tell MUI to give your window a dragbar.

Defaults to TRUE.

There is no good reason to disable the dragbar!

## MUIA_Window_DrawInfo
### NAME
[MUIA_Window_DrawInfo](MUI_Window.md/#MUIA_Window_DrawInfo) -- V4 [..G], `struct DrawInfo *`, 0x80423726

### FUNCTION
Get a pointer to the window's DrawInfo structure. This pointer is valid
between [MUIM_Window_Setup](MUI_Window.md/#MUIM_Window_Setup) and [MUIM_Window_Cleanup](MUI_Window.md/#MUIM_Window_Cleanup) only and is strictly
read-only.

The main purpose of this attribute is the possibility to obtain a valid
DrawInfo pointer **before** the window is actually opened, i.e. to set up
certain structures like Intuition images and menus.

### SEE ALSO
[MUIM_Window_Setup](MUI_Window.md/#MUIM_Window_Setup), [MUIM_Window_Cleanup](MUI_Window.md/#MUIM_Window_Cleanup)

## MUIA_Window_FancyDrawing
### NAME
[MUIA_Window_FancyDrawing](MUI_Window.md/#MUIA_Window_FancyDrawing) -- V8 [ISG], `BOOL`, 0x8042bd0e **(OBSOLETE)**

### FUNCTION
This attribute used to allow a more relaxed way of drawing for custom
classes. This behaviour is discouraged, the attribute is obsolete. The only
place where a class is allowed to draw something is the [MUIM_Draw](MUI_Area.md/#MUIM_Draw) method.
Setting a few flags and calling MUI_Redraw() on your object is no major
performance loss.

OLD AND OBSOLETE DOCUMENTATION
Usually, the only possible place to do some rendering is during a [MUIM_Draw](MUI_Area.md/#MUIM_Draw)
method. However, if you have a class that really requires very high
graphical output speed (e.g. a module players scope or a game class), you
can set [MUIA_Window_FancyDrawing](MUI_Window.md/#MUIA_Window_FancyDrawing) to TRUE.

This allows your class to render anywhere between [MUIM_Show](MUI_Area.md/#MUIM_Show) and [MUIM_Hide](MUI_Area.md/#MUIM_Hide),
e.g. directly after an attribute change with OM_SET or from a seperate task.

Note that your rastport etc. is only valid between [MUIM_Show](MUI_Area.md/#MUIM_Show) and [MUIM_Hide](MUI_Area.md/#MUIM_Hide).
Keep that in mind!

When drawing from a seperate task, you have to clone the RastPort and use
the copy for your rendering!

Please use this attribute sparingly. It might prevent MUI from doing nice
things with your window, e.g. building an automatic virtual group when the
screen is too small.

[MUIA_Window_FancyDrawing](MUI_Window.md/#MUIA_Window_FancyDrawing) is really only necessary for very few types of
applications. You should use the traditional way ([MUIM_Draw](MUI_Area.md/#MUIM_Draw) and
MUI_Redraw()) whenever and wherever possible!

## MUIA_Window_Height
### NAME
[MUIA_Window_Height](MUI_Window.md/#MUIA_Window_Height) -- V4 [ISG], `LONG`, 0x80425846

### SPECIAL INPUTS
  * MUIV_Window_Height_MinMax(p)
  * MUIV_Window_Height_Visible(p)
  * MUIV_Window_Height_Screen(p)
  * MUIV_Window_Height_Scaled
  * MUIV_Window_Height_Default

### FUNCTION
Specify the height of a window. Usually, you won't give a pixel value here
but instead use one of the following magic macros:

**`MUIV_Window_Height_Default`**
     calculated from objects default sizes.

**`MUIV_Window_Height_MinMax(0..100)`**
     somewhere between the minimum height (0) and the
     maximum height (100) of your window.

**`MUIV_Window_Height_Visible(1..100)`**
     percentage of the screens visible height.

**`MUIV_Window_Height_Screen(1..100)`**
     percentage of the screens total height.

**`MUIV_Window_Height_Scaled`**
     height will be adjusted so that
     width : height == minimum width : minimum height.
     Note that a window's width and height may not both be scaled.

Defaults to MUIV_Window_Height_Default.

As long as your window has a window ID ([MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)), choosing a position
is not that important. MUI will always remember a window's last position and
size and these values will simply override your settings. Positioning and
sizing should be completely under user control, a programmer doesn't need to
worry about it.

### SEE ALSO
[MUIA_Window_Width](MUI_Window.md/#MUIA_Window_Width), [MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)

## MUIA_Window_ID
### NAME
[MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID) -- V4 [ISG], `ULONG`, 0x804201bd

### FUNCTION
For most of your windows, you should define a longword as ID value. Only a
window with an ID is able to remember its size and position.

Additionally, when you use an ASCII ID (e.g. 'MAIN'), your window can be
controlled from ARexx.

Of course all windows of your application must have unique IDs.

### SEE ALSO
[MUIA_Window_LeftEdge](MUI_Window.md/#MUIA_Window_LeftEdge), [MUIM_Window_Snapshot](MUI_Window.md/#MUIM_Window_Snapshot)

## MUIA_Window_InputEvent
### NAME
[MUIA_Window_InputEvent](MUI_Window.md/#MUIA_Window_InputEvent) -- V4 [..G], `struct InputEvent *`, 0x804247d8

### FUNCTION
This attribute gets set whenever your window receives an input event. You can
react on this by creating a notification event containing a standard
commodities.library input description string.

Due to performance reasons, only IDCMP_RAWKEY, IDCMP_DISKINSERTED and
IDCMP_DISKREMOVED events are translated to a [MUIA_Window_InputEvent](MUI_Window.md/#MUIA_Window_InputEvent)
notification.

Prior to MUI 3.0, the input description string needed to remain valid as long as
the notification lasts. MUI 3.0 converts the string to a struct IX immediately,
speeding up the comparision and eliminating the need to keep the description
strings allocated.

### NOTES
Notification on [MUIA_Window_InputEvent](MUI_Window.md/#MUIA_Window_InputEvent) is inefficient. You should only use this
notification for a few keyboard events that are "general" to the window, e.g.
F-Keys for certain program actions. Keyboard control for single user interface
elements should be implemented by using subclasses and requesting rawkey input
events from there.

Details about input event descriptions can be found in the AmigaOS Documentation
Wiki:
http://wiki.amigaos.net/wiki/Commodities_Exchange_Library#Filter_Objects_and_Input_Description_Strings

### EXAMPLE
```c++
DoMethod(window, MUIM_Notify,
  MUIA_Window_InputEvent, "-repeat f1",
  txobj, 3,
  MUIM_Set, MUIA_Text_Contents, "f1 pressed/repeated");
```

## MUIA_Window_IsSubWindow
### NAME
[MUIA_Window_IsSubWindow](MUI_Window.md/#MUIA_Window_IsSubWindow) -- V4 [ISG], `BOOL`, 0x8042b5aa

### FUNCTION
Windows with this flag set to TRUE don't get disposed when the application
object is disposed. You should set this if your window belongs to an object
placed in another window (e.g. popup windows) and you want to dispose the
window object yourself during the OM_DISPOSE method of the parent object.

## MUIA_Window_LeftEdge
### NAME
[MUIA_Window_LeftEdge](MUI_Window.md/#MUIA_Window_LeftEdge) -- V4 [ISG], `LONG`, 0x80426c65

### SPECIAL INPUTS
  * MUIV_Window_LeftEdge_Centered
  * MUIV_Window_LeftEdge_Moused
  * MUIV_Window_LeftEdge_Right(n)

### FUNCTION
Specify the left edge of a window. Usually, you shouldn't define a pixel
value here but instead use one of the following macros:

**`MUIV_Window_LeftEdge_Centered`**
     window appears centered on the visible area of screen.

**`MUIV_Window_LeftEdge_Moused`**
     window appears centered under the mouse pointer.

Defaults to MUIV_Window_LeftEdge_Centered.

As long as your window has a window ID ([MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)), choosing a position
is not that important. MUI will always remember a window's last position and
size and these values will simply override your settings. Positioning and
sizing should be completely under user control, a programmer doesn't need to
worry about it.

### SEE ALSO
[MUIA_Window_TopEdge](MUI_Window.md/#MUIA_Window_TopEdge), [MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)

## MUIA_Window_Menu
### NAME
[MUIA_Window_Menu](MUI_Window.md/#MUIA_Window_Menu) -- V4 [I..], `struct NewMenu *`, 0x8042db94 **(OBSOLETE)**

### SPECIAL INPUTS
  * MUIV_Window_Menu_NoMenu

### FUNCTION
Obsolete, use [MUIA_Window_Menustrip](MUI_Window.md/#MUIA_Window_Menustrip) instead.

### SEE ALSO
[MUIA_Window_Menustrip](MUI_Window.md/#MUIA_Window_Menustrip)

## MUIA_Window_MenuAction
### NAME
[MUIA_Window_MenuAction](MUI_Window.md/#MUIA_Window_MenuAction) -- V8 [ISG], `ULONG`, 0x80427521

### FUNCTION
Whenever a menu item is selected, this attribute will be set to the
corresponding UserData field of the gadtools NewMenu structure. This allows
reacting on menu items via broadcasting.

### SEE ALSO
[MUIA_Window_Menu](MUI_Window.md/#MUIA_Window_Menu)

## MUIA_Window_Menustrip
### NAME
[MUIA_Window_Menustrip](MUI_Window.md/#MUIA_Window_Menustrip) -- V8 [ISG], `Object *`, 0x8042855e

### FUNCTION
Specify a menu strip object for this window. The object is treated as a
child of the window and will be disposed when the window is disposed.

Menustrip objects defined for a window will override an application's
Menustrip object.

[MUIA_Window_Menustrip](MUI_Window.md/#MUIA_Window_Menustrip) replaces the old and obsolete [MUIA_Window_Menu](MUI_Window.md/#MUIA_Window_Menu) tag.

Usually, you will create the menu object with MUI's builtin object library
from a gadtools NewMenu structure, but its also OK to define the menu tree
"by hand" using the Family class.

If you have a global menu for all your application's windows but you want
some windows to have no menu, use the [MUIA_Window_NoMenus](MUI_Window.md/#MUIA_Window_NoMenus) tag.

The attribute is ISG since muimaster.library 20.5855, IG with earlier
versions.

### SEE ALSO
[MUIA_Window_NoMenus](MUI_Window.md/#MUIA_Window_NoMenus)

## MUIA_Window_MouseObject
### NAME
[MUIA_Window_MouseObject](MUI_Window.md/#MUIA_Window_MouseObject) -- V10 [..G], `Object *`, 0x8042bf9b

### FUNCTION
Find out which object is currently below the mouse pointer. You can set up
notifications to react on changes or you can use IDCMP_MOUSEOBJECT in your
event handler and query the attribute in your event scheduler.

Always returns the deepest nested object.

OLD AND OBSOLETE DOCUMENTATION
When [MUIA_Window_NeedsMouseObject](MUI_Window.md/#MUIA_Window_NeedsMouseObject) is enabled for this window, you can setup
notificationns on [MUIA_Window_MouseObject](MUI_Window.md/#MUIA_Window_MouseObject) to find out on which object the
mouse pointer is located.

### SEE ALSO
[MUIA_Window_NeedsMouseObject](MUI_Window.md/#MUIA_Window_NeedsMouseObject)

## MUIA_Window_NeedsMouseObject
### NAME
[MUIA_Window_NeedsMouseObject](MUI_Window.md/#MUIA_Window_NeedsMouseObject) -- V10 [I..], `BOOL`, 0x8042372a **(OBSOLETE)**

### FUNCTION
Since MUI 4, [MUIA_Window_MouseObject](MUI_Window.md/#MUIA_Window_MouseObject) always triggers notification.

OLD AND OBSOLETE DOCUMENTATION
If you want to react on changes of the [MUIA_Window_MouseObject](MUI_Window.md/#MUIA_Window_MouseObject) attribute,
you have to set this to TRUE when creating your window.

### SEE ALSO
[MUIA_Window_MouseObject](MUI_Window.md/#MUIA_Window_MouseObject)

## MUIA_Window_NoMenus
### NAME
[MUIA_Window_NoMenus](MUI_Window.md/#MUIA_Window_NoMenus) -- V4 [ISG], `BOOL`, 0x80429df5

### FUNCTION
Temporarily disable the menu strip of a window.

### SEE ALSO
[MUIA_Window_Menu](MUI_Window.md/#MUIA_Window_Menu)

## MUIA_Window_Opacity
### NAME
[MUIA_Window_Opacity](MUI_Window.md/#MUIA_Window_Opacity) -- V20 [ISG], `LONG`, 0x80429617

### FUNCTION
Specify the opacity of a window. Transparent windows are supported by
AmigaOS4 only.

Defaults to 255 (fully opaque).

## MUIA_Window_Open
### NAME
[MUIA_Window_Open](MUI_Window.md/#MUIA_Window_Open) -- V4 [.SG], `BOOL`, 0x80428aa0

### FUNCTION
This little attribute can be used to open and close a window. When opening a
window, MUI does lots of stuff to calculate sizes and positions of all
gadgets. Minimum and maximum window sizes will be adjusted automatically.

When the minimum size of a window is too big to fit on the screen, MUI tries
to reduce font sizes and does a new calculation. You should always design
your windows to fit on a 640*200 screen with all fonts set to topaz/8.

When a window is closed (and you specified a [MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)), MUI remembers
its position and size and uses these values during the next opening.

In addition to that, MUI will also check the current activation state if a
window is going to be closed and if it was activated while closing took
place, MUI will automatically activate another window of the application
by analysing the activation priority.

After setting [MUIA_Window_Open](MUI_Window.md/#MUIA_Window_Open) to TRUE, you should test if MUI was able to
open the window by getting the attribute again. If you don't and if this was
the only window of your application, the user won't be able to do any input
and your application will seem to hang.

If a window is already open and you perform a second "[MUIA_Window_Open](MUI_Window.md/#MUIA_Window_Open),
TRUE" on it, MUI will bring that window to front and also activate it. So it
is always be a wise decision to check the current open state before setting
it to TRUE.

### EXAMPLE
```c++
ULONG open;
set(window, MUIA_Window_Open, TRUE);
get(window, MUIA_Window_Open, &open);
if(open == FALSE)
{
  MUI_Request(app,0,0,0,"Ok","Failed to open window.");
  exit(20);
}
```

### SEE ALSO
[MUIA_Window_RootObject](MUI_Window.md/#MUIA_Window_RootObject)

## MUIA_Window_PublicScreen
### NAME
[MUIA_Window_PublicScreen](MUI_Window.md/#MUIA_Window_PublicScreen) -- V6 [ISG], `STRPTR`, 0x804278e4

### FUNCTION
Force the window to appear on the public screen who's name is specified by
this attribute. This tag overrides the user preferences setting and is
overridden by [MUIA_Window_Screen](MUI_Window.md/#MUIA_Window_Screen).

Please use this tag sparely, overriding user prefs is not a good idea!

### SEE ALSO
[MUIA_Window_Screen](MUI_Window.md/#MUIA_Window_Screen)

## MUIA_Window_RefWindow
### NAME
[MUIA_Window_RefWindow](MUI_Window.md/#MUIA_Window_RefWindow) -- V4 [IS.], `Object *`, 0x804201f4

### FUNCTION
Setting [MUIA_Window_RefWindow](MUI_Window.md/#MUIA_Window_RefWindow) to another MUI window object will make the
left and top position relative to this reference window. Using
[MUIA_Window_LeftEdge](MUI_Window.md/#MUIA_Window_LeftEdge), MUIV_Window_LeftEdge_Centered or [MUIA_Window_TopEdge](MUI_Window.md/#MUIA_Window_TopEdge),
MUIV_Window_TopEdge_Centered tag, you can easily open one window within
another.

Note that if your window has an id, the window will remember its last
position and reopen there. Thus, this tag is only useful if you omit
[MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID), maybe for some small requester windows.

### SEE ALSO
[MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID), [MUIA_Window_LeftEdge](MUI_Window.md/#MUIA_Window_LeftEdge)

## MUIA_Window_RootObject
### NAME
[MUIA_Window_RootObject](MUI_Window.md/#MUIA_Window_RootObject) -- V4 [ISG], `Object *`, 0x8042cba5

### FUNCTION
This is a pointer to a MUI object and defines the contents of your window.
Usually, this root object will be of class MUIC_Group since you surely want
to have more than one gadget.

The root object is treated as child of a window and will be disposed when
the window is disposed. Note that windows can only have one child.

The root object is mandatory during window creation and trying to create a
window without a root object will definitely fail. However, the initial root
object can be replaced with a different one later. It is the developer's
task to dispose the former root object then as it is no longer a member of
the window anymore.

### NOTES
You can **only** use [MUIA_Window_RootObject](MUI_Window.md/#MUIA_Window_RootObject) in a SetAttrs() call if your
window is not open yet!

### EXAMPLE
```c++
win = WindowObject, MUIA_Window_RootObject,
  VGroup,
    Child, ...,
    Child, ...,
  End,
End;
```

### SEE ALSO
[MUIA_Window_Open](MUI_Window.md/#MUIA_Window_Open)

## MUIA_Window_Screen
### NAME
[MUIA_Window_Screen](MUI_Window.md/#MUIA_Window_Screen) -- V4 [ISG], `struct Screen *`, 0x8042df4f

### FUNCTION
You can get a pointer to the parent screen of a window by  getting this
attribute. The result will be NULL when the window is currently closed.

Specifying [MUIA_Window_Screen](MUI_Window.md/#MUIA_Window_Screen) at object creation time or with a SetAttrs()
call allows you to explicitly tell MUI on which screen the window should be
opened. You normally won't need this feature and leave the decision about
screens to the users preferences setting.

### SEE ALSO
[MUIA_Window_PublicScreen](MUI_Window.md/#MUIA_Window_PublicScreen), [MUIA_Window_Window](MUI_Window.md/#MUIA_Window_Window)

## MUIA_Window_ScreenTitle
### NAME
[MUIA_Window_ScreenTitle](MUI_Window.md/#MUIA_Window_ScreenTitle) -- V5 [ISG], `STRPTR`, 0x804234b0

### FUNCTION
This text will appear in the screens title bar when the window is active.

### SEE ALSO
[MUIA_Window_Title](MUI_Window.md/#MUIA_Window_Title)

## MUIA_Window_SizeGadget
### NAME
[MUIA_Window_SizeGadget](MUI_Window.md/#MUIA_Window_SizeGadget) -- V4 [I..], `BOOL`, 0x8042e33d

### FUNCTION
Tell MUI if you want a sizing gadget for this window. Usually you won't
need this attribute since MUI will automatically disable the sizing gadget
when your window is not sizeable because of your gadget layout.

## MUIA_Window_SizeRight
### NAME
[MUIA_Window_SizeRight](MUI_Window.md/#MUIA_Window_SizeRight) -- V4 [I..], `BOOL`, 0x80424780

### FUNCTION
When set to TRUE, the size gadget will reside in the right window border.

## MUIA_Window_Sleep
### NAME
[MUIA_Window_Sleep](MUI_Window.md/#MUIA_Window_Sleep) -- V4 [.SG], `BOOL`, 0x8042e7db

### FUNCTION
This attribute can be used to put a window to sleep. The window gets
disabled and a busy pointer appears.

The attribute contains a nesting count, if you tell your window to sleep
twice, you will have to tell it to wake up twice as well.

A sleeping window cannot be resized.

### NOTES
Only opened windows can be put to sleep. However, currently closed windows
can be taken out of sleep nevertheless.

### SEE ALSO
[MUIA_Application_Sleep](MUI_Application.md/#MUIA_Application_Sleep)

## MUIA_Window_Title
### NAME
[MUIA_Window_Title](MUI_Window.md/#MUIA_Window_Title) -- V4 [ISG], `STRPTR`, 0x8042ad3d

### FUNCTION
Specify the title of a window.

### SEE ALSO
[MUIA_Window_ScreenTitle](MUI_Window.md/#MUIA_Window_ScreenTitle)

## MUIA_Window_TopEdge
### NAME
[MUIA_Window_TopEdge](MUI_Window.md/#MUIA_Window_TopEdge) -- V4 [ISG], `LONG`, 0x80427c66

### SPECIAL INPUTS
  * MUIV_Window_TopEdge_Centered
  * MUIV_Window_TopEdge_Moused
  * MUIV_Window_TopEdge_Delta(p)
  * MUIV_Window_TopEdge_Bottom(n)

### FUNCTION
Specify the top edge of a window. Usually, you shouldn't define a pixel
value here but instead use one of the following macros:

**`MUIV_Window_TopEdge_Centered`**
     window appears centered on the visible area of screen.

**`MUIV_Window_TopEdge_Moused`**
     window appears centered under the mouse pointer.

**`MUIV_Window_TopEdge_Delta(p)`**
     window appears p pixels below the screen's title bar.

Defaults to MUIV_Window_TopEdge_Centered.

As long as your window has a window ID ([MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)), choosing a position
is not that important. MUI will always remember a window's last position and
size and these values will simply override your settings. Positioning and
sizing should be completely under user control, a programmer doesn't need to
worry about it.

### SEE ALSO
[MUIA_Window_LeftEdge](MUI_Window.md/#MUIA_Window_LeftEdge), [MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)

## MUIA_Window_UseBottomBorderScroller
### NAME
[MUIA_Window_UseBottomBorderScroller](MUI_Window.md/#MUIA_Window_UseBottomBorderScroller) -- V13 [ISG], `BOOL`, 0x80424e79

### FUNCTION
If set to TRUE, the window will feature a scrollbar in its bottom border.
You must set this for the window object if any children are going to use
this window border scroller, e.g. prop gadgets with the
[MUIA_Prop_UseWinBorder](MUI_Prop.md/#MUIA_Prop_UseWinBorder) attribute.

### NOTES
Obviously, scroll gadgets in window borders won't look good with borderless
or non-resizable windows.

### SEE ALSO
[MUIA_Window_UseLeftBorderScroller](MUI_Window.md/#MUIA_Window_UseLeftBorderScroller), [MUIA_Window_UseRightBorderScroller](MUI_Window.md/#MUIA_Window_UseRightBorderScroller),
[MUIA_Prop_UseWinBorder](MUI_Prop.md/#MUIA_Prop_UseWinBorder), [MUIA_Scrollgroup_UseWinBorder](MUI_Scrollgroup.md/#MUIA_Scrollgroup_UseWinBorder)

## MUIA_Window_UseLeftBorderScroller
### NAME
[MUIA_Window_UseLeftBorderScroller](MUI_Window.md/#MUIA_Window_UseLeftBorderScroller) -- V13 [ISG], `BOOL`, 0x8042433e

### FUNCTION
If set to TRUE, the window will feature a scrollbar in its left border. You
must set this for the window object if any children are going to use this
window border scroller, e.g. prop gadgets with the [MUIA_Prop_UseWinBorder](MUI_Prop.md/#MUIA_Prop_UseWinBorder)
attribute.

### NOTES
Obviously, scroll gadgets in window borders won't look good with borderless
or non-resizable windows.

### SEE ALSO
[MUIA_Window_UseBottomBorderScroller](MUI_Window.md/#MUIA_Window_UseBottomBorderScroller), [MUIA_Window_UseRightBorderScroller](MUI_Window.md/#MUIA_Window_UseRightBorderScroller),
[MUIA_Prop_UseWinBorder](MUI_Prop.md/#MUIA_Prop_UseWinBorder), [MUIA_Scrollgroup_UseWinBorder](MUI_Scrollgroup.md/#MUIA_Scrollgroup_UseWinBorder)

## MUIA_Window_UseRightBorderScroller
### NAME
[MUIA_Window_UseRightBorderScroller](MUI_Window.md/#MUIA_Window_UseRightBorderScroller) -- V13 [ISG], `BOOL`, 0x8042c05e

### FUNCTION
If set to TRUE, the window will feature a scrollbar in its right border. You
must set this for the window object if any children are going to use this
window border scroller, e.g. prop gadgets with the [MUIA_Prop_UseWinBorder](MUI_Prop.md/#MUIA_Prop_UseWinBorder)
attribute.

### NOTES
Obviously, scroll gadgets in window borders won't look good with borderless
or non-resizable windows.

### SEE ALSO
[MUIA_Window_UseLeftBorderScroller](MUI_Window.md/#MUIA_Window_UseLeftBorderScroller), [MUIA_Window_UseBottomBorderScroller](MUI_Window.md/#MUIA_Window_UseBottomBorderScroller),
[MUIA_Prop_UseWinBorder](MUI_Prop.md/#MUIA_Prop_UseWinBorder), [MUIA_Scrollgroup_UseWinBorder](MUI_Scrollgroup.md/#MUIA_Scrollgroup_UseWinBorder)

## MUIA_Window_Width
### NAME
[MUIA_Window_Width](MUI_Window.md/#MUIA_Window_Width) -- V4 [ISG], `LONG`, 0x8042dcae

### SPECIAL INPUTS
  * MUIV_Window_Width_MinMax(p)
  * MUIV_Window_Width_Visible(p)
  * MUIV_Window_Width_Screen(p)
  * MUIV_Window_Width_Scaled
  * MUIV_Window_Width_Default

### FUNCTION
Specify the width of a window. Usually, you won't give a pixel value here
but instead use one of the following magic macros:

**`MUIV_Window_Width_Default`**
     calculated from objects default sizes.

**`MUIV_Window_Width_MinMax(0..100)`**
     somewhere between the minimum width (0) and the maximum width (100) of
     your window.

**`MUIV_Window_Width_Visible(1..100)`**
     percentage of the screens visible width.

**`MUIV_Window_Width_Screen(1..100)`**
     percentage of the screens total width.

**`MUIV_Window_Width_Scaled`**
     width will be adjusted so that
     width : height == minimum width : minimum height.
     Note that a window's width and height may not both be scaled.

Defaults to MUIV_Window_Width_Default.

As long as your window has a window ID ([MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)), choosing a position
is not that important. MUI will always remember a window's last position and
size and these values will simply override your settings. Positioning and
sizing should be completely under user control, a programmer doesn't need to
worry about it.

### SEE ALSO
[MUIA_Window_Height](MUI_Window.md/#MUIA_Window_Height), [MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)

## MUIA_Window_Window
### NAME
[MUIA_Window_Window](MUI_Window.md/#MUIA_Window_Window) -- V4 [..G], `struct Window *`, 0x80426a42

### FUNCTION
When your window is open, you can obtain a pointer  to the intuition Window
structure with this tag and use it e.g. in an asl.library requester call.

Since the user can close your window any time (e.g. iconification), you must
be prepared to receive a NULL pointer as result.

### SEE ALSO
[MUIA_Window_Screen](MUI_Window.md/#MUIA_Window_Screen)

## MUIM_Window_AddEventHandler
### NAME
[MUIM_Window_AddEventHandler](MUI_Window.md/#MUIM_Window_AddEventHandler) -- V16, 0x804203b7

### SYNOPSIS
`DoMethod(obj, MUIM_Window_AddEventHandler, struct MUI_EventHandlerNode *ehnode);`

### FUNCTION
Event handlers introduced in muimaster.library V16 offer a new way for
custom classes to receive user input. They work a little like the previously
introduced input handlers ([MUIM_Application_AddInputHandler](MUI_Application.md/#MUIM_Application_AddInputHandler)). You fill out a
struct MUI_EventHandlerNode (preferably located somewhere in the instance
data of your custom class) with the type of events you wish to receive and
then call [MUIM_Window_AddEventHandler](MUI_Window.md/#MUIM_Window_AddEventHandler) to add your node to a windows event
handler queue.

Whenever an input event arrives, MUIs window class iterates through the list
of event handlers. The class of the input event is matched against the event
handlers class field and in case of a match, the method [MUIM_HandleEvent](MUI_Area.md/#MUIM_HandleEvent) is
invoked on the specified object.

Each event handler may decide to "eat" the input event by returning
MUI_EventHandlerRC_Eat instead of zero. This means Window class will abort
iterating the handler queue after calling this handler.

MUI follows certain priority rules when iterating through the handler queue
of a window. If there are handler entries for the active object
([MUIA_Window_ActiveObject](MUI_Window.md/#MUIA_Window_ActiveObject)) or for the default object
([MUIA_Window_DefaultObject](MUI_Window.md/#MUIA_Window_DefaultObject)), their nodes are checked before all other nodes.
Active objects are checked before default objects. If there was no active
and no default object or if none of them ate the event, the rest of the
handler queue is checked according to their ehn_Priority field.

A good place to add/remove event handlers is the [MUIM_Setup](MUI_Area.md/#MUIM_Setup)/[MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup)
method pair of your custom class.

If you wish to change certain fields (e.g. ehn_Events) in an active handler
(one that is currently added to a window), you must deactivate (remove) the
handler first, make your changes and then add it again. Do not change fields
of an active handler without removing it first!

### INPUTS
**`struct MUI_EventHandlerNode *ehnode`**
      pointer to an initialized MUI_EventHandler structure.

The MUI_EventHandlerNode structure consists of these fields:
**`ehn_Priority`**
     event handlers are inserted according to their priority. 0 is
     fine in almost all cases.

**`ehn_Flags`**
     a combination of these public flags:
       * MUI_EHF_GUIMODE: the handler will be called only if the
         object is neither disabled nor invsibile.
     All other flags are either private or read-only.

**`ehn_Events`**
     exclusive OR of all IDCMP_* flags you want this handler to
     react on.

**`ehn_Object`**
     insert a pointer to yourself here.

**`ehn_Class`**
     if you point this to your class, MUI will invoke
     [MUIM_HandleEvent](MUI_Area.md/#MUIM_HandleEvent) with CoerceMethod(ehn_Class,...) instead as
     with DoMethod(obj,...). This will bypass any subclasses you
     might have and directly hand the input event to your
     dispatcher. If you don't set ehn_Class, [MUIM_HandleEvent](MUI_Area.md/#MUIM_HandleEvent) is
     sent like any other method to the true class of your object.
     Since every class should add a handler itself if it needs
     some input, [MUIM_HandleEvent](MUI_Area.md/#MUIM_HandleEvent) methods are different from other
     MUI methods which usually travel from class to class in an
     object's class tree. [MUIM_HandleEvent](MUI_Area.md/#MUIM_HandleEvent) is more treated like a
     hook function instead of a method: in almost all cases you
     will want it to be passed directly to a specific class
     dispatcher (by setting ehn_Class). Also, this dispatcher will
     usually not pass the method to its super class but instead
     return directly.

### RESULT
[MUIM_Window_AddEventHandler](MUI_Window.md/#MUIM_Window_AddEventHandler) cannot fail, the result value of the method is
currently undefined.

### NOTES
Event handlers are more flexible and more efficient than the pre-V16
functions MUI_RequestIDCMP() and MUI_RejectIDCMP(). Also, event handlers
don't suffer from problems that arise if more than one class of an object
calls MUI_RequestIDCMP(). Though the old functions will remain working for
compatibility reasons, it's suggested that only event handlers are used in
new code.

You must match each [MUIM_Window_AddEventHandler](MUI_Window.md/#MUIM_Window_AddEventHandler) with exactly one
[MUIM_Window_RemEventHandler](MUI_Window.md/#MUIM_Window_RemEventHandler) method.

### EXAMPLE
[MUIM_Setup](MUI_Area.md/#MUIM_Setup):
```c++
data->ehnode.ehn_Object = obj;
data->ehnode.ehn_Class  = cl;
data->ehnode.ehn_Events = IDCMP_MOUSEBUTTONS;
DoMethod(_win(obj), MUIM_Window_AddEventHandler, &data->ehnode);
```

[MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup):
```c++
DoMethod(_win(obj), MUIM_Window_RemEventHandler, &data->ehnode);
```

Changing the trigger events of an active handler:
```c++
DoMethod(_win(obj), MUIM_Window_RemEventHandler, &data->ehnode);
data->ehnode.ehn_Events |= IDCMP_MOUSEMOVE;
DoMethod(_win(obj), MUIM_Window_AddEventHandler, &data->ehnode);
```

More examples can be found in the MUI demo source codes that deal with
custom classes.

### SEE ALSO
[MUIM_Window_RemEventHandler](MUI_Window.md/#MUIM_Window_RemEventHandler), [MUIM_HandleEvent](MUI_Area.md/#MUIM_HandleEvent)

## MUIM_Window_Cleanup
### NAME
[MUIM_Window_Cleanup](MUI_Window.md/#MUIM_Window_Cleanup) -- V18, 0x8042ab26

### SYNOPSIS
`DoMethod(obj, MUIM_Window_Cleanup);`

### FUNCTION
This method is the analog cleanup method for window objects as [MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup)
is for all other kinds of objects. Perform all the work to clean up things
that have been set up during [MUIM_Window_Setup](MUI_Window.md/#MUIM_Window_Setup).

### SEE ALSO
[MUIM_Window_Setup](MUI_Window.md/#MUIM_Window_Setup)

## MUIM_Window_GetMenuCheck
### NAME
[MUIM_Window_GetMenuCheck](MUI_Window.md/#MUIM_Window_GetMenuCheck) -- V4, 0x80420414 **(OBSOLETE)**

### SYNOPSIS
`DoMethod(obj, MUIM_Window_GetMenuCheck, ULONG MenuID);`

### FUNCTION
Ask whether a checkmark menu item has its checkmark set or cleared.

### INPUTS
**`ULONG MenuID`**
     the value you wrote into the UserData field of struct NewMenu.

### SEE ALSO
[MUIM_Window_SetMenuCheck](MUI_Window.md/#MUIM_Window_SetMenuCheck), [MUIA_Window_Menu](MUI_Window.md/#MUIA_Window_Menu)

## MUIM_Window_GetMenuState
### NAME
[MUIM_Window_GetMenuState](MUI_Window.md/#MUIM_Window_GetMenuState) -- V4, 0x80420d2f **(OBSOLETE)**

### SYNOPSIS
`DoMethod(obj, MUIM_Window_GetMenuState, ULONG MenuID);`

### FUNCTION
Ask whether a menu item is enabled or disabled.

### INPUTS
**`ULONG MenuID`**
     the value you wrote into the UserData field of struct NewMenu.

### SEE ALSO
[MUIM_Window_SetMenuState](MUI_Window.md/#MUIM_Window_SetMenuState), [MUIA_Window_Menu](MUI_Window.md/#MUIA_Window_Menu)

## MUIM_Window_RemEventHandler
### NAME
[MUIM_Window_RemEventHandler](MUI_Window.md/#MUIM_Window_RemEventHandler) -- V16, 0x8042679e

### SYNOPSIS
`DoMethod(obj, MUIM_Window_RemEventHandler, struct MUI_EventHandlerNode *ehnode);`

### FUNCTION
Remove an event handler.

### INPUTS
**`struct MUI_EventHandlerNode *ehnode`**
     event handler node structure you passed to [MUIM_Window_AddEventHandler](MUI_Window.md/#MUIM_Window_AddEventHandler)
     previously.

### RESULT
[MUIM_Window_RemEventHandler](MUI_Window.md/#MUIM_Window_RemEventHandler) cannot fail, the result value of the method is
currently undefined.

### NOTES
Every call to [MUIM_Window_AddEventHandler](MUI_Window.md/#MUIM_Window_AddEventHandler) must be matched by exactly one
call to [MUIM_Window_RemEventHandler](MUI_Window.md/#MUIM_Window_RemEventHandler).

### SEE ALSO
[MUIM_Window_RemEventHandler](MUI_Window.md/#MUIM_Window_RemEventHandler), [MUIM_HandleEvent](MUI_Area.md/#MUIM_HandleEvent)

## MUIM_Window_ScreenToBack
### NAME
[MUIM_Window_ScreenToBack](MUI_Window.md/#MUIM_Window_ScreenToBack) -- V4, 0x8042913d

### SYNOPSIS
`DoMethod(obj, MUIM_Window_ScreenToBack);`

### FUNCTION
Put the window's screen to back. This command is only valid when the window
is opened.

### SEE ALSO
[MUIM_Window_ScreenToFront](MUI_Window.md/#MUIM_Window_ScreenToFront), [MUIM_Window_ToBack](MUI_Window.md/#MUIM_Window_ToBack), [MUIM_Window_ToFront](MUI_Window.md/#MUIM_Window_ToFront)

## MUIM_Window_ScreenToFront
### NAME
[MUIM_Window_ScreenToFront](MUI_Window.md/#MUIM_Window_ScreenToFront) -- V4, 0x804227a4

### SYNOPSIS
`DoMethod(obj, MUIM_Window_ScreenToFront);`

### FUNCTION
Put the window's screen to font. This command is only valid when the window
is opened.

### SEE ALSO
[MUIM_Window_ScreenToBack](MUI_Window.md/#MUIM_Window_ScreenToBack), [MUIM_Window_ToBack](MUI_Window.md/#MUIM_Window_ToBack), [MUIM_Window_ToFront](MUI_Window.md/#MUIM_Window_ToFront)

## MUIM_Window_SetCycleChain
### NAME
[MUIM_Window_SetCycleChain](MUI_Window.md/#MUIM_Window_SetCycleChain) -- V4, 0x80426510 **(OBSOLETE)**

### SYNOPSIS
`DoMethod(obj, MUIM_Window_SetCycleChain, Object *obj[1]);`

### FUNCTION
Set the cycle chain for a window. To make MUI's keyboard control work, you
need to setup a chain of objects that should be activatable with the tab
key. This can be any objects you wish, MUI supports complete keyboard
handling even for sliders or listviews.

If you forget to set a cycle chain because you are a mouse-man, you
certainly will annoy some users of your application!

### INPUTS
**`Object *obj1, ...`**
     one or more objects, terminated with a NULL.

### EXAMPLE
```c++
DoMethod(window, MUIM_Window_SetCycleChain, str1, str2, slide1, list, radio, cycle1, cycle2, NULL);
```

### SEE ALSO
[MUIA_Window_ActiveObject](MUI_Window.md/#MUIA_Window_ActiveObject), [MUIA_CycleChain](MUI_Area.md/#MUIA_CycleChain)

## MUIM_Window_SetMenuCheck
### NAME
[MUIM_Window_SetMenuCheck](MUI_Window.md/#MUIM_Window_SetMenuCheck) -- V4, 0x80422243 **(OBSOLETE)**

### SYNOPSIS
`DoMethod(obj, MUIM_Window_SetMenuCheck, ULONG MenuID, LONG stat);`

### FUNCTION
Set or clear the checkmark of a menu item.

### INPUTS
**`ULONG MenuID`**
     the value you wrote into the UserData field of struct NewMenu.

**`LONG stat`**
     TRUE to set checkmark, FALSE to clear

### SEE ALSO
[MUIM_Window_GetMenuCheck](MUI_Window.md/#MUIM_Window_GetMenuCheck), [MUIA_Window_Menu](MUI_Window.md/#MUIA_Window_Menu)

## MUIM_Window_SetMenuState
### NAME
[MUIM_Window_SetMenuState](MUI_Window.md/#MUIM_Window_SetMenuState) -- V4, 0x80422b5e **(OBSOLETE)**

### SYNOPSIS
`DoMethod(obj, MUIM_Window_SetMenuState, ULONG MenuID, LONG stat);`

### FUNCTION
Enable or disable a menu item.

### INPUTS
**`ULONG MenuID`**
     the value you wrote into the UserData field of struct NewMenu.

**`LONG stat`**
     TRUE to enable item, FALSE to disable.

### SEE ALSO
[MUIM_Window_GetMenuState](MUI_Window.md/#MUIM_Window_GetMenuState), [MUIA_Window_Menu](MUI_Window.md/#MUIA_Window_Menu)

## MUIM_Window_Setup
### NAME
[MUIM_Window_Setup](MUI_Window.md/#MUIM_Window_Setup) -- V18, 0x8042c34c

### SYNOPSIS
`DoMethod(obj, MUIM_Window_Setup);`

### FUNCTION
This method is the analog setup method for window objects as [MUIM_Setup](MUI_Area.md/#MUIM_Setup) is
for all other kinds of objects. If you need to initialize anything ahead of
layouting and opening the window you can override this method.

Note: The window itself is neither opened yet, nor is any window dimension
calculated yet.

### SEE ALSO
[MUIM_Window_Cleanup](MUI_Window.md/#MUIM_Window_Cleanup)

## MUIM_Window_Snapshot
### NAME
[MUIM_Window_Snapshot](MUI_Window.md/#MUIM_Window_Snapshot) -- V11, 0x8042945e

### SYNOPSIS
`DoMethod(obj, MUIM_Window_Snapshot, LONG flags);`

### FUNCTION
[MUIM_Window_Snapshot](MUI_Window.md/#MUIM_Window_Snapshot) is the programmer's interface to MUI's window position
remembering facility.

### NOTES
Snapshotting a window is only possible if it has a non-NULL [MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID).

### INPUTS
**`LONG flags`**
      * use 0 to unsnapshot the window.
        This is equal to the user doubleclicking on the window's snapshot
        gadget.
      * use 1 to snapshot the window.
        This is equal to the user clicking on the window's snapshot gadget.

### SEE ALSO
[MUIA_Window_ID](MUI_Window.md/#MUIA_Window_ID)

## MUIM_Window_ToBack
### NAME
[MUIM_Window_ToBack](MUI_Window.md/#MUIM_Window_ToBack) -- V4, 0x8042152e

### SYNOPSIS
`DoMethod(obj, MUIM_Window_ToBack);`

### FUNCTION
Put the window to back. When the window is not currently open, this command
does simply nothing.

### SEE ALSO
[MUIM_Window_ToFront](MUI_Window.md/#MUIM_Window_ToFront), [MUIM_Window_ScreenToBack](MUI_Window.md/#MUIM_Window_ScreenToBack), [MUIM_Window_ScreenToFront](MUI_Window.md/#MUIM_Window_ScreenToFront)

## MUIM_Window_ToFront
### NAME
[MUIM_Window_ToFront](MUI_Window.md/#MUIM_Window_ToFront) -- V4, 0x8042554f

### SYNOPSIS
`DoMethod(obj, MUIM_Window_ToFront);`

### FUNCTION
Put the window to front. When the window is not currently open, this command
does simply nothing.

### SEE ALSO
[MUIM_Window_ToBack](MUI_Window.md/#MUIM_Window_ToBack), [MUIM_Window_ScreenToBack](MUI_Window.md/#MUIM_Window_ScreenToBack), [MUIM_Window_ScreenToFront](MUI_Window.md/#MUIM_Window_ScreenToFront)

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
