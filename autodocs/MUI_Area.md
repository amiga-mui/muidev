# Area.mui
## Super class
[Notify.mui](MUI_Notify.md)
## Inherited by
* [Balance.mui](MUI_Balance.md)
* [Bitmap.mui](MUI_Bitmap.md)
* [Colorfield.mui](MUI_Colorfield.md)
* [Dtpic.mui](MUI_Dtpic.md)
* [Gadget.mui](MUI_Gadget.md)
* [Gauge.mui](MUI_Gauge.md)
* [Group.mui](MUI_Group.md)
* [Image.mui](MUI_Image.md)
* [List.mui](MUI_List.md)
* [Numeric.mui](MUI_Numeric.md)
* [Pendisplay.mui](MUI_Pendisplay.md)
* [Pixmap.mui](MUI_Pixmap.md)
* [Rectangle.mui](MUI_Rectangle.md)
* [Scale.mui](MUI_Scale.md)
* [String.mui](MUI_String.md)
* [Text.mui](MUI_Text.md)
## Background
Area class is a super class for every other MUI class except windows and
applications. It holds information about an object's current position, size
and weight and manages frames, fonts and backgrounds.

Additionally, Area class handles the user input. By setting an object's
[MUIA_InputMode](MUI_Area.md/#MUIA_InputMode), you can make it behave like a button or like a toggle
gadget. That's why MUI doesn't offer an extra button class. A button is
simply a text object with a raised frame and a relverify input mode. Since
especially group class is a subclass of Area class, you can create rather
complex buttons consisting of many other display elements.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Background](MUI_Area.md/#MUIA_Background)|V4|IS.|`LONG`
[MUIA_BottomEdge](MUI_Area.md/#MUIA_BottomEdge)|V4|..G|`LONG`
[MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu)|V11|ISG|`Object *`
[MUIA_ContextMenuHook](MUI_Area.md/#MUIA_ContextMenuHook)|V20|ISG|`struct Hook *`
[MUIA_ContextMenuTrigger](MUI_Area.md/#MUIA_ContextMenuTrigger)|V11|..G|`Object *`
[MUIA_ControlChar](MUI_Area.md/#MUIA_ControlChar)|V4|ISG|`char`
[MUIA_CycleChain](MUI_Area.md/#MUIA_CycleChain)|V11|ISG|`LONG`
[MUIA_Disabled](MUI_Area.md/#MUIA_Disabled)|V4|ISG|`BOOL`
[MUIA_DoubleBuffer](MUI_Area.md/#MUIA_DoubleBuffer)|V20|ISG|`BOOL`
[MUIA_DoubleClick](MUI_Area.md/#MUIA_DoubleClick)|V20|..G|`BOOL`
[MUIA_Draggable](MUI_Area.md/#MUIA_Draggable)|V11|ISG|`BOOL`
[MUIA_Dropable](MUI_Area.md/#MUIA_Dropable)|V11|ISG|`BOOL`
[MUIA_ExportID](MUI_Area.md/#MUIA_ExportID)|V4|ISG|`ULONG` **(OBSOLETE)**
[MUIA_FillArea](MUI_Area.md/#MUIA_FillArea)|V4|IS.|`BOOL`
[MUIA_FixHeight](MUI_Area.md/#MUIA_FixHeight)|V4|I..|`LONG`
[MUIA_FixHeightTxt](MUI_Area.md/#MUIA_FixHeightTxt)|V4|I..|`STRPTR`
[MUIA_FixWidth](MUI_Area.md/#MUIA_FixWidth)|V4|I..|`LONG`
[MUIA_FixWidthTxt](MUI_Area.md/#MUIA_FixWidthTxt)|V4|I..|`STRPTR`
[MUIA_Floating](MUI_Area.md/#MUIA_Floating)|V20|ISG|`BOOL`
[MUIA_Font](MUI_Area.md/#MUIA_Font)|V4|ISG|`struct TextFont *`
[MUIA_Frame](MUI_Area.md/#MUIA_Frame)|V4|I..|`LONG`
[MUIA_FrameDynamic](MUI_Area.md/#MUIA_FrameDynamic)|V20|ISG|`BOOL`
[MUIA_FramePhantomHoriz](MUI_Area.md/#MUIA_FramePhantomHoriz)|V4|I..|`BOOL`
[MUIA_FrameTitle](MUI_Area.md/#MUIA_FrameTitle)|V4|ISG|`STRPTR`
[MUIA_FrameVisible](MUI_Area.md/#MUIA_FrameVisible)|V20|ISG|`BOOL`
[MUIA_Height](MUI_Area.md/#MUIA_Height)|V4|..G|`LONG`
[MUIA_HorizDisappear](MUI_Area.md/#MUIA_HorizDisappear)|V11|ISG|`LONG`
[MUIA_HorizWeight](MUI_Area.md/#MUIA_HorizWeight)|V4|ISG|`WORD`
[MUIA_InnerBottom](MUI_Area.md/#MUIA_InnerBottom)|V4|I.G|`LONG`
[MUIA_InnerLeft](MUI_Area.md/#MUIA_InnerLeft)|V4|I.G|`LONG`
[MUIA_InnerRight](MUI_Area.md/#MUIA_InnerRight)|V4|I.G|`LONG`
[MUIA_InnerTop](MUI_Area.md/#MUIA_InnerTop)|V4|I.G|`LONG`
[MUIA_InputMode](MUI_Area.md/#MUIA_InputMode)|V4|I..|`LONG`
[MUIA_KnowsDisabled](MUI_Area.md/#MUIA_KnowsDisabled)|V20|ISG|`BOOL`
[MUIA_LeftEdge](MUI_Area.md/#MUIA_LeftEdge)|V4|..G|`LONG`
[MUIA_MaxHeight](MUI_Area.md/#MUIA_MaxHeight)|V11|I..|`LONG`
[MUIA_MaxWidth](MUI_Area.md/#MUIA_MaxWidth)|V11|I..|`LONG`
[MUIA_MinHeight](MUI_Area.md/#MUIA_MinHeight)|V20|I..|`LONG`
[MUIA_MinWidth](MUI_Area.md/#MUIA_MinWidth)|V20|I..|`LONG`
[MUIA_PointerType](MUI_Area.md/#MUIA_PointerType)|V20|ISG|`LONG`
[MUIA_Pressed](MUI_Area.md/#MUIA_Pressed)|V4|..G|`BOOL`
[MUIA_RightEdge](MUI_Area.md/#MUIA_RightEdge)|V4|..G|`LONG`
[MUIA_Selected](MUI_Area.md/#MUIA_Selected)|V4|ISG|`BOOL`
[MUIA_ShortHelp](MUI_Area.md/#MUIA_ShortHelp)|V11|ISG|`STRPTR`
[MUIA_ShowMe](MUI_Area.md/#MUIA_ShowMe)|V4|ISG|`BOOL`
[MUIA_ShowSelState](MUI_Area.md/#MUIA_ShowSelState)|V4|I..|`BOOL`
[MUIA_TextColor](MUI_Area.md/#MUIA_TextColor)|V22|..G|`ULONG`
[MUIA_Timer](MUI_Area.md/#MUIA_Timer)|V4|..G|`LONG`
[MUIA_TopEdge](MUI_Area.md/#MUIA_TopEdge)|V4|..G|`LONG`
[MUIA_VertDisappear](MUI_Area.md/#MUIA_VertDisappear)|V11|ISG|`LONG`
[MUIA_VertWeight](MUI_Area.md/#MUIA_VertWeight)|V4|ISG|`WORD`
[MUIA_Weight](MUI_Area.md/#MUIA_Weight)|V4|I..|`WORD`
[MUIA_Width](MUI_Area.md/#MUIA_Width)|V4|..G|`LONG`
[MUIA_Window](MUI_Area.md/#MUIA_Window)|V4|..G|`struct Window *`
[MUIA_WindowObject](MUI_Area.md/#MUIA_WindowObject)|V4|..G|`Object *`

## Methods
Method|Version
------|-------
[MUIM_AskMinMax](MUI_Area.md/#MUIM_AskMinMax)|V4
[MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup)|V4
[MUIM_ContextMenuAdd](MUI_Area.md/#MUIM_ContextMenuAdd)|V20
[MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild)|V11
[MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice)|V11
[MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble)|V18
[MUIM_CreateDragImage](MUI_Area.md/#MUIM_CreateDragImage)|V18
[MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp)|V11
[MUIM_DeleteBubble](MUI_Area.md/#MUIM_DeleteBubble)|V18
[MUIM_DeleteDragImage](MUI_Area.md/#MUIM_DeleteDragImage)|V18
[MUIM_DeleteShortHelp](MUI_Area.md/#MUIM_DeleteShortHelp)|V11
[MUIM_DoDrag](MUI_Area.md/#MUIM_DoDrag)|V20
[MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin)|V11
[MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop)|V11
[MUIM_DragEvent](MUI_Area.md/#MUIM_DragEvent)|V20
[MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish)|V11
[MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery)|V11
[MUIM_DragReport](MUI_Area.md/#MUIM_DragReport)|V11
[MUIM_Draw](MUI_Area.md/#MUIM_Draw)|V4
[MUIM_DrawBackground](MUI_Area.md/#MUIM_DrawBackground)|V11
[MUIM_DrawBackgroundParent](MUI_Area.md/#MUIM_DrawBackgroundParent)|V20
[MUIM_GoActive](MUI_Area.md/#MUIM_GoActive)|V8
[MUIM_GoInactive](MUI_Area.md/#MUIM_GoInactive)|V8
[MUIM_HandleEvent](MUI_Area.md/#MUIM_HandleEvent)|V16
[MUIM_HandleInput](MUI_Area.md/#MUIM_HandleInput)|V4
[MUIM_Hide](MUI_Area.md/#MUIM_Hide)|V4
[MUIM_Layout](MUI_Area.md/#MUIM_Layout)|V4
[MUIM_Relayout](MUI_Area.md/#MUIM_Relayout)|V22
[MUIM_Setup](MUI_Area.md/#MUIM_Setup)|V4
[MUIM_Show](MUI_Area.md/#MUIM_Show)|V4
[MUIM_Text](MUI_Area.md/#MUIM_Text)|V20
[MUIM_TextDim](MUI_Area.md/#MUIM_TextDim)|V20
[MUIM_UpdateConfig](MUI_Area.md/#MUIM_UpdateConfig)|V20
[MUIM_WhichPointerType](MUI_Area.md/#MUIM_WhichPointerType)|V20

## MUIA_Background
### NAME
[MUIA_Background](MUI_Area.md/#MUIA_Background) -- V4 [IS.], `LONG`, 0x8042545b

### FUNCTION
Adjust the background for an object.

Every MUI object has its own background setting. The background is displayed
"behind" the actual object contents, e.g. behind a the text of a text object
or behind the image of an image object.

This attribute takes the same values as [MUIA_Image_Spec](MUI_Image.md/#MUIA_Image_Spec), please refer to
Autodocs of image class for a complete description.

An object without a specific background setting will inherit the pattern
from its parent group (1). The default background for a window and many
other background patterns are adjustable with the preferences program.

Only a few MUII_xxxxxxx tags make sense as background.
Important are:
**`MUII_ButtonBack`**
     You have to set this when you create a button gadget. Thus, your button
     will be displayed in the users preferred style.

**`MUII_TextBack`**
     Set this when you create a text object with a TextFrame, e.g. some kind
     of status line. Do **NOT** use MUII_TextBack for simple text without frame
     (e.g. gadget labels).

**`MUII_BACKGROUND`**
     MUII_SHADOW::
     MUII_SHINE::
     MUII_FILL::
     MUII_SHADOWBACK::
     MUII_SHADOWFILL::
     MUII_SHADOWSHINE::
     MUII_FILLBACK::
     MUII_FILLSHINE::
     MUII_SHINEBACK::
     MUII_SHINEBACK2::
     One of MUI's predefined pattern. These are not configurable by the user
     and will always look the same.

Note: It is **important** that you test your programs with a fancy pattern
configuration. With the default setting you won't notice any errors in
your backgrounds.

(1) In case the object had a background already then the background
inheritance can be activated by setting [MUIA_Background](MUI_Area.md/#MUIA_Background) to an empty
string "" (as opposed to NULL which will make the object use the
window's backfill as background in any case).

### SEE ALSO
[MUIA_Image_Spec](MUI_Image.md/#MUIA_Image_Spec)

## MUIA_BottomEdge
### NAME
[MUIA_BottomEdge](MUI_Area.md/#MUIA_BottomEdge) -- V4 [..G], `LONG`, 0x8042e552

### FUNCTION
You can use this to read the current position and dimension of an object, if
you e.g. need it to pop up some requester below.

Of course, this attribute is only valid when the parent window of the object
is currently open.

### SEE ALSO
[MUIA_TopEdge](MUI_Area.md/#MUIA_TopEdge), [MUIA_Width](MUI_Area.md/#MUIA_Width), [MUIA_Height](MUI_Area.md/#MUIA_Height), [MUIA_RightEdge](MUI_Area.md/#MUIA_RightEdge), [MUIA_LeftEdge](MUI_Area.md/#MUIA_LeftEdge)

## MUIA_ContextMenu
### NAME
[MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) -- V11 [ISG], `Object *`, 0x8042b704

### FUNCTION
Specifies a context sensitive popup menu for the current object. For MUI,
popup menus are nothing else but standard menus, so you must specify a
pointer to a MUI menustrip object (e.g. something returned from
MUI_MakeObject(MUIO_MenustripNM,...)) here.

Whenever the user hits the RMB and the mouse is above the parent object, MUI
will present the popup menu instead of the windows menu.

Note: MUI will **NOT** dispose the [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) object when the object is
disposed. You must take care of the menustrip object yourself. This is
because menustrip objects in [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) do not actually "belong" to
their parent objects, they're just a "reference". You are allowed to use a
single menustrip object as [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) for different objects of the
same window. Do **NOT** share with objects in other windows or with the
default menu of a window or an application!

If the user selects an item, the object will receive a
[MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice) method containing the selected menuitem object. If
you build your menustrip tree with MUI_MakeObject(MUIO_MenustripNM,...), you
will find the nm_UserData of your menu entry in muiUserData(msg->item). If
you have control over methods because you are a subclass, you can
immediately take approriate actions when receiving [MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice).

If you don't have a subclass or don't override [MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice), the
method will finally reach Area class and will set the attribute
[MUIA_ContextMenuTrigger](MUI_Area.md/#MUIA_ContextMenuTrigger) to the appropriate menuitem object. This allows you
to react on context menu selections by simple notification and eliminates
the need of writing a subclass just for this purpose. Subclasses are always
the better solution though!

There is also a possibility to dynamically create popup menus on the fly.
See [MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild) for details.

### NOTES
MUI uses the same tree-like technique as always (e.g. with drag&drop) to
find out which context menu to use on a certain mouse position. This allows
you to have a context menu for a group and different context menus for its
children. The MUI preferences program makes use of that feature by allowing
to control a single gadget or a whole page of gadgets with popup menus.

### SEE ALSO
[MUIA_ContextMenuHook](MUI_Area.md/#MUIA_ContextMenuHook), [MUIA_ContextMenuTrigger](MUI_Area.md/#MUIA_ContextMenuTrigger), [MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice),
[MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild)

## MUIA_ContextMenuHook
### NAME
[MUIA_ContextMenuHook](MUI_Area.md/#MUIA_ContextMenuHook) -- V20 [ISG], `struct Hook *`, 0x80427c6e

### FUNCTION
Specifies a hook function to return a context sensitive popup menu for the
current object. The hook function gets the current object and a pointer to a
struct MUIP_ContextMenuBuild structure passed as parameters to dynamically
return different menu objects depending on the object and on the current
mouse position. In addition [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) **MUST** be set to TRUE to
basically enable context menu support for the object.

Note: MUI will **NOT** dispose the returned menu object when the object is
disposed. You must take care of the menustrip object yourself. This is
because menustrip objects from [MUIA_ContextMenuHook](MUI_Area.md/#MUIA_ContextMenuHook) do not actually "belong"
to their parent objects, they're just a "reference". You are allowed to
return a single menustrip object from the hook for different objects of the
same window. Do **NOT** share with objects in other windows or with the
default menu of a window or an application!

### EXAMPLE
```c++
ASM Object *ctxmenuFunc(REG(a0, struct Hook *hook),
                        REG(a2, Object *obj),
                        REG(a1, struct MUIP_ContextMenuBuild *msg))
{
  // return a context menu for a specific object
  if(obj == specialObject)
    return specialMenu;

  // "obj" always refers to the object the mouse is currently
  // hovering over. Hence the mouse coordinates are guaranteed
  // to be within the object's realm.

  // return different context menu object for the object's left
  // and right half
  if(msg->mx <= _left(obj)+_width(obj)/2)
    return leftSideMenu;
  else
    return rightSideMenu;
}

[...]
struct Hook ctxmenuHook;
Object *myobj;

memset(&ctxmenuHook, 0, sizeof(struct ctxmenuHook));
ctxmenuHook.h_Entry = (HOOKFUNC)ctxmenuFunc;

myobj = MUI_NewObject("fooclass",
  MUIA_ContextMenu, TRUE,
  MUIA_ContextMenuHook, &ctxmenuHook,
  TAG_DONE);
```

### SEE ALSO
[MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu), [MUIA_ContextMenuTrigger](MUI_Area.md/#MUIA_ContextMenuTrigger), [MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild)

## MUIA_ContextMenuTrigger
### NAME
[MUIA_ContextMenuTrigger](MUI_Area.md/#MUIA_ContextMenuTrigger) -- V11 [..G], `Object *`, 0x8042a2c1

### FUNCTION
Allows reacting on context menus with notificaton. When the
[MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice) method reaches Area class because you did not
override it in a subclass, it sets [MUIA_ContextMenuTrigger](MUI_Area.md/#MUIA_ContextMenuTrigger) to the received
parameter which is a pointer to the user-selected menuitem object.

See [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) for details.

### SEE ALSO
[MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu), [MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice), [MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild)

## MUIA_ControlChar
### NAME
[MUIA_ControlChar](MUI_Area.md/#MUIA_ControlChar) -- V4 [ISG], `char`, 0x8042120b

### FUNCTION
Pressing the control char will have the same effect as pressing return if
the object was active.

This can be used to create old style key shortcuts.

Note: Using an uppercase control char will force the user to press shift.

### SEE ALSO
mui.h / KeyButton() macro

## MUIA_CycleChain
### NAME
[MUIA_CycleChain](MUI_Area.md/#MUIA_CycleChain) -- V11 [ISG], `LONG`, 0x80421ce7

### FUNCTION
MUI 3 introduces a new keyboard cycle chain system. All you have to do is to
set  [MUIA_CycleChain](MUI_Area.md/#MUIA_CycleChain) to 1 for every object that you want to have in your
chain, MUI does the rest automatically. The old [MUIM_Window_SetCycleChain](MUI_Window.md/#MUIM_Window_SetCycleChain)
will continue to work but is considered obsolete.

### SEE ALSO
[MUIM_Window_SetCycleChain](MUI_Window.md/#MUIM_Window_SetCycleChain)

## MUIA_Disabled
### NAME
[MUIA_Disabled](MUI_Area.md/#MUIA_Disabled) -- V4 [ISG], `BOOL`, 0x80423661

### FUNCTION
Disable or enable a gadget. Setting this attribute causes a gadget to become
disabled, it gets a ghost pattern and doesn't respond to user input any
longer.

Disabled gadgets cannot be activated with the TAB key.

Using [MUIA_Disable](MUI_Area.md/#MUIA_Disable) on a group of objects will disable all objects within
that group.

### EXAMPLE
```c++
/* we have a radio button gadget with three         */
/* entries, the third should enable a string gadget */
/* with additional parameters                       */

DoMethod(radio, MUIM_Notify, MUIA_Radio_Active, 0,
  string, 3, MUIM_Set,
  MUIA_Disabled, TRUE);

DoMethod(radio, MUIM_Notify, MUIA_Radio_Active, 1,
  string, 3, MUIM_Set,
  MUIA_Disabled, TRUE);

DoMethod(radio, MUIM_Notify, MUIA_Radio_Active, 2,
  string, 3, MUIM_Set,
  MUIA_Disabled, FALSE);
```

## MUIA_DoubleBuffer
### NAME
[MUIA_DoubleBuffer](MUI_Area.md/#MUIA_DoubleBuffer) -- V20 [ISG], `BOOL`, 0x8042a9c7

### FUNCTION
Setting this to TRUE will enable a doublebuffer for this objects [MUIM_Draw](MUI_Area.md/#MUIM_Draw)
method.

When MUI is about to draw an object with this attribute, it will maintain an
extra struct MUI_RenderInfo which points to an offscreen bitmap. Just before
calling [MUIM_Draw](MUI_Area.md/#MUIM_Draw), your object's normal muiRenderInfo(obj) pointer (which
stores drawing attributes such as _rp(obj) for example) will be replaced by
this buffered MUI_RenderInfo. Also, your object's coordinates (_mleft(obj),
_mtop(obj), etc) will be changed to point into the offscreen buffer.

Your [MUIM_Draw](MUI_Area.md/#MUIM_Draw) method can then render as it would normally do, there is no
need to change anything for the doublebuffer. When it is completed, MUI will
blit the contents of the offscreen-bitmap into view and then restore your
object's coordinates and MUI_RenderInfo pointers to their standard values.

### NOTES
This attribute is **ONLY** meant for your own subclasses of Area class. Don't
use it on subclasses of Group class or on other classes not written by you.

You must absolutely make sure to not render outside your object's bounding box,
always stay between _mleft/_mtop/_mright/_bottom. Otherwise you will trash
innocent memory since the offscreen bitmap may just be big enough and has no
clipping enabled.

Special care must be taken when your classes draw method interfaces other
coordinates, like for example the mouse-position. You would have to substract
_left/_top in [MUIM_HandleEvent](MUI_Area.md/#MUIM_HandleEvent) from imsg->MouseX/Y before storing the
coordinates (ie make them relative to your objects origin) and then, when using
them in your [MUIM_Draw](MUI_Area.md/#MUIM_Draw) method, add _left/_top(obj) again. This will ensure
everything ends up at its place regardless whether you use [MUIA_DoubleBuffer](MUI_Area.md/#MUIA_DoubleBuffer) or
not.

IMPORTANT: MUI may also use different methods of double buffering, besides
allocating new bitmap structures. It may for example decide to do nothing at all
when it finds out, that the underlying intuition/layer libraries already
implement buffering.

You CANNOT make any assumptions about the double buffer, its bitmap, its
coordinates, its lifetime or anything else. Your rendering code must work just
as flawlessly with [MUIA_DoubleBuffer](MUI_Area.md/#MUIA_DoubleBuffer)=TRUE as with [MUIA_DoubleBuffer](MUI_Area.md/#MUIA_DoubleBuffer)=FALSE.

## MUIA_DoubleClick
### NAME
[MUIA_DoubleClick](MUI_Area.md/#MUIA_DoubleClick) -- V20 [..G], `BOOL`, 0x8042f057

### FUNCTION
This attribute will be set to TRUE whenever a double click on the object is
detected. The most appropriate use is in notifications only.

## MUIA_Draggable
### NAME
[MUIA_Draggable](MUI_Area.md/#MUIA_Draggable) -- V11 [ISG], `BOOL`, 0x80420b6e

### FUNCTION
Set this if you want the complete object to be dragable for D&D operations.

## MUIA_Dropable
### NAME
[MUIA_Dropable](MUI_Area.md/#MUIA_Dropable) -- V11 [ISG], `BOOL`, 0x8042fbce

### FUNCTION
Only objects with this attribute set to TRUE will be asked if they want to
become an active Drag & Drop destination at all. Though this attribute
defaults to TRUE, this doesn't mean that every object automatically accepts
D&D actions, because the [MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery) method is answered FALSE when it
arrives at Area class.

### SEE ALSO
[MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery)

## MUIA_ExportID
### NAME
[MUIA_ExportID](MUI_Area.md/#MUIA_ExportID) -- V4 [ISG], `ULONG`, 0x8042d76e **(OBSOLETE)**

### FUNCTION
Obsolete. See Notify.mui/[MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID)

### NOTES
This attribute was renamed to [MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID) and moved to Notify class in
muimaster.library V12.

### SEE ALSO
[MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID), [MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load), [MUIM_Application_Save](MUI_Application.md/#MUIM_Application_Save)

## MUIA_FillArea
### NAME
[MUIA_FillArea](MUI_Area.md/#MUIA_FillArea) -- V4 [IS.], `BOOL`, 0x804294a3

### FUNCTION
Set this to FALSE if you are a custom class and don't want Area class to
clear your background during the DoSuperMethod() in your [MUIM_Draw](MUI_Area.md/#MUIM_Draw) method.
Note that if you set this, your [MUIM_Draw](MUI_Area.md/#MUIM_Draw) method is responsible for filling
every pixel of your objects rectangle, otherwise some display trash will
remain there.

## MUIA_FixHeight
### NAME
[MUIA_FixHeight](MUI_Area.md/#MUIA_FixHeight) -- V4 [I..], `LONG`, 0x8042a92b

### FUNCTION
Give your object a fixed pixel height. This tag is absolutely not needed in
a general MUI application and only present for emergency situations. Please
think twice before using it!

### EXAMPLE
```c++
/* create an 8x8 pixel rectangle with FILLPEN */

RectangleObject,
  MUIA_FixWidth  , 8,
  MUIA_FixHeight , 8,
  MUIA_Background, MUII_FILL,
  End;
```

### SEE ALSO
[MUIA_FixWidth](MUI_Area.md/#MUIA_FixWidth), [MUIA_FixWidthTxt](MUI_Area.md/#MUIA_FixWidthTxt), [MUIA_FixHeightTxt](MUI_Area.md/#MUIA_FixHeightTxt)

## MUIA_FixHeightTxt
### NAME
[MUIA_FixHeightTxt](MUI_Area.md/#MUIA_FixHeightTxt) -- V4 [I..], `STRPTR`, 0x804276f2

### FUNCTION
Give your object a fixed pixel height. The height will match the height of
the given string. This tag is absolutely not needed in a general MUI
application and only present for emergency situations. Please think twice
before using it!

### EXAMPLE
```c++
/* create a fixed size rectangle with FILLPEN */

RectangleObject,
  MUIA_FixWidthTxt , "00:00:00",
  MUIA_FixHeightTxt, "\n\n",
  MUIA_Background  , MUII_FILL,
  End;
```

### SEE ALSO
[MUIA_FixHeight](MUI_Area.md/#MUIA_FixHeight), [MUIA_FixWidth](MUI_Area.md/#MUIA_FixWidth), [MUIA_FixWidthTxt](MUI_Area.md/#MUIA_FixWidthTxt)

## MUIA_FixWidth
### NAME
[MUIA_FixWidth](MUI_Area.md/#MUIA_FixWidth) -- V4 [I..], `LONG`, 0x8042a3f1

### FUNCTION
Give your object a fixed pixel width. This tag is absolutely not needed in a
general MUI application and only present for emergency situations. Please
think twice before using it!

### EXAMPLE
```c++
/* create an 8x8 pixel rectangle with FILLPEN */

RectangleObject,
  MUIA_FixWidth  , 8,
  MUIA_FixHeight , 8,
  MUIA_Background, MUII_FILL,
  End;
```

### SEE ALSO
[MUIA_FixHeight](MUI_Area.md/#MUIA_FixHeight), [MUIA_FixWidthTxt](MUI_Area.md/#MUIA_FixWidthTxt), [MUIA_FixHeightTxt](MUI_Area.md/#MUIA_FixHeightTxt)

## MUIA_FixWidthTxt
### NAME
[MUIA_FixWidthTxt](MUI_Area.md/#MUIA_FixWidthTxt) -- V4 [I..], `STRPTR`, 0x8042d044

### FUNCTION
Give your object a fixed pixel width. The width will match the width of the
given string. This tag is absolutely not needed in a general MUI application
and only present for emergency situations. Please think twice before using
it!

### EXAMPLE
```c++
/* create a fixed size rectangle with FILLPEN */

RectangleObject,
  MUIA_FixWidthTxt , "00:00:00",
  MUIA_FixHeightTxt, "\n\n",
  MUIA_Background  , MUII_FILL,
  End;
```

### SEE ALSO
[MUIA_FixHeight](MUI_Area.md/#MUIA_FixHeight), [MUIA_FixWidth](MUI_Area.md/#MUIA_FixWidth), [MUIA_FixHeightTxt](MUI_Area.md/#MUIA_FixHeightTxt)

## MUIA_Floating
### NAME
[MUIA_Floating](MUI_Area.md/#MUIA_Floating) -- V20 [ISG], `BOOL`, 0x80429753

### FUNCTION
Usually every MUI object will be layouted and drawn in exactly the same
sequence as it has been constructed along with other objects. Floating
objects however will be layouted and drawn after all other objects to make
sure they appear in front of all other objects in case they overlap. Such
object's classes should implement [MUIM_Layout](MUI_Area.md/#MUIM_Layout) to ensure a proper layout.

### EXAMPLE
```c++
obj1 = ExampleObject,
  MUIA_Floating, TRUE,
  End,
obj2 = ExampleObject,
  MUIA_Floating, FALSE,
  End,
  ...
```

In this scenario obj1 will be layouted and drawn after obj2, although it was
created earlier.

### SEE ALSO
[MUIM_Layout](MUI_Area.md/#MUIM_Layout)

## MUIA_Font
### NAME
[MUIA_Font](MUI_Area.md/#MUIA_Font) -- V4 [ISG], `struct TextFont *`, 0x8042be50

### SPECIAL INPUTS
  * MUIV_Font_Inherit
  * MUIV_Font_Normal
  * MUIV_Font_List
  * MUIV_Font_Tiny
  * MUIV_Font_Fixed
  * MUIV_Font_Title
  * MUIV_Font_Big
  * MUIV_Font_Button
  * MUIV_Font_Slider
  * MUIV_Font_Gauge
  * MUIV_Font_Menu
  * MUIV_Font_Tab
  * MUIV_Font_Bubble
  * MUIV_Font_Huge
  * MUIV_Font_Last
  * MUIV_Font_Count

### FUNCTION
Every MUI object can have its own font, just set it with this tag. Objects
without an explicit font setting will inherit it from their parent group.

You normally won't need to open a font yourself, just use one of the
predefined values to get a font from the users preferences:

**`MUIV_Font_Inherit`**
     use the same font as the surrounding object, this is the default.

**`MUIV_Font_Normal`**
     use the normal font.

**`MUIV_Font_List`**
     use the font configured for lists.

**`MUIV_Font_Tiny`**
     use the tiny font.

**`MUIV_Font_Fixed`**
     use the fixed width font.

**`MUIV_Font_Title`**
     use the font configured for group titles.

**`MUIV_Font_Big`**
     use the big font.

**`MUIV_Font_Button`**
     use the font configured for buttons.

**`MUIV_Font_Slider`**
     use the font configured for sliders.

**`MUIV_Font_Gauge`**
     use the font configured for gauges.

**`MUIV_Font_Menu`**
     use the font configured for menus.

**`MUIV_Font_Tab`**
     use the font configured for tab buttons.

**`MUIV_Font_Bubble`**
     use the font configured for bubble help.

**`MUIV_Font_Huge`**
     use the huge font.

You can also pass a struct TextFont * obtained by OpenFont(). You are
responsible for freeing this font yourself after the object is disposed.

### EXAMPLE
```c++
/* since the text contains tabs,           */
/* use the fixed width font for displaying */

msgread = FloattextObject,
 MUIA_Font, MUIV_Font_Fixed,
 ...,
 End;
```

## MUIA_Frame
### NAME
[MUIA_Frame](MUI_Area.md/#MUIA_Frame) -- V4 [I..], `LONG`, 0x8042ac64

### SPECIAL INPUTS
  * MUIV_Frame_None
  * MUIV_Frame_Button
  * MUIV_Frame_ImageButton
  * MUIV_Frame_Text
  * MUIV_Frame_String
  * MUIV_Frame_ReadList
  * MUIV_Frame_InputList
  * MUIV_Frame_Prop
  * MUIV_Frame_Gauge
  * MUIV_Frame_Group
  * MUIV_Frame_PopUp
  * MUIV_Frame_Virtual
  * MUIV_Frame_Slider
  * MUIV_Frame_SliderKnob
  * MUIV_Frame_GaugeInner
  * MUIV_Frame_Menudisplay
  * MUIV_Frame_MenudisplayMenu
  * MUIV_Frame_PropKnob
  * MUIV_Frame_Window
  * MUIV_Frame_Requester
  * MUIV_Frame_Page
  * MUIV_Frame_Register
  * MUIV_Frame_GroupTitle
  * MUIV_Frame_RegisterTitle
  * MUIV_Frame_Count

### FUNCTION
Define a frame for the current object. Since Area class is a superclass for all
elements in a window, you can assign frames to every object you wish.

You don't adjust the style of your frame directly, instead you only specify a
type:

**`MUIV_Frame_Button`**
     for standard buttons with text in it.

**`MUIV_Frame_ImageButton`**
     for small buttons with images, e.g. the arrows of a scrollbar.

**`MUIV_Frame_Text`**
     for a text field, e.g. a status line display.

**`MUIV_Frame_String`**
     for a string gadget.

**`MUIV_Frame_ReadList`**
     for a read only list.

**`MUIV_Frame_InputList`**
     for a list that handles input (has a cursor).

**`MUIV_Frame_Prop`**
     for proportional gadgets.

**`MUIV_Frame_Group`**
     for groups.

How the frame is going to look is adjustable via the preferences program.

Four spacing values belong to each frame that tell MUI how many pixels should
be left free between the frame and its contents. These spacing values are also
user adjustable as long as you don't override them with one of [MUIA_InnerLeft](MUI_Area.md/#MUIA_InnerLeft),
[MUIA_InnerRight](MUI_Area.md/#MUIA_InnerRight), [MUIA_InnerTop](MUI_Area.md/#MUIA_InnerTop) or [MUIA_InnerBottom](MUI_Area.md/#MUIA_InnerBottom).

Starting with version 20 of muimaster.library, you can also pass a pointer to a
struct MUI_FrameSpec as [MUIA_Frame](MUI_Area.md/#MUIA_Frame). This allows the use of customized frames
adjustable with the Frameadjust class custom class. Note that the pointer to the
passed MUI_FrameSpec must remain valid until you overwrite [MUIA_Frame](MUI_Area.md/#MUIA_Frame) with
something different or dispose the object. A good place to keep the
MUI_FrameSpec is the instance data of your custom class.

Do not pass such pointers if your muimaster.library is version 19 or below!

### NOTES
The first object in a window ([MUIA_Window_RootObject](MUI_Window.md/#MUIA_Window_RootObject)) can **NOT** have a
frame. If you need this you will have to create a dummy group with just one
child.

### EXAMPLE
```c++
strobj = StringObject,
  MUIA_Frame, MUIV_Frame_String,
  End;
```

### SEE ALSO
[MUIA_InnerLeft](MUI_Area.md/#MUIA_InnerLeft), [MUIA_InnerRight](MUI_Area.md/#MUIA_InnerRight), [MUIA_InnerTop](MUI_Area.md/#MUIA_InnerTop), [MUIA_InnerBottom](MUI_Area.md/#MUIA_InnerBottom)

## MUIA_FrameDynamic
### NAME
[MUIA_FrameDynamic](MUI_Area.md/#MUIA_FrameDynamic) -- V20 [ISG], `BOOL`, 0x804223c9

### FUNCTION
This attribute defines whether the object's frame will be dynamically
visible or not. If set to TRUE the frame will be made visible as soon as the
mouse pointer is over the object and made invisible when the mouse leaves
the object. Best use the attribute together with [MUIA_FrameVisible](MUI_Area.md/#MUIA_FrameVisible) set to
FALSE to make the frame invisible by default.

Defaults to FALSE.

### SEE ALSO
[MUIA_Frame](MUI_Area.md/#MUIA_Frame), [MUIA_FrameVisible](MUI_Area.md/#MUIA_FrameVisible)

## MUIA_FramePhantomHoriz
### NAME
[MUIA_FramePhantomHoriz](MUI_Area.md/#MUIA_FramePhantomHoriz) -- V4 [I..], `BOOL`, 0x8042ed76

### FUNCTION
Setting this to TRUE causes the specified frame to be a horizontal phantom
frame. The frame will not appear but its vertical components (frame height,
inner top and inner bottom spacing) will be used to calculate positions and
dimensions (horizontal components are treated as 0).

This is extremely useful for a correct labeling of objects. You would e.g.
label a string gadget by using a text object with a phantom string frame.
Thus, the label text will be always on the same vertical position as the
string gadget text, no matter what spacing values the user configured.

### SEE ALSO
Label() macros in "mui.h".

## MUIA_FrameTitle
### NAME
[MUIA_FrameTitle](MUI_Area.md/#MUIA_FrameTitle) -- V4 [ISG], `STRPTR`, 0x8042d1c7

### FUNCTION
This tag identifies a text string that will be displayed in the top line of
a frame. This can come in handy if you want to name groups of objects.

You may not use [MUIA_FrameTitle](MUI_Area.md/#MUIA_FrameTitle) without defining a [MUIA_Frame](MUI_Area.md/#MUIA_Frame).

### EXAMPLE
```c++
VGroup,
  MUIA_Frame, MUIV_Frame_Group,
  MUIA_FrameTitle, "Spacing",
  ...
```

### SEE ALSO
[MUIA_Frame](MUI_Area.md/#MUIA_Frame)

## MUIA_FrameVisible
### NAME
[MUIA_FrameVisible](MUI_Area.md/#MUIA_FrameVisible) -- V20 [ISG], `BOOL`, 0x80426498

### FUNCTION
This attribute defines whether the object's frame will be visible or not, no
matter which kind of frame is set.

Defaults to TRUE.

### SEE ALSO
[MUIA_Frame](MUI_Area.md/#MUIA_Frame), [MUIA_FrameDynamic](MUI_Area.md/#MUIA_FrameDynamic)

## MUIA_Height
### NAME
[MUIA_Height](MUI_Area.md/#MUIA_Height) -- V4 [..G], `LONG`, 0x80423237

### FUNCTION
You can use this to read the current position and dimension of an object, if
you e.g. need it to pop up some requester below.

Of course, this attribute is only valid when the parent window of the object
is currently open.

### SEE ALSO
[MUIA_TopEdge](MUI_Area.md/#MUIA_TopEdge), [MUIA_Width](MUI_Area.md/#MUIA_Width), [MUIA_LeftEdge](MUI_Area.md/#MUIA_LeftEdge), [MUIA_RightEdge](MUI_Area.md/#MUIA_RightEdge), [MUIA_BottomEdge](MUI_Area.md/#MUIA_BottomEdge)

## MUIA_HorizDisappear
### NAME
[MUIA_HorizDisappear](MUI_Area.md/#MUIA_HorizDisappear) -- V11 [ISG], `LONG`, 0x80429615

### FUNCTION
Objects with a disappear level disappear automatically when their parent
window gets too small to display them. Use this for things that make your
GUI look nicer (e.g. Imagery) but are not absolutely necessary.

By using disappearing objects, you can make nice GUIs which still work on
crappy 640x200 screens.

You can give horizontal or vertical disappear levels to objects which are
used for horizontal or vertical layout calculations respectively.

Objects with a small disappear level disappear before objects with a big
disappear level.

### EXAMPLE
```c++
// group with objects disappearing from right to left,
// like a row of hotlink buttons in a browser:

// creation:
quickies = HGroup, End;

// add a few buttons:
for(i=0;i<20;i++)
{
  char buf[256];

  snprintf(buf, sizeof(buf), "Quicklink %ld", i);
  DoMethod(quickies, OM_ADDMEMBER, SimpleButton(buf));
}

// set up the disappear levels, right one goes first
int dis; Object *but;
get(quickies,MUIA_Group_ChildCount,&dis);
for(but=NULL; but=(Object *)DoMethod(quickies, MUIM_Group_GetChild, MUIV_Group_GetChild_Next, but);)
{
  SetAttrs(but, MUIA_HorizDisappear, dis--, TAG_DONE);
}
```

### SEE ALSO
[MUIA_VertDisappear](MUI_Area.md/#MUIA_VertDisappear), [MUIM_Group_GetChild](MUI_Group.md/#MUIM_Group_GetChild)

## MUIA_HorizWeight
### NAME
[MUIA_HorizWeight](MUI_Area.md/#MUIA_HorizWeight) -- V4 [ISG], `WORD`, 0x80426db9

### FUNCTION
Adjust the horizontal weight of an object. Usually you can simply use
[MUIA_Weight](MUI_Area.md/#MUIA_Weight) instead of this tag but in some two-dimensional groups it may
become handy to have different horizontal and vertical weights.

### SEE ALSO
[MUIA_Weight](MUI_Area.md/#MUIA_Weight)

## MUIA_InnerBottom
### NAME
[MUIA_InnerBottom](MUI_Area.md/#MUIA_InnerBottom) -- V4 [I.G], `LONG`, 0x8042f2c0

### FUNCTION
Adjust the space between an object and its frame. Usually you shouldn't use
this tag since you will override the user's preferred default setting.

### SEE ALSO
[MUIA_Frame](MUI_Area.md/#MUIA_Frame)

## MUIA_InnerLeft
### NAME
[MUIA_InnerLeft](MUI_Area.md/#MUIA_InnerLeft) -- V4 [I.G], `LONG`, 0x804228f8

### FUNCTION
Adjust the space between an object and its frame. Usually you shouldn't use
this tag since you will override the user's preferred default setting.

### SEE ALSO
[MUIA_Frame](MUI_Area.md/#MUIA_Frame)

## MUIA_InnerRight
### NAME
[MUIA_InnerRight](MUI_Area.md/#MUIA_InnerRight) -- V4 [I.G], `LONG`, 0x804297ff

### FUNCTION
Adjust the space between an object and its frame. Usually you shouldn't use
this tag since you will override the user's preferred default setting.

### SEE ALSO
[MUIA_Frame](MUI_Area.md/#MUIA_Frame)

## MUIA_InnerTop
### NAME
[MUIA_InnerTop](MUI_Area.md/#MUIA_InnerTop) -- V4 [I.G], `LONG`, 0x80421eb6

### FUNCTION
Adjust the space between an object and its frame. Usually you shouldn't use
this tag since you will override the user's preferred default setting.

### SEE ALSO
[MUIA_Frame](MUI_Area.md/#MUIA_Frame)

## MUIA_InputMode
### NAME
[MUIA_InputMode](MUI_Area.md/#MUIA_InputMode) -- V4 [I..], `LONG`, 0x8042fb04

### SPECIAL INPUTS
  * MUIV_InputMode_None
  * MUIV_InputMode_RelVerify
  * MUIV_InputMode_Immediate
  * MUIV_InputMode_Toggle

### FUNCTION
Adjust the input mode for an object.

MUI has no distinct button class. Instead you can make every object (even
groups) behave like a button by setting an input mode for them. Several
input modes are available:

**`MUIV_InputMode_None`**
     No input, this is not a gadget.

**`MUIV_InputMode_RelVerify`**
     For buttons and similar stuff.

**`MUIV_InputMode_Immediate`**
     Used e.g. in a radio button object.

**`MUIV_InputMode_Toggle`**
     For things like checkmark gadgets.

The input mode setting determines how a user action will trigger the
attributes [MUIA_Selected](MUI_Area.md/#MUIA_Selected), [MUIA_Pressed](MUI_Area.md/#MUIA_Pressed) and [MUIA_Timer](MUI_Area.md/#MUIA_Timer). See their
documentation for details.

### EXAMPLE
```c++
/* A traditional button, just a text object with */
/* a button frame and a relverify input mode:    */

okbutton = TextObject,
  MUIA_Frame        , MUIV_Frame_Button,
  MUIA_InputMode    , MUIV_InputMode_RelVerify,
  MUIA_Text_Contents, "OK",
  ...
```

### SEE ALSO
[MUIA_Selected](MUI_Area.md/#MUIA_Selected), [MUIA_Timer](MUI_Area.md/#MUIA_Timer), [MUIA_Pressed](MUI_Area.md/#MUIA_Pressed)

## MUIA_KnowsDisabled
### NAME
[MUIA_KnowsDisabled](MUI_Area.md/#MUIA_KnowsDisabled) -- V20 [ISG], `BOOL`, 0x8042deef

### FUNCTION
Usually MUI will take care to draw a suitable disable pattern for objects
which have [MUIA_Disabled](MUI_Area.md/#MUIA_Disabled) set to TRUE. However, if your class knows a special
way to indicate the disabled state in a different way then set this
attribute to TRUE. MUI will then no longer apply its own disabled pattern
for this object.

### SEE ALSO
[MUIA_Disabled](MUI_Area.md/#MUIA_Disabled)

## MUIA_LeftEdge
### NAME
[MUIA_LeftEdge](MUI_Area.md/#MUIA_LeftEdge) -- V4 [..G], `LONG`, 0x8042bec6

### FUNCTION
You can use this to read the current position and dimension of an object, if
you e.g. need it to pop up some requester below.

Of course, this attribute is only valid when the parent window of the object
is currently open.

### SEE ALSO
[MUIA_TopEdge](MUI_Area.md/#MUIA_TopEdge), [MUIA_Width](MUI_Area.md/#MUIA_Width), [MUIA_Height](MUI_Area.md/#MUIA_Height), [MUIA_RightEdge](MUI_Area.md/#MUIA_RightEdge), [MUIA_BottomEdge](MUI_Area.md/#MUIA_BottomEdge)

## MUIA_MaxHeight
### NAME
[MUIA_MaxHeight](MUI_Area.md/#MUIA_MaxHeight) -- V11 [I..], `LONG`, 0x804293e4

### FUNCTION
Specify a maximum height for an object (in pixels).

### SEE ALSO
[MUIA_MaxWidth](MUI_Area.md/#MUIA_MaxWidth), [MUIA_FixWidth](MUI_Area.md/#MUIA_FixWidth), [MUIA_FixHeight](MUI_Area.md/#MUIA_FixHeight)

## MUIA_MaxWidth
### NAME
[MUIA_MaxWidth](MUI_Area.md/#MUIA_MaxWidth) -- V11 [I..], `LONG`, 0x8042f112

### FUNCTION
Specify a maximum width for an object (in pixels).

### SEE ALSO
[MUIA_MaxHeight](MUI_Area.md/#MUIA_MaxHeight), [MUIA_FixWidth](MUI_Area.md/#MUIA_FixWidth), [MUIA_FixHeight](MUI_Area.md/#MUIA_FixHeight)

## MUIA_MinHeight
### NAME
[MUIA_MinHeight](MUI_Area.md/#MUIA_MinHeight) -- V20 [I..], `LONG`, 0x8042c04a

### FUNCTION
Specify a minimum height for an object (in pixels). This attribute exists for
convenience reasons only. It is a much cleaner approach to create a subclass of
Area class and overload the [MUIM_AskMinMax](MUI_Area.md/#MUIM_AskMinMax) method to enforce a certain minimum
height.

### SEE ALSO
[MUIA_MinWidth](MUI_Area.md/#MUIA_MinWidth)

## MUIA_MinWidth
### NAME
[MUIA_MinWidth](MUI_Area.md/#MUIA_MinWidth) -- V20 [I..], `LONG`, 0x80424342

### FUNCTION
Specify a minimum width for an object (in pixels). This attribute exists for
convenience reasons only. It is a much cleaner approach to create a subclass
or Area class and overload the [MUIM_AskMinMax](MUI_Area.md/#MUIM_AskMinMax) method to enforce a certain
minimum width.

### SEE ALSO
[MUIA_MinHeight](MUI_Area.md/#MUIA_MinHeight)

## MUIA_PointerType
### NAME
[MUIA_PointerType](MUI_Area.md/#MUIA_PointerType) -- V20 [ISG], `LONG`, 0x8042b467

### SPECIAL INPUTS
  * MUIV_PointerType_Parent
  * MUIV_PointerType_Normal
  * MUIV_PointerType_Busy
  * MUIV_PointerType_Alias
  * MUIV_PointerType_Cell
  * MUIV_PointerType_ColumnResize
  * MUIV_PointerType_ContextMenu
  * MUIV_PointerType_Copy
  * MUIV_PointerType_Cross
  * MUIV_PointerType_DragAndDrop
  * MUIV_PointerType_EastResize
  * MUIV_PointerType_EastWestResize
  * MUIV_PointerType_Hand
  * MUIV_PointerType_Help
  * MUIV_PointerType_Link
  * MUIV_PointerType_Menu
  * MUIV_PointerType_NoDrop
  * MUIV_PointerType_None
  * MUIV_PointerType_NorthEastResize
  * MUIV_PointerType_NorthEastSouthWestResize
  * MUIV_PointerType_NorthResize
  * MUIV_PointerType_NorthSouthResize
  * MUIV_PointerType_NorthWestResize
  * MUIV_PointerType_NorthWestSouthEastResize
  * MUIV_PointerType_NotAllowed
  * MUIV_PointerType_Progress
  * MUIV_PointerType_RowResize
  * MUIV_PointerType_ScrollAll
  * MUIV_PointerType_SouthEastResize
  * MUIV_PointerType_SouthResize
  * MUIV_PointerType_SouthWestResize
  * MUIV_PointerType_Text
  * MUIV_PointerType_VerticalText
  * MUIV_PointerType_WestResize
  * MUIV_PointerType_ZoomIn
  * MUIV_PointerType_ZoomOut
  * MUIV_PointerType_Pen
  * MUIV_PointerType_Rotate
  * MUIV_PointerType_Rotation
  * MUIV_PointerType_Rubber
  * MUIV_PointerType_Select
  * MUIV_PointerType_Smudge
  * MUIV_PointerType_Count

### FUNCTION
[MUIA_PointerType](MUI_Area.md/#MUIA_PointerType) defines the built-in mouse pointer to be used when the
mouse hovers over the object. Usually this is used to indicate certain
actions which will be triggered when the object is clicked or to make its
purpose more obvious. For example, string gadgets may use a text cursur as
mouse pointer to indicate that the object accepts text for input.

There is one special value:
**`MUIV_PointerType_Parent`**
     Use the parent object's mouse pointer. This is useful for embedded objects
     to use the same pointer as the parent object without having to know which
     one is actually used. This is the default value.

It is also possible to set custom pointer images created by pointerclass.

In case you need different pointer types depending on the mouse position
within the object your object's class must overload the method
[MUIM_WhichPointerType](MUI_Area.md/#MUIM_WhichPointerType) and return the desired pointer type value.

MUI has built-in images for all kinds of pointer types except the normal and
the busy pointer. The system images will be used in this case.

For AmigaOS4.1 intuition.library 53.41+ is able to use truecolor images as
mouse pointer images if the hardware is capable to handle these. If all this
is the case then the appropriate truecolor system images will be used.

### EXAMPLE
```c++
set(obj, MUIA_PointerType, MUIV_PointerType_Text);
```

A detailed example can be found in the source code of the Pointers demo
application.

### SEE ALSO
[MUIM_WhichPointerType](MUI_Area.md/#MUIM_WhichPointerType)

## MUIA_Pressed
### NAME
[MUIA_Pressed](MUI_Area.md/#MUIA_Pressed) -- V4 [..G], `BOOL`, 0x80423535

### FUNCTION
Learn if a button is pressed (or released). The [MUIA_Pressed](MUI_Area.md/#MUIA_Pressed) attribute of a
gadget is triggered by some user action, depending on the input mode:

MUIV_InputMode_RelVerify:
   - set when lmb is pressed.
   - cleared when lmb is released and the mouse is still over the gadget
     (otherwise it will be cleared too, but without triggering a
     notification event).

MUIV_InputMode_Immediate:
   - undefined, use [MUIA_Selected](MUI_Area.md/#MUIA_Selected) for this.

MUIV_InputMode_Toggle:
   - undefined, use [MUIA_Selected](MUI_Area.md/#MUIA_Selected) for this.

Waiting for [MUIA_Pressed](MUI_Area.md/#MUIA_Pressed) becoming FALSE is the usual way to react on button
gadgets.

### EXAMPLE
```c++
DoMethod(btcancel, MUIM_Notify, MUIA_Pressed, FALSE,
  app, 2,
  MUIM_Application_ReturnID, ID_CANCEL);
```

### SEE ALSO
[MUIA_Selected](MUI_Area.md/#MUIA_Selected), [MUIA_Timer](MUI_Area.md/#MUIA_Timer), [MUIA_ShowSelState](MUI_Area.md/#MUIA_ShowSelState), [MUIA_InputMode](MUI_Area.md/#MUIA_InputMode)

## MUIA_RightEdge
### NAME
[MUIA_RightEdge](MUI_Area.md/#MUIA_RightEdge) -- V4 [..G], `LONG`, 0x8042ba82

### FUNCTION
You can use this to read the current position and dimension of an object, if
you e.g. need it to pop up some requester below.

Of course, this attribute is only valid when the parent window of the object
is currently open.

### SEE ALSO
[MUIA_TopEdge](MUI_Area.md/#MUIA_TopEdge), [MUIA_Width](MUI_Area.md/#MUIA_Width), [MUIA_Height](MUI_Area.md/#MUIA_Height), [MUIA_LeftEdge](MUI_Area.md/#MUIA_LeftEdge), [MUIA_BottomEdge](MUI_Area.md/#MUIA_BottomEdge)

## MUIA_Selected
### NAME
[MUIA_Selected](MUI_Area.md/#MUIA_Selected) -- V4 [ISG], `BOOL`, 0x8042654b

### FUNCTION
Get and set the selected state of a gadget. This attribute can be triggered
by the user clicking on the gadget (or using the keyboard), depending on the
input mode:

MUIV_InputMode_RelVerify:
   - set when lmb is pressed.
   - cleared when lmb is released.
   - cleared when the gadget is selected and the mouse leaves the gadget
     box.
   - set when the mouse reenters the gadget box.

MUIV_InputMode_Immediate:
   - set when lmb is pressed.

MUIV_InputMode_Toggle:
   - toggled when lmb is pressed.

Of course you may set this attribute yourself, e.g. to adjust the state of a
checkmark gadget.

A selected gadget will display its border reverse and get the configured
MUII_SelectedBack background. This can be avoided using the
[MUIA_ShowSelState](MUI_Area.md/#MUIA_ShowSelState) tag.

### SEE ALSO
[MUIA_Pressed](MUI_Area.md/#MUIA_Pressed), [MUIA_Timer](MUI_Area.md/#MUIA_Timer), [MUIA_ShowSelState](MUI_Area.md/#MUIA_ShowSelState), [MUIA_InputMode](MUI_Area.md/#MUIA_InputMode)

## MUIA_ShortHelp
### NAME
[MUIA_ShortHelp](MUI_Area.md/#MUIA_ShortHelp) -- V11 [ISG], `STRPTR`, 0x80428fe3

### FUNCTION
Specify a string that is to be used as bubble help for this object.

### SEE ALSO
[MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp), [MUIM_DeleteShortHelp](MUI_Area.md/#MUIM_DeleteShortHelp), [MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble),
[MUIM_DeleteBubble](MUI_Area.md/#MUIM_DeleteBubble)

## MUIA_ShowMe
### NAME
[MUIA_ShowMe](MUI_Area.md/#MUIA_ShowMe) -- V4 [ISG], `BOOL`, 0x80429ba8

### FUNCTION
Objects with this attribute set are not displayed. You can set [MUIA_ShowMe](MUI_Area.md/#MUIA_ShowMe)
at any time, causing objects to appear and to disappear immediately. A new
layout is calculated whenever some objects are shown or hidden. When
necessary, MUI will resize the parent window to make room for the new
objects.

### NOTES
Currently, MUI does a complete window refresh after showing/hiding objects.
This behaviour might get improved in the future.

Do not confuse this attribute with any kind of "visibility" of an object,
i.e. on a currently not active page of a register group. get()ing
[MUIA_ShowMe](MUI_Area.md/#MUIA_ShowMe) will just return the last set value or the default (TRUE).

## MUIA_ShowSelState
### NAME
[MUIA_ShowSelState](MUI_Area.md/#MUIA_ShowSelState) -- V4 [I..], `BOOL`, 0x8042caac

### FUNCTION
Normally a gadget will reverse its frame and display the configured
MUII_SelectedBack background pattern in its selected state. For some objects
(e.g. checkmarks) this is not recommended and can be supressed by setting
[MUIA_ShowSelState](MUI_Area.md/#MUIA_ShowSelState) to FALSE.

### SEE ALSO
[MUIA_Selected](MUI_Area.md/#MUIA_Selected)

## MUIA_TextColor
### NAME
[MUIA_TextColor](MUI_Area.md/#MUIA_TextColor) -- V22 [..G], `ULONG`, 0x8042dba6

### FUNCTION
Returns the RGB color without alpha channel (00RRGGBB) information of the text
associated with the object. This value is valid between [MUIM_Setup](MUI_Area.md/#MUIM_Setup) and
[MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup) only, otherwise it returns 0.

Do not cache this value and read it once per [MUIM_Draw](MUI_Area.md/#MUIM_Draw) call to support online
prefs changes.

## MUIA_Timer
### NAME
[MUIA_Timer](MUI_Area.md/#MUIA_Timer) -- V4 [..G], `LONG`, 0x80426435

### FUNCTION
[MUIA_Timer](MUI_Area.md/#MUIA_Timer) gets triggered when a relverify button is pressed and (after a
little delay) increases every INTUITICK as long as the mouse remains over
the gadget.

This makes it possible to have buttons repeatedly cause some actions, just
like the arrow gadgets of a scrollbar.

### EXAMPLE
```c++
DoMethod(btmore, MUIM_Notify, MUIA_Timer, MUIV_EveryTime,
  app, 2,
  MUIM_Application_ReturnID, ID_MORE);

DoMethod(btless, MUIM_Notify, MUIA_Timer, MUIV_EveryTime,
  app, 2,
  MUIM_Application_ReturnID, ID_LESS);
```

### SEE ALSO
[MUIA_Pressed](MUI_Area.md/#MUIA_Pressed), [MUIA_Selected](MUI_Area.md/#MUIA_Selected)

## MUIA_TopEdge
### NAME
[MUIA_TopEdge](MUI_Area.md/#MUIA_TopEdge) -- V4 [..G], `LONG`, 0x8042509b

### FUNCTION
You can use this to read the current position and dimension of an object, if
you e.g. need it to pop up some requester below.

Of course, this attribute is only valid when the parent window of the object is
currently open.

### SEE ALSO
[MUIA_LeftEdge](MUI_Area.md/#MUIA_LeftEdge), [MUIA_Width](MUI_Area.md/#MUIA_Width), [MUIA_Height](MUI_Area.md/#MUIA_Height), [MUIA_RightEdge](MUI_Area.md/#MUIA_RightEdge), [MUIA_BottomEdge](MUI_Area.md/#MUIA_BottomEdge)

## MUIA_VertDisappear
### NAME
[MUIA_VertDisappear](MUI_Area.md/#MUIA_VertDisappear) -- V11 [ISG], `LONG`, 0x8042d12f

### FUNCTION
Objects with a disappear level disappear automatically when their parent
window gets too small to display them. Use this for things that make your
GUI look nicer (e.g. Imagery) but are not absolutely necessary.

By using disappearing objects, you can make nice GUIs which still work on
crappy 640x200 screens.

You can give horizontal or vertical disappear levels to objects which are
used for horizontal or vertical layout calculations respectively.

Objects with a small disappear level disappear before objects with a big
disappear level.

### SEE ALSO
[MUIA_HorizDisappear](MUI_Area.md/#MUIA_HorizDisappear)

## MUIA_VertWeight
### NAME
[MUIA_VertWeight](MUI_Area.md/#MUIA_VertWeight) -- V4 [ISG], `WORD`, 0x804298d0

### FUNCTION
Adjust the vertical weight of an object. Usually you can simply use
[MUIA_Weight](MUI_Area.md/#MUIA_Weight) instead of this tag but in some two-dimensional groups it may
become handy to have different horizontal and vertical weights.

### SEE ALSO
[MUIA_Weight](MUI_Area.md/#MUIA_Weight)

## MUIA_Weight
### NAME
[MUIA_Weight](MUI_Area.md/#MUIA_Weight) -- V4 [I..], `WORD`, 0x80421d1f

### FUNCTION
This tag is a shorthand for [MUIA_HorizWeight](MUI_Area.md/#MUIA_HorizWeight) and [MUIA_VertWeight](MUI_Area.md/#MUIA_VertWeight), it sets
both weights at once.

The weight of an object determines how much room it will get during the
layout process. Imagine you have a 100 pixel wide horizontal group with two
string gadgets. Usually, each gadget will get half of the room and be 50
pixels wide. If you feel the left gadget is more important and should be
bigger, you can give it a weight of 200 (and 100 for the right gadget).
Because the left gadget is twice as "heavy" as the right gadget, it will
become twice as big (about 66 pixel) as the right one (34 pixel).

Of course giving weights only makes sense if the object is resizable. A
[MUIA_VertWeight](MUI_Area.md/#MUIA_VertWeight) for a (always fixed height) string gadget is useless.

An object with a weight of 0 will always stay at its minimum size.

By default, all objects have a weight of 100.

### EXAMPLE
```c++
HGroup,
  StringGadget, MUIA_Weight,  50, End,
  StringGadget, MUIA_Weight, 100, End,
  StringGadget, MUIA_Weight, 200, End,
  End;
```

### SEE ALSO
[MUIA_HorizWeight](MUI_Area.md/#MUIA_HorizWeight), [MUIA_VertWeight](MUI_Area.md/#MUIA_VertWeight)

## MUIA_Width
### NAME
[MUIA_Width](MUI_Area.md/#MUIA_Width) -- V4 [..G], `LONG`, 0x8042b59c

### FUNCTION
You can use this to read the current position and dimension of an object, if
you e.g. need it to pop up some requester below.

Of course, this attribute is only valid when the parent window of the object
is currently open.

### SEE ALSO
[MUIA_TopEdge](MUI_Area.md/#MUIA_TopEdge), [MUIA_LeftEdge](MUI_Area.md/#MUIA_LeftEdge), [MUIA_Height](MUI_Area.md/#MUIA_Height), [MUIA_RightEdge](MUI_Area.md/#MUIA_RightEdge), [MUIA_BottomEdge](MUI_Area.md/#MUIA_BottomEdge)

## MUIA_Window
### NAME
[MUIA_Window](MUI_Area.md/#MUIA_Window) -- V4 [..G], `struct Window *`, 0x80421591

### FUNCTION
This attribute can be used to get a pointer to the intuition window
structure of the parent window of the object. This pointer could e.g. be
used in calls to asl.library.

The result is only valid when the window is opened.

Alternatively the macro _window() can be used with the restriction that the
returned window pointer is valid between [MUIM_Show](MUI_Area.md/#MUIM_Show) and [MUIM_Hide](MUI_Area.md/#MUIM_Hide) only.

### SEE ALSO
[MUIA_Window_Window](MUI_Window.md/#MUIA_Window_Window)

## MUIA_WindowObject
### NAME
[MUIA_WindowObject](MUI_Area.md/#MUIA_WindowObject) -- V4 [..G], `Object *`, 0x8042669e

### FUNCTION
You can obtain a pointer to the window object that some gadget belongs to by
using this attribute. Useful mainly within callback hooks if you do not want
to deal with global variables.

Alternatively the macro _win() can be used with the restriction that the
returned object pointer is valid between [MUIM_Setup](MUI_Area.md/#MUIM_Setup) and [MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup) only.

### SEE ALSO
[MUIA_ApplicationObject](MUI_Notify.md/#MUIA_ApplicationObject)

## MUIM_AskMinMax
### NAME
[MUIM_AskMinMax](MUI_Area.md/#MUIM_AskMinMax) -- V4, 0x80423874
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_AskMinMax, struct MUI_MinMax *MinMaxInfo);`

### FUNCTION
see developer documentation.

### INPUTS
**`struct MUI_MinMax *MinMaxInfo`**
     a pointer to a MUI_MinMax structure to be filled with the required
     minimum, default and maximum dimensions.

## MUIM_Cleanup
### NAME
[MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup) -- V4, 0x8042d985
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_Cleanup);`

### FUNCTION
see developer documentation.

## MUIM_ContextMenuAdd
### NAME
[MUIM_ContextMenuAdd](MUI_Area.md/#MUIM_ContextMenuAdd) -- V20, 0x8042df9e

### SYNOPSIS
`DoMethod(obj, MUIM_ContextMenuAdd, Object *menustrip, LONG mx, LONG my, LONG *mxp, LONG *myp);`

### FUNCTION
Allows dynamic creation of context menus. When MUI is about to show a new
context menu, it does not simply use the [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) field of Area
class. Instead, it sends a [MUIM_ContextMenuAdd](MUI_Area.md/#MUIM_ContextMenuAdd) to the object in question to
let it add its own context menu items to the given menustrip object.

When [MUIM_ContextMenuAdd](MUI_Area.md/#MUIM_ContextMenuAdd) reaches Area class, it will pass this method to its
parent object, if it exists.

However, if your context menus depend on some internal states of your object
or on the mouse position within your object, you have to build a subclass
which implements [MUIM_ContextMenuAdd](MUI_Area.md/#MUIM_ContextMenuAdd) and adds some items to the menustrip
object.

### INPUTS
**`Object *menustrip`**
      a MenuStrip object to add your own Menu objects to.

**`LONG mx`**
     current x position of mouse.

**`LONG my`**
     current y position of mouse.

**`LONG *mxp`**
     pointer to mx.

**`LONG *myp`**
     pointer to my.

Since MUI does (unfortunately) not use relative coordinates at all, these
two aren't relative either.

By modifying the values in mxp and myp you can let the menu appear at a
different position.

### EXAMPLE
```c++
// create the menu
if((data->menu = MenuObject, MUIA_Menu_Title, "Columns", End) != NULL)
{
  DoMethod(data->menu, OM_ADDMEMBER, MenuitemObject,
    MUIA_Menuitem_Title, "Show all",
  End);
  DoMethod(data->menu, OM_ADDMEMBER, MenuitemObject,
    MUIA_Menuitem_Title, "Reset sizes",
  End);

  // add the menu to the menustrip
  DoMethod(msg->menustrip, OM_ADDMEMBER, data->menu);
}
```

### NOTES
Although MUI will dispose the object you create, you should nevertheless
remember it in your class' instance data for later reference during
[MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice).

Even when implementing [MUIM_ContextMenuAdd](MUI_Area.md/#MUIM_ContextMenuAdd), you **MUST** set [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu)
of your object to something different from NULL. MUI will find out that your
object actually has a popup menu by directly checking the contents of
[MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) in the instance data of Area class due to speed reasons.

Do not forget to OM_ADDMEMBER the created items to the given menustrip
objects, otherwise the user will never see those items!

### EXAMPLE
```c++
struct Data
{
  Object *menu;
  [...]
};

ULONG m_MyClass_ContextMenuAdd(struct IClass *cl, Object *obj,
                               struct MUIP_ContextMenuAdd *msg)
{
  struct Data *data = INST_DATA(cl, obj);

  if((data->menu = MenuObject, MUIA_Menu_Title, "my title", FALSE,
    Child, MenuitemObject,
      MUIA_Menuitem_Title, "my item",
      MUIA_UserData, 1001,
      End,
    [...]
  End) != NULL)
  {
    // very important, add your own menu to the supplied menu strip
    DoMethod(msg->menustrip, OM_ADDMEMBER, data->menu);
  }

  // let your superclass possibly add further own menu items
  return DoSuperMethodA(cl, obj, (Msg)msg);
}

ULONG m_MyClass_ContextMenuChoice(struct IClass *cl, Object *obj,
                                  struct MUIP_ContextMenuChoice *msg)
{
  struct Data *data = INST_DATA(cl, obj);
  ULONG rc = 0;

  // make sure the menu still exists and the item belongs to our menu
  if(data->menu != NULL && DoMethod(data->menu, MUIM_FindObject, msg->item))
  {
    switch(muiUserData(msg->item))
    {
      case 1001:
      {
        // do your desired actions
      }
      break;
    }
  }
  else
  {
    // let the superclass handle its own menus
    rc = DoSuperMethodA(cl, obj, (Msg)msg);
  }

  // forget the menu object, it will be disposed with the menustrip
  data->menu = NULL;

  return rc;
}
```

### SEE ALSO
[MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild), [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu), [MUIA_ContextMenuTrigger](MUI_Area.md/#MUIA_ContextMenuTrigger),
[MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice)

## MUIM_ContextMenuBuild
### NAME
[MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild) -- V11, 0x80429d2e

### SYNOPSIS
`DoMethod(obj, MUIM_ContextMenuBuild, LONG mx, LONG my);`

### FUNCTION
OBSOLETE - USE [MUIM_ContextMenuAdd](MUI_Area.md/#MUIM_ContextMenuAdd) in new code.

old documentation:
Allows dynamic creation of context menus. When MUI is about to show a new
context menu, it does not simply use the [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) field of Area
class. Instead, it sends a [MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild) to the object in question
and uses the return value as the new menustrip object.

When [MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild) reaches Area class, it just returns the contents
of [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) so you don't need to care about this method if you only
have static, non-changing context menus.

However, if your context menus depend on some internal states of your object
or on the mouse position within your object, you have to build a subclass
which overrides [MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild), creates a nice menustrip object and
returns it.

### INPUTS
**`LONG mx`**
     current x position of mouse.

**`LONG my`**
     current y position of mouse.

Since MUI does (unfortunately) not use relative coordinates at all, these
two aren't relative either.

### RESULT
If you return a pointer to a menustrip object, MUI will show it as popup
menu.

If you return the special value MUIV_ContextMenuBuild_Default, MUI will show
the window's default menu instead. This is e.g. recommended for classes that
only want popup menus on certain mouse positions.

If you return NULL, nothing will happen. This is for compatibility for
pre-MUI4 applications which used [MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild) to detect the right
mouse button. This is no longer recommended. With MUI4 and its event
handlers, you can simply handle RMB just like LMB.

### NOTES
MUI will never dispose the object you return. You must take care of this
yourself, e.g. by storing a pointer somewhere in your instance data and
killing it on the next invocation of [MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild) or on
OM_DISPOSE.

Even when implementing [MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild), you **MUST** set
[MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) of your object to something different from NULL. MUI will
find out that your object actually has a popup menu by directly checking the
contents of [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) in the instance data of area class due to speed
reasons.

### SEE ALSO
[MUIM_ContextMenuAdd](MUI_Area.md/#MUIM_ContextMenuAdd), [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu), [MUIA_ContextMenuTrigger](MUI_Area.md/#MUIA_ContextMenuTrigger),
[MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice)

## MUIM_ContextMenuChoice
### NAME
[MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice) -- V11, 0x80420f0e

### SYNOPSIS
`DoMethod(obj, MUIM_ContextMenuChoice, Object *item);`

### FUNCTION
Allows reacting on context menus in subclasses.

See [MUIA_ContextMenu](MUI_Area.md/#MUIA_ContextMenu) for details.

### INPUTS
**`Object *item`**
     the selected menu item.

### SEE ALSO
[MUIA_ContextMenuTrigger](MUI_Area.md/#MUIA_ContextMenuTrigger), [MUIM_ContextMenuChoice](MUI_Area.md/#MUIM_ContextMenuChoice), [MUIM_ContextMenuBuild](MUI_Area.md/#MUIM_ContextMenuBuild)

## MUIM_CreateBubble
### NAME
[MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble) -- V18, 0x80421c41

### SYNOPSIS
`DoMethod(obj, MUIM_CreateBubble, LONG x, LONG y, CONST_STRPTR txt, ULONG flags);`

### FUNCTION
Together with [MUIM_DeleteBubble](MUI_Area.md/#MUIM_DeleteBubble), this method provides an interface for MUI's
bubble mechanism. Applications can use bubbles for their own purpose, e.g.
for indicating error conditions on certain gadgets.

[MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble) creates a bubble at the specified coordinates with the
specified (textual) contents. It returns a bubble "handle" that has to be
passed to [MUIM_DeleteBubble](MUI_Area.md/#MUIM_DeleteBubble) when the bubble shall disappear.

There's no limitation on the number of bubbles, you can create lots of them
at a time if you wish. Also, these custom bubbles are completely independant
of MUI's bubble help system and won't disappear automatically when the mouse
is moved.

Note that bubbles will only show up when the object in question is visible.
Otherwise [MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble) returns NULL. You are responsible for deleting
the bubble **before** the object becomes invisible. Good place to remove a
custom bubble is e.g. the [MUIM_Hide](MUI_Area.md/#MUIM_Hide) method of your object.

### INPUTS
**`LONG x`**
     window-relative X coordinate of the bubble.

**`LONG y`**
     window-relative Y coordinate of the bubble.

**`CONST_STRPTR txt`**
     custom text for the bubble. If you pass NULL here, MUI will query
     the object with [MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp) method for a text (like the
     automatic help system does).

**`ULONG flags`**
     - MUIV_CreateBubble_DontHidePointer:
       prevents MUI from hiding the mouse pointer when displaying the help
       bubble. It is recommended that you always set this, unless your bubble
       is meant to disappear as soon as there is some user input.

### RESULT
This method returns a pointer to a (black box) bubble handle or NULL on
failure. You have to pass the bubble handle to [MUIM_DeleteBubble](MUI_Area.md/#MUIM_DeleteBubble) if you want
to delete the bubble later.

### SEE ALSO
[MUIM_DeleteBubble](MUI_Area.md/#MUIM_DeleteBubble), [MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp), [MUIM_DeleteShortHelp](MUI_Area.md/#MUIM_DeleteShortHelp),
[MUIA_ShortHelp](MUI_Area.md/#MUIA_ShortHelp)

## MUIM_CreateDragImage
### NAME
[MUIM_CreateDragImage](MUI_Area.md/#MUIM_CreateDragImage) -- V18, 0x8042eb6f
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_CreateDragImage, LONG touchx, LONG touchy, ULONG flags);`

### FUNCTION
Overriding this method allows you to set up a custom image to be used during
drap&dDrop operations. The default image is the object's visible imagery at
the time the drag&drop operation starts.

### INPUTS
**`LONG touchx`**
     x-distance between "click point" and object coordinates.

**`LONG touchy`**
     y-distance between "click point" and object coordinates.

**`ULONG flags`**
     none defined yet, must be 0 for now.

### RESULT
You must return a pointer to a struct MUI_DragImage or NULL if you failed to
create one. MUI will abort the drag&drop operation if you return either NULL
or the bitmap pointer is NULL.

### EXAMPLE
[MUIM_CreateDragImage](MUI_Area.md/#MUIM_CreateDragImage) method:
```c++
struct MUI_DragImage *di;
if((di = AllocVec(sizeof(struct MUI_DragImage), MEMF_CLEAR)) != NULL)
{
  if((bi->bm = AllocBitMap(_width(obj), _height(obj), 8, BMF_CLEAR, NULL) != NULL)
  {
    // paint something fancy into the bitmap
    <...>
    // fill the MUI_DragImage structure with sensible values
    di->width  = _width(obj);
    di->height = _height(obj);
    di->touchx = msg->touchx;
    di->touchy = msg->touchy;
    // if you need an additional mask plane put the pointer to it here
    // and set the MUIF_DRAGIMAGE_HASMASK flag.
    di->flags = 0;
    di->mask = NULL;
    return di;
  }
  // bitmap allocation failed
  FreeVec(di);
}
// signal failure
return NULL;
```

[MUIM_DeleteDragImage](MUI_Area.md/#MUIM_DeleteDragImage) method:
```c++
FreeBitMap(di->bm);
FreeVec(di);
```

### SEE ALSO
[MUIM_DeleteDragImage](MUI_Area.md/#MUIM_DeleteDragImage)

## MUIM_CreateShortHelp
### NAME
[MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp) -- V11, 0x80428e93

### SYNOPSIS
`DoMethod(obj, MUIM_CreateShortHelp, LONG mx, LONG my);`

### FUNCTION
Allows dynamic creation of help bubble texts.

When MUI is about to show a help bubble, it does not simply use the
[MUIA_ShortHelp](MUI_Area.md/#MUIA_ShortHelp) field of area class. Instead, it sends a [MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp)
method to the object in question and uses the return value as text for the
bubble.

When [MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp) reaches Area class, it just returns the contents
of [MUIA_ShortHelp](MUI_Area.md/#MUIA_ShortHelp), so you needn't care about this method if you only have
static, non-changing help bubbles.

However, if your help bubble texts depend on some internal states of your
objects or on the mouse position within your objects, you have to create a
subclass which overrides [MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp), creates a custom text string
and returns it.

You can dynamically allocate memory here. MUI will call the method
[MUIM_DeleteShortHelp](MUI_Area.md/#MUIM_DeleteShortHelp) after the bubble has disappeared to give you a chance
to free this memory again.

### INPUTS
**`LONG mx`**
     current x position of mouse.

**`LONG my`**
     current y position of mouse.

Since MUI does (unfortunately) not use relative coordinates at all, these
two aren't relative either.

### RESULT
You must return a pointer to a string or NULL if you failed to create one.
MUI will not show any bubble at all if you return NULL, so you can use this
to selectively supply bubble help only on certain areas of your object.

### NOTES
This method is sent by MUI. Never send it yourself.

MUI will not free the string you return. You must take care of this
yourself, e.g. by using static text or by freeing anything you allocated in
the following [MUIM_DeleteShortHelp](MUI_Area.md/#MUIM_DeleteShortHelp) method.

Even when overriding [MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp), you **MUST** set [MUIA_ShortHelp](MUI_Area.md/#MUIA_ShortHelp) of
your object to something different from NULL. MUI will find out that your
object actually has a bubble help by directly checking the contents of
[MUIA_ShortHelp](MUI_Area.md/#MUIA_ShortHelp) in the instance data of Area class due to speed reasons.

### EXAMPLE
Suggested use is something like

```c++
obj = NewObject(..., MUIA_ShortHelp, TRUE, ...);
```

and then override these methods in obj's class.

```c++
ULONG MUIM_CreateShortHelp(...)
{
  STRPTR help;
  int mx = msg->mx;
  int my = msg->my;

  mx -= _mleft(obj); // make coordinates relative
  my -= _mtop(obj);

  // no bubble at all if mouse is in a 10 pixel
  // wide x-region at the edge of the object.
  if (mx < 10 || mx > _mwidth(obj)-10)
     return(NULL);

  // allocate space for bubble text
  if((help = AllocVec(300, MEMF_ANY)) == NULL)
     return (ULONG)NULL;

  // fill help string with some dynamic text
  sprintf(help, "Yahoo... very dynamic... %ld %ld", mx, my);

  return (ULONG)help;
}

ULONG MUIM_DeleteShortHelp(...)
{
  FreeVec(msg->help);
  return 0;
}
```

### SEE ALSO
[MUIM_DeleteShortHelp](MUI_Area.md/#MUIM_DeleteShortHelp), [MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble), [MUIM_DeleteBubble](MUI_Area.md/#MUIM_DeleteBubble), [MUIA_ShortHelp](MUI_Area.md/#MUIA_ShortHelp)

## MUIM_DeleteBubble
### NAME
[MUIM_DeleteBubble](MUI_Area.md/#MUIM_DeleteBubble) -- V18, 0x804211af

### SYNOPSIS
`DoMethod(obj, MUIM_DeleteBubble, APTR bubble);`

### FUNCTION
Together with [MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble), this method provides an interface for MUI's
bubble mechanism. Applications can use bubbles for their own purpose, e.g.
for indicating error conditions on certain gadgets.

[MUIM_DeleteBubble](MUI_Area.md/#MUIM_DeleteBubble) deletes a bubble that was previously created with
[MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble). Note that bubbles have to be deleted before an object
becomes invisible!

### INPUTS
**`APTR bubble`**
     pointer to black box bubble handle as returned by [MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble).

### RESULT
The bubble will be removed. The return value is undefined.

### SEE ALSO
[MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble), [MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp), [MUIM_DeleteShortHelp](MUI_Area.md/#MUIM_DeleteShortHelp)

## MUIM_DeleteDragImage
### NAME
[MUIM_DeleteDragImage](MUI_Area.md/#MUIM_DeleteDragImage) -- V18, 0x80423037
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_DeleteDragImage, struct MUI_DragImage *di);`

### FUNCTION
Free all stuff allocated during [MUIM_CreateDragImage](MUI_Area.md/#MUIM_CreateDragImage).

### INPUTS
**`struct MUI_DragImage *di`**
     the MUI_DragImage structure to be freed.

### SEE ALSO
[MUIM_CreateDragImage](MUI_Area.md/#MUIM_CreateDragImage)

## MUIM_DeleteShortHelp
### NAME
[MUIM_DeleteShortHelp](MUI_Area.md/#MUIM_DeleteShortHelp) -- V11, 0x8042d35a

### SYNOPSIS
`DoMethod(obj, MUIM_DeleteShortHelp, STRPTR help);`

### FUNCTION
Delete the string that [MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp) might have allocated.

MUI will call this method if you returned a custom text in
[MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp) when the bubble has disappeared.

You can free memory that you allocated for the dynamic bubble text here.

### INPUTS
**`STRPTR help`**
     the STRPTR you previously returned in [MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp).

### RESULT
Return NULL in every case.

### SEE ALSO
[MUIM_CreateShortHelp](MUI_Area.md/#MUIM_CreateShortHelp), [MUIM_CreateBubble](MUI_Area.md/#MUIM_CreateBubble), [MUIM_DeleteBubble](MUI_Area.md/#MUIM_DeleteBubble), [MUIA_ShortHelp](MUI_Area.md/#MUIA_ShortHelp)

## MUIM_DoDrag
### NAME
[MUIM_DoDrag](MUI_Area.md/#MUIM_DoDrag) -- V20, 0x804216bb

### SYNOPSIS
`DoMethod(obj, MUIM_DoDrag, LONG touchx, LONG touchy, ULONG flags);`

### FUNCTION
This method invokes MUI's drag & drop handling. Normally, MUI takes care
about this itself when objects are specified as draggable. However, if you
e.g. have a whole group of objects that should be dragged (like a toolbar)
and just a small "handle" button to start this operation, you must use this
method.

### INPUTS
**`LONG touchx`**
     x-distance between "click point" and object coordinates.
     Using the special value 0x80000000 will make MUI use
     window->MouseX - _left(obj)

**`LONG touchy`**
     y-distance between "click point" and object coordinates.
     Using the special value 0x80000000 will make MUI use
     window->MouseY - _top(obj)

**`ULONG flags`**
     none defined yet, must be 0 for now.

### EXAMPLE
```c++
Child, toolbar = HGroup,
  Child, draghandle = SimpleButton("dragme"),
  Child, SimpleButton("toolbutton1"),
  Child, SimpleButton("toolbutton2"),
  Child, SimpleButton("toolbutton3"),
  Child, SimpleButton("toolbutton4"),
  End,

DoMethod(draghandle, MUIM_Notify, MUIA_Pressed, TRUE,
  toolbar, 4,
  MUIM_DoDrag, 0x80000000, 0x80000000, 0);
```

### SEE ALSO
[MUIA_Draggable](MUI_Area.md/#MUIA_Draggable), [MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin), [MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery), [MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish),
[MUIM_DragReport](MUI_Area.md/#MUIM_DragReport), [MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop)

## MUIM_DragBegin
### NAME
[MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin) -- V11, 0x8042c03a

### SYNOPSIS
`DoMethod(obj, MUIM_DragBegin, Object *obj);`

### FUNCTION
Inform an object that it has become the active destination of a drag&drop
action. An object will only receive this if it has responded positively to a
previous [MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery).

### SEE ALSO
[MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery), [MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish), [MUIM_DragReport](MUI_Area.md/#MUIM_DragReport), [MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop)

## MUIM_DragDrop
### NAME
[MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop) -- V11, 0x8042c555

### SYNOPSIS
`DoMethod(obj, MUIM_DragDrop, Object *obj, LONG x, LONG y, ULONG qualifier);`

### FUNCTION
Indicate that the user dropped something on the current object.

### SEE ALSO
[MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin), [MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish), [MUIM_DragReport](MUI_Area.md/#MUIM_DragReport), [MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery)

## MUIM_DragEvent
### NAME
[MUIM_DragEvent](MUI_Area.md/#MUIM_DragEvent) -- V20, 0x8042b774
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_DragEvent, struct Window *objwindow, Object *obj, struct MUI_DragImage *di, struct IntuiMessage *imsg, LONG muikey, ULONG mouseptrtype, ULONG flags);`

### FUNCTION
Query the source object of a drag&drop operation for further actions.
Overloading this method makes it possible to change the drag images while
the drag&drop operation is still in progress or to change the mouse pointer
image.

### INPUTS
**`struct Window *objwindow`**
     a pointer to the window the mouse pointer is currently
     hovering over. This may be a foreign window. If your
     application is able to handle drops outside the application
     you must set the flag MUIF_DRAGEVENT_FOREIGNDROP in the flags
     field.

**`Object *obj`**
     the current destination object. May be NULL if there is
     currently no object within the application to accept the
     drag&drop operation.

**`struct MUI_DragImage *di`**
     a pointer to a struct MUI_DragImage. If you wish to change
     the drag image during the drag&drop operation provide a
     pointer to a new drag image here. You must also set the
     MUIF_DRAGEVENT_REDRAW flag in the flags field to let MUI
     accept this change.

**`struct IntuiMessage *imsg`**
     a pointer to the current IntuiMessage.

**`LONG muikey`**
     the current standard MUI key.

**`ULONG mouseptrtype`**
     set this field to the pointer type you want MUI to use during
     the drag&drop operation. You must also set the
     MUIF_DRAGEVENT_MOUSECHANGED flag in the flags field to let
     MUI accept this change. Valid values are all
     MUIV_PointerType_#? values, except MUIV_PointerType_Parent,
     as well as pointer image objects created by pointerclass.

**`ULONG flags`**
     flags indicating which of the above fields were changed and
     need to be applied to the drag&drop process. Currently these
     flags exists:
       * MUIF_DRAGEVENT_REDRAW: set by the overloader in case the
         MUI_DragImage was modified during [MUIM_DragEvent](MUI_Area.md/#MUIM_DragEvent).
       * MUIF_DRAGEVENT_FOREIGNDROP: set by the overloader in case
         it can drop to a foreign window, the actual drop must be
         implemented in the Application's [MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop) method.
       * MUIF_DRAGEVENT_MOUSECHANGED: set by the overloader to
         force a custom mouse pointer instead of the one picked by
         MUI.

### SEE ALSO
[MUIA_PointerType](MUI_Area.md/#MUIA_PointerType)

## MUIM_DragFinish
### NAME
[MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish) -- V11, 0x804251f0

### SYNOPSIS
`DoMethod(obj, MUIM_DragFinish, Object *obj, LONG dropfollows);`

### FUNCTION
Indicate that an object is no longer the active destination object of a
drag&drop action.

### INPUTS
**`Object *obj`**
     the source object being dragged.

**`LONG dropfollows`**
     a flag indicating whether a [MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop) message will follow
     for the receiving object.

### SEE ALSO
[MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery), [MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin), [MUIM_DragReport](MUI_Area.md/#MUIM_DragReport), [MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop)

## MUIM_DragQuery
### NAME
[MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery) -- V11, 0x80420261

### SYNOPSIS
`DoMethod(obj, MUIM_DragQuery, Object *obj);`

### FUNCTION
MUI offers complete drag & drop capabilities for every object. If enabled,
the user is able to grab an object, drag it around and drop it on another
object. Currently, D&D is limited to single applications, i.e. you cannot
take an object from one program and drop it into another one. D&D between
different windows of the same application, however, is fine.

MUI controls the D&D actions with a set of five methods: [MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery),
[MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin), [MUIM_DragReport](MUI_Area.md/#MUIM_DragReport), [MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop) and [MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish).
Basically things work this way:

Let's assume the user has taken an object (called the source object) and is
now starting to drag it around. During dragging, MUI will find out which
object is currently under the mouse pointer and if it found one, send it the
[MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery) method. An object that receives [MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery) can now
determine it it wishes to accept drops from the source object or not. If it
responds positively, the object will become the current destination object.

Due to the nature of MUIs layout system, a specific x,y pair of coordinates
cannot be bound to a specific object immediately. Instead, the coordinates
belong to a whole tree of objects, for example some cycle gadget, its parent
group, the parent group of the parent group and so on until the tree reaches
the windows root object. To allow complete groups of objects to participate
in D&D business, the [MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery) is first sent to the deepest nested
object (the cycle gadget in the example above). If this one doesn't respond,
MUI sends a [MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery) to its parent group and so on until it either
finds some object which accepts the drop or reaches the end of the tree. If
there is an accepting object, it will become the current destination. If
there isn't one, no destination will be set.

Objects becoming active destinations of a drag process learn about their
current state by receiving a [MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin) method. This method, when
reaching area class, e.g. draws a special frame around the object to
indicate the current state to the user.

The opposite of [MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin) is [MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish) and will be sent as soon
as the object stops being destination of the drag process, i.e. because the
user aborted the drag or moved out of the bounding box. [MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish)
will also be sent after a successful drop, you can rely on receiving a
[MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish) if you received a [MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin) before. Furthermore, only
one object will be between [MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin) and [MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish) at any time.

Active destination objects (between [MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin) and [MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish))
receive [MUIM_DragReport](MUI_Area.md/#MUIM_DragReport) methods as long as the user moves the mouse within
the object. [MUIM_DragReport](MUI_Area.md/#MUIM_DragReport) contains the mouse coordinates, so the object
can update its display according to the position of the source object. A
listview would e.g. indicate the insert position to give the user an idea
where the source would be inserted in case of a drop.

All the methods mentioned above are just interim messages that help
visualizing the drag process. When the user actually decides to drop its
source object, the current destination object (if any) receives a
[MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop) method and can perform whatever operation it thinks is suited
to handle a D&D action from the source object.

You probably have noticed that D&D is controlled by methods. This means that
you need to write subclasses if you intend to use it. However, you don't
need to implement all the above mentioned things to reach your goal. In
fact, [MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery) and [MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop) are enough for almost all D&D
invocations. Here's a little example of how MUI implements D&D between
objects of Pendisplay class. These few lines allow the user to take any
Pendisplay (or subclasses from Pendisplay like e.g. Poppen class) and drop
it onto another one:

```c++
ULONG mDragQuery(struct IClass *cl, Object *obj, struct MUIP_DragQuery *msg)
{
  char *spec;

  /* refuse to be dropped on ourself */
  if(msg->obj == obj)
    return MUIV_DragQuery_Refuse;

  /* if the source object offers the attribute */
  /* we want, show that we would accept it. */
  if(get(msg->obj, MUIA_Pendisplay_Spec, &spec))
    return MUIV_DragQuery_Accept;

  /* refuse otherwise */
  return MUIV_DragQuery_Refuse;
}

ULONG mDragDrop(struct IClass *cl, Object *obj, struct MUIP_DragDrop *msg)
{
  char *spec;

  /* copy the attribute from the source object */
  get(msg->obj, MUIA_Pendisplay_Spec, &spec);
  set(obj, MUIA_Pendisplay_Spec, spec);

  return 0;
}
```

### INPUTS
**`Object *obj`**
     the source object being dragged.

### SEE ALSO
[MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin), [MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish), [MUIM_DragReport](MUI_Area.md/#MUIM_DragReport), [MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop)

## MUIM_DragReport
### NAME
[MUIM_DragReport](MUI_Area.md/#MUIM_DragReport) -- V11, 0x8042edad

### SYNOPSIS
`DoMethod(obj, MUIM_DragReport, Object *obj, LONG x, LONG y, LONG update, ULONG qualifier);`

### FUNCTION
Interim messages from MOUSEMOVEs and INTUITICKs sent as long as an object is
active destination of a drag&drop action.

### INPUTS
**`Object *obj`**
     the source object being dragged.

**`LONG x`**
     the current mouse X position.

**`LONG y`**
     the current mouse Y position.

**`LONG update`**
     a flag indicating whether this method is called again due to e
     previous call returning MUIV_DragReport_Refresh.

**`ULONG qualifier`**
     the currently active input qualifiers.

### SEE ALSO
[MUIM_DragQuery](MUI_Area.md/#MUIM_DragQuery), [MUIM_DragFinish](MUI_Area.md/#MUIM_DragFinish), [MUIM_DragBegin](MUI_Area.md/#MUIM_DragBegin), [MUIM_DragDrop](MUI_Area.md/#MUIM_DragDrop)

## MUIM_Draw
### NAME
[MUIM_Draw](MUI_Area.md/#MUIM_Draw) -- V4, 0x80426f3f
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_Draw, ULONG flags);`

### FUNCTION
see developer documentation.

### INPUTS
**`ULONG flags`**
     define how the object is to be redrawn. Can be one of
       * MADF_DRAWOBJECT
         draw the full object
       * MADF_DRAWUPDATE
         do a possibly partitial redraw only

## MUIM_DrawBackground
### NAME
[MUIM_DrawBackground](MUI_Area.md/#MUIM_DrawBackground) -- V11, 0x804238ca

### SYNOPSIS
`DoMethod(obj, MUIM_DrawBackground, LONG left, LONG top, LONG width, LONG height, LONG xoffset, LONG yoffset, LONG flags);`

### FUNCTION
If you decided to use [MUIA_FillArea](MUI_Area.md/#MUIA_FillArea), FALSE for your custom class, i.e. if
you care about background rendering yourself, you can use this method to
draw a specific part of your objects background with the defined
[MUIA_Background](MUI_Area.md/#MUIA_Background).

### INPUTS
**`LONG left`**
     left coordinate of the rectangle to be drawn, make sure to add
     your object's _mleft coordinates.

**`LONG top`**
     top coordinate of the rectangle to be drawn, make sure to add
     your object's _mtop coordinates.

**`LONG width`**
     width of the rectangle to be drawn.

**`LONG height`**
     height of the rectangle to be drawn.

**`LONG xoffset`**
     offset to use when background is a pattern.

**`LONG yoffset`**
     offset to use when background is a pattern.

**`LONG flags`**
     none defined yet, set to 0 for now.

### RESULT
The result value of this method is currently undefined.

### SEE ALSO
[MUIA_Background](MUI_Area.md/#MUIA_Background)

## MUIM_DrawBackgroundParent
### NAME
[MUIM_DrawBackgroundParent](MUI_Area.md/#MUIM_DrawBackgroundParent) -- V20, 0x804240e7

### SYNOPSIS
`DoMethod(obj, MUIM_DrawBackgroundParent, LONG left, LONG top, LONG width, LONG height, LONG brightness, LONG xoffset, LONG yoffset, LONG flags);`

### FUNCTION
Just like [MUIM_DrawBackground](MUI_Area.md/#MUIM_DrawBackground) to fill the object's background with the
defined background image this method will do same except that the parent
object's background image will be used instead. This allows to modify the
brightness of the parent object's background image.

### INPUTS
**`LONG left`**
     left coordinate of the rectangle to be drawn, make sure to add
     your object's _mleft coordinates.

**`LONG top`**
     top coordinate of the rectangle to be drawn, make sure to add
     your object's _mtop coordinates.

**`LONG width`**
     width of the rectangle to be drawn.

**`LONG height`**
     height of the rectangle to be drawn.

**`LONG brightness`**
     adjust the parent object background's brightness by the given
     percentage (-100%...+100%).

**`LONG xoffset`**
     offset to use when background is a pattern.

**`LONG yoffset`**
     offset to use when background is a pattern.

**`LONG flags`**
     none defined yet, set to 0 for now.

### RESULT
The result value of this method is currently undefined.

### SEE ALSO
[MUIM_DrawBackground](MUI_Area.md/#MUIM_DrawBackground)

## MUIM_GoActive
### NAME
[MUIM_GoActive](MUI_Area.md/#MUIM_GoActive) -- V8, 0x8042491a
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_GoActive, ULONG flags);`

### FUNCTION
Tells the object to switch to its active state. For example, this makes a String
object show its text input cursor.

### INPUTS
**`ULONG flags`**
     Flags bit mask, currently unused.

## MUIM_GoInactive
### NAME
[MUIM_GoInactive](MUI_Area.md/#MUIM_GoInactive) -- V8, 0x80422c0c
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_GoInactive, ULONG flags);`

### FUNCTION
Tells the object to switch to its inactive state. For example, this makes a
String object hide its text input cursor.

### INPUTS
**`ULONG flags`**
     Flags bit mask, currently unused.

## MUIM_HandleEvent
### NAME
[MUIM_HandleEvent](MUI_Area.md/#MUIM_HandleEvent) -- V16, 0x80426d66
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_HandleEvent, struct IntuiMessage *imsg, LONG muikey, struct MUI_EventHandlerNode *ehn);`

### FUNCTION
This method is invoked whenever one of an event handler's trigger signals
arrives. It's described in Area class context but does not really belong
here.

### INPUTS
**`struct IntuiMessage *imsg`**
     pointer to a struct IntuiMessage that caused the event. Note well
     that this may be NULL in which case you simply not parse imsg.

**`LONG muikey`**
     if the imsg translates to a predefined keystroke, this parameter
     holds the corresponding MUIKEY_XXXX value. Otherwise it will be
     MUIKEY_NONE.

**`struct MUI_EventHandlerNode *ehn`**
     a pointer to the MUI_EventHandlerNode which caused this method to
     be called.

### NOTES
You must not rely on imsg being non-NULL, regardless whether muikey is set
or unset.

Do NOT pass this method to your superclass by calling DoSuperMethod(). This
method is meant for your class only. If your superclass wants to handle certain
input events it MUST install an event handler itself.

### RESULT
The result is a bitfield. Currently, only one bit is defined:

- MUI_EventHandlerRC_Eat
  Set this if this event was for you and you want MUI to stop calling other
  event handlers in the chain.

All other bits are reserved for future use and must be zero!

### SEE ALSO
[MUIM_Window_AddEventHandler](MUI_Window.md/#MUIM_Window_AddEventHandler), [MUIM_Window_RemEventHandler](MUI_Window.md/#MUIM_Window_RemEventHandler)

## MUIM_HandleInput
### NAME
[MUIM_HandleInput](MUI_Area.md/#MUIM_HandleInput) -- V4, 0x80422a1a
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_HandleInput, struct IntuiMessage *imsg, LONG muikey);`

### FUNCTION
see developer documentation.

### INPUTS
**`struct IntuiMessage *imsg`**
     pointer to a struct IntuiMessage that caused the event. Note well
     that this may be NULL in which case you simply not parse imsg.

**`LONG muikey`**
     if the imsg translates to a predefined keystroke, this parameter
     holds the corresponding MUIKEY_XXXX value. Otherwise it will be
     MUIKEY_NONE.

## MUIM_Hide
### NAME
[MUIM_Hide](MUI_Area.md/#MUIM_Hide) -- V4, 0x8042f20f
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_Hide);`

### FUNCTION
see developer documentation.

## MUIM_Layout
### NAME
[MUIM_Layout](MUI_Area.md/#MUIM_Layout) -- V4, 0x8042845b

### SYNOPSIS
`DoMethod(obj, MUIM_Layout, LONG left, LONG top, LONG width, LONG height, ULONG flags);`

### FUNCTION
Since version 11 of muimaster.library, you have the ability to customize the way
objects are placed in a group. Altough MUI features a very powerful builtin
layout algorithm which serves well for almost all GUI related purposes, it might
sometimes become handy to override this with custom code.

Imagine you want to build a multimedia document viewer which contains text
objects, bitmap objects and buttons. An easy way for doing this is to simply
create a subclass of group class which contains all the documents elements as
MUI objects and which specifies a custom layout hook for the parent group. This
hook is then responsible for placing the objects within the bounds of the parent
group.

Implementing [MUIM_Layout](MUI_Area.md/#MUIM_Layout) is basically the same as specifying a layout hook for
groups, but also works for decendants of Area class. Your class is expected to
let the superclass first do its layout stuff and afterwards place your own
children in the rectangle _mleft(obj)/_mtop(obj)/_mright(obj)/_mbottom(obj)
using MUI_Layout().

### INPUTS
**`LONG left`**
     final left coordinate of the object.

**`LONG top`**
     final top coordinate of the object.

**`LONG width`**
     final width of the object.

**`LONG height`**
     final height of the object.

**`ULONG flags`**
     none defined yet, set to 0.

### EXAMPLE
see MUI demo program Layout.c

### SEE ALSO
muimaster.library/MUI_Layout(), [MUIA_Group_LayoutHook](MUI_Group.md/#MUIA_Group_LayoutHook)

## MUIM_Relayout
### NAME
[MUIM_Relayout](MUI_Area.md/#MUIM_Relayout) -- V22, 0x8042b381

### SYNOPSIS
`DoMethod(obj, MUIM_Relayout, ULONG flags);`

### FUNCTION
Perform a full relayout of the object in case it is visible. Actually the
object will be completely hidden and shown again to trigger a full redraw
as well.

### INPUTS
**`ULONG flags`**
     none defined yet, set to 0.

### RESULT
A boolean value indicating whether the relayout succeeded or not.

### SEE ALSO
[MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup), [MUIM_Hide](MUI_Area.md/#MUIM_Hide), [MUIM_Setup](MUI_Area.md/#MUIM_Setup), [MUIM_Show](MUI_Area.md/#MUIM_Show)

## MUIM_Setup
### NAME
[MUIM_Setup](MUI_Area.md/#MUIM_Setup) -- V4, 0x80428354
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_Setup, struct MUI_RenderInfo *RenderInfo);`

### FUNCTION
see developer documentation.

### INPUTS
**`struct MUI_RenderInfo *RenderInfo`**
     a pointer to the object's MUI_RenderInfo structure.

## MUIM_Show
### NAME
[MUIM_Show](MUI_Area.md/#MUIM_Show) -- V4, 0x8042cc84
[For use within custom classes only]

### SYNOPSIS
`DoMethod(obj, MUIM_Show, struct LongRect *clip);`

### FUNCTION
see developer documentation.

### INPUTS
**`struct LongRect *clip`**
     the rectangle which contains the area to be shown.

## MUIM_Text
### NAME
[MUIM_Text](MUI_Area.md/#MUIM_Text) -- V20, 0x8042ee70

### SYNOPSIS
`DoMethod(obj, MUIM_Text, LONG left, LONG top, LONG width, LONG height, CONST_STRPTR text, LONG len, CONST_STRPTR preparse, LONG ulchar);`

### FUNCTION
This function is a preferred way to render text inside the object. It uses
the object's font and it's color (if not specified in the string itself).

### INPUTS
**`LONG left`**
     rectangle to render the text into.

**`LONG top`**
     rectangle to render the text into.

**`LONG width`**
     rectangle to render the text into.

**`LONG height`**
     rectangle to render the text into.

**`CONST_STRPTR text`**
     the text to be rendered.

**`LONG len`**
     the number of characters to be respected, pass -1 to render the
     full string.

**`CONST_STRPTR preparse`**
     an optional preparse string, may be NULL.

**`LONG ulchar`**
     character to be underlined (i.e. as shortcut), pass 0 for no
     underlining.

### NOTES
All facilities of MUI's text engine are allowed for both the text and the
preparse string. Refer to [MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents) for all possible sequences.

Make sure to specify a rectangle which resides in the object's area,
otherwise the object's frame might be overdrawn.

It is recommended to calculate the text's dimensions via [MUIM_TextDim](MUI_Area.md/#MUIM_TextDim), i.e.
during [MUIM_AskMinMax](MUI_Area.md/#MUIM_AskMinMax), to ensure that the text is fully visible and will not
be drawn beyond the object's area.

### EXAMPLE
```c++
/* show "foo bar" centered in a 150x20 rectangle at x=10, y=10 within the */
/* object's area */
/* the 'b' of 'bar' will be underlined */
DoMethod(obj, MUIM_Text, _mleft(obj)+10, _mtop(obj)+10, 150, 20,
         "foo bar", -1, "\033c", 'b');
```

### SEE ALSO
[MUIM_TextDim](MUI_Area.md/#MUIM_TextDim), [MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents), [MUIA_Text_PreParse](MUI_Text.md/#MUIA_Text_PreParse)

## MUIM_TextDim
### NAME
[MUIM_TextDim](MUI_Area.md/#MUIM_TextDim) -- V20, 0x80422ad7

### SYNOPSIS
`DoMethod(obj, MUIM_TextDim, CONST_STRPTR text, LONG len, CONST_STRPTR preparse, ULONG flags);`

### FUNCTION
Use this function to measure the area which will be required to render a
text of the given length.

All facilities of MUI's text engine are allowed for both the text and the
preparse string. Refer to [MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents) for all possible sequences.

### INPUTS
**`CONST_STRPTR text`**
     the text to be measured.

**`LONG len`**
     the number of characters to be respected, pass -1 to measure the
     full string.

**`CONST_STRPTR preparse`**
     an optional preparse string, may be NULL.

**`ULONG flags`**
     currently unused, pass 0.

### RESULT
A 32bit value combined of the calculated width and height of the text
string. Use the DIM2WIDTH() and DIM2HEIGHT() macros to extract the width and
height values.

### SEE ALSO
[MUIM_Text](MUI_Area.md/#MUIM_Text), [MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents), [MUIA_Text_PreParse](MUI_Text.md/#MUIA_Text_PreParse)

## MUIM_UpdateConfig
### NAME
[MUIM_UpdateConfig](MUI_Area.md/#MUIM_UpdateConfig) -- V20, 0x8042b0a9

### SYNOPSIS
`DoMethod(obj, MUIM_UpdateConfig, ULONG cfgid, LONG redrawcount, Object *redrawobj[64], UBYTE redrawflags[64]);`

### FUNCTION
This is the central method of MUI's real time prefs. This method will be
called whenever the user changed a configuration item in MUI's prefs
application. It is your task to react accordingly to this change to give a
visual feedback about the change (i.e. redraw yourself). See Animals demo
for details.

### INPUTS
**`ULONG cfgid`**
     ID of the modified configuration item.

## MUIM_WhichPointerType
### NAME
[MUIM_WhichPointerType](MUI_Area.md/#MUIM_WhichPointerType) -- V20, 0x8042e212

### SYNOPSIS
`DoMethod(obj, MUIM_WhichPointerType, LONG mx, LONG my);`

### FUNCTION
Return a mouse pointer type for complex objects depending on the current
mouse position.

### INPUTS
**`LONG mx`**
     current x position of mouse.

**`LONG my`**
     current y position of mouse.

### RESULT
Return the value of the mouse pointer type to be used at the given
coordinates. You may return all possible types including custom pointer
images created by pointerclass.

### EXAMPLE
A detailed example can be found in the source code of the Pointers demo
application.

### SEE ALSO
[MUIA_PointerType](MUI_Area.md/#MUIA_PointerType)

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
