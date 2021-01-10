# Application.mui
## Super class
[Notify.mui](MUI_Notify.md)
## Background
Application class is the master class for all MUI applications. It serves as
a kind of anchor for all input, either coming from the user or somewhere
from the system, e.g. commodities or ARexx messages.

An application can have any number of sub windows, these windows are the
children of the application.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Application_Active](MUI_Application.md/#MUIA_Application_Active)|V4|ISG|`BOOL`
[MUIA_Application_Author](MUI_Application.md/#MUIA_Application_Author)|V4|I.G|`STRPTR`
[MUIA_Application_Base](MUI_Application.md/#MUIA_Application_Base)|V4|I.G|`STRPTR`
[MUIA_Application_Broker](MUI_Application.md/#MUIA_Application_Broker)|V4|..G|`CxObj *`
[MUIA_Application_BrokerHook](MUI_Application.md/#MUIA_Application_BrokerHook)|V4|ISG|`struct Hook *`
[MUIA_Application_BrokerPort](MUI_Application.md/#MUIA_Application_BrokerPort)|V6|..G|`struct MsgPort *`
[MUIA_Application_BrokerPri](MUI_Application.md/#MUIA_Application_BrokerPri)|V6|I.G|`LONG`
[MUIA_Application_Commands](MUI_Application.md/#MUIA_Application_Commands)|V4|ISG|`struct MUI_Command *`
[MUIA_Application_Copyright](MUI_Application.md/#MUIA_Application_Copyright)|V4|I.G|`STRPTR`
[MUIA_Application_Description](MUI_Application.md/#MUIA_Application_Description)|V4|I.G|`STRPTR`
[MUIA_Application_DiskObject](MUI_Application.md/#MUIA_Application_DiskObject)|V4|ISG|`struct DiskObject *`
[MUIA_Application_DoubleStart](MUI_Application.md/#MUIA_Application_DoubleStart)|V4|..G|`BOOL`
[MUIA_Application_DropObject](MUI_Application.md/#MUIA_Application_DropObject)|V5|IS.|`Object *`
[MUIA_Application_ForceQuit](MUI_Application.md/#MUIA_Application_ForceQuit)|V8|.SG|`BOOL`
[MUIA_Application_HelpFile](MUI_Application.md/#MUIA_Application_HelpFile)|V8|ISG|`STRPTR`
[MUIA_Application_Iconified](MUI_Application.md/#MUIA_Application_Iconified)|V4|.SG|`BOOL`
[MUIA_Application_IconifyTitle](MUI_Application.md/#MUIA_Application_IconifyTitle)|V18|ISG|`STRPTR`
[MUIA_Application_Menu](MUI_Application.md/#MUIA_Application_Menu)|V4|I.G|`struct NewMenu *` **(OBSOLETE)**
[MUIA_Application_MenuAction](MUI_Application.md/#MUIA_Application_MenuAction)|V4|..G|`ULONG`
[MUIA_Application_MenuHelp](MUI_Application.md/#MUIA_Application_MenuHelp)|V4|..G|`ULONG`
[MUIA_Application_Menustrip](MUI_Application.md/#MUIA_Application_Menustrip)|V8|I.G|`Object *`
[MUIA_Application_RexxHook](MUI_Application.md/#MUIA_Application_RexxHook)|V7|ISG|`struct Hook *`
[MUIA_Application_RexxMsg](MUI_Application.md/#MUIA_Application_RexxMsg)|V4|..G|`struct RxMsg *`
[MUIA_Application_RexxString](MUI_Application.md/#MUIA_Application_RexxString)|V4|.S.|`STRPTR`
[MUIA_Application_SingleTask](MUI_Application.md/#MUIA_Application_SingleTask)|V4|I..|`BOOL`
[MUIA_Application_Sleep](MUI_Application.md/#MUIA_Application_Sleep)|V4|.SG|`BOOL`
[MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title)|V4|I.G|`STRPTR`
[MUIA_Application_UseCommodities](MUI_Application.md/#MUIA_Application_UseCommodities)|V10|I..|`BOOL`
[MUIA_Application_UsedClasses](MUI_Application.md/#MUIA_Application_UsedClasses)|V20|ISG|`STRPTR *`
[MUIA_Application_UseRexx](MUI_Application.md/#MUIA_Application_UseRexx)|V10|I..|`BOOL`
[MUIA_Application_UseScreenNotify](MUI_Application.md/#MUIA_Application_UseScreenNotify)|V20|I..|`BOOL`
[MUIA_Application_Version](MUI_Application.md/#MUIA_Application_Version)|V4|I.G|`STRPTR`
[MUIA_Application_Window](MUI_Application.md/#MUIA_Application_Window)|V4|I..|`Object *`
[MUIA_Application_WindowList](MUI_Application.md/#MUIA_Application_WindowList)|V13|..G|`struct List *`

## Methods
Method|Version
------|-------
[MUIM_Application_AboutMUI](MUI_Application.md/#MUIM_Application_AboutMUI)|V14
[MUIM_Application_AddInputHandler](MUI_Application.md/#MUIM_Application_AddInputHandler)|V11
[MUIM_Application_BuildSettingsPanel](MUI_Application.md/#MUIM_Application_BuildSettingsPanel)|V20
[MUIM_Application_CheckRefresh](MUI_Application.md/#MUIM_Application_CheckRefresh)|V11
[MUIM_Application_DefaultConfigItem](MUI_Application.md/#MUIM_Application_DefaultConfigItem)|V20
[MUIM_Application_Execute](MUI_Application.md/#MUIM_Application_Execute)|V20
[MUIM_Application_GetMenuCheck](MUI_Application.md/#MUIM_Application_GetMenuCheck)|V4 **(OBSOLETE)**
[MUIM_Application_GetMenuState](MUI_Application.md/#MUIM_Application_GetMenuState)|V4 **(OBSOLETE)**
[MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input)|V4 **(OBSOLETE)**
[MUIM_Application_InputBuffered](MUI_Application.md/#MUIM_Application_InputBuffered)|V4
[MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load)|V4
[MUIM_Application_NewInput](MUI_Application.md/#MUIM_Application_NewInput)|V11
[MUIM_Application_OpenConfigWindow](MUI_Application.md/#MUIM_Application_OpenConfigWindow)|V11
[MUIM_Application_PushMethod](MUI_Application.md/#MUIM_Application_PushMethod)|V4
[MUIM_Application_RemInputHandler](MUI_Application.md/#MUIM_Application_RemInputHandler)|V11
[MUIM_Application_ReturnID](MUI_Application.md/#MUIM_Application_ReturnID)|V4
[MUIM_Application_Run](MUI_Application.md/#MUIM_Application_Run)|V20
[MUIM_Application_Save](MUI_Application.md/#MUIM_Application_Save)|V4
[MUIM_Application_SetConfigItem](MUI_Application.md/#MUIM_Application_SetConfigItem)|V11
[MUIM_Application_SetMenuCheck](MUI_Application.md/#MUIM_Application_SetMenuCheck)|V4 **(OBSOLETE)**
[MUIM_Application_SetMenuState](MUI_Application.md/#MUIM_Application_SetMenuState)|V4 **(OBSOLETE)**
[MUIM_Application_ShowHelp](MUI_Application.md/#MUIM_Application_ShowHelp)|V4
[MUIM_Application_UnpushMethod](MUI_Application.md/#MUIM_Application_UnpushMethod)|V20

## MUIA_Application_Active
### NAME
[MUIA_Application_Active](MUI_Application.md/#MUIA_Application_Active) -- V4 [ISG], `BOOL`, 0x804260ab

### FUNCTION
This attribute reflects the state that the user adjusted with commodities
Exchange. MUI itself doesn't pay any attention to it, this is up to you.

### SEE ALSO
[MUIA_Application_Broker](MUI_Application.md/#MUIA_Application_Broker)

## MUIA_Application_Author
### NAME
[MUIA_Application_Author](MUI_Application.md/#MUIA_Application_Author) -- V4 [I.G], `STRPTR`, 0x80424842

### FUNCTION
Name of the application's author.

### EXAMPLE
see [MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title)

### SEE ALSO
[MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title), [MUIA_Application_Copyright](MUI_Application.md/#MUIA_Application_Copyright),
[MUIA_Application_Version](MUI_Application.md/#MUIA_Application_Version), [MUIA_Application_Description](MUI_Application.md/#MUIA_Application_Description),
[MUIA_Application_Base](MUI_Application.md/#MUIA_Application_Base)

## MUIA_Application_Base
### NAME
[MUIA_Application_Base](MUI_Application.md/#MUIA_Application_Base) -- V4 [I.G], `STRPTR`, 0x8042e07a

### FUNCTION
The basename for an application. This name is used for the builtin ARexx
port and for some internal file management.

A basename must neither contain spaces nor any special characters such as
":/()#?*...".

When your program is a single task application (i.e.
[MUIA_Application_SingleTask](MUI_Application.md/#MUIA_Application_SingleTask) is TRUE), the base name will be used without
further modification.

Otherwise, it gets a ".1", ".2", etc. appended, depending on how many
applications are already running. If you need to know the name of your
ARexx port, you can query the base name attribute after the application is
created.

### EXAMPLE
see [MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title)

### SEE ALSO
[MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title), [MUIA_Application_Version](MUI_Application.md/#MUIA_Application_Version), [MUIA_Application_Author](MUI_Application.md/#MUIA_Application_Author),
[MUIA_Application_Copyright](MUI_Application.md/#MUIA_Application_Copyright), [MUIA_Application_Description](MUI_Application.md/#MUIA_Application_Description)

## MUIA_Application_Broker
### NAME
[MUIA_Application_Broker](MUI_Application.md/#MUIA_Application_Broker) -- V4 [..G], `CxObj *`, 0x8042dbce

### FUNCTION
If you need to attach some additional commodities objects to your
application (e.g. because you need lots of hotkeys), you can obtain a
pointer to the application's Broker structure and add some commodities
objects.

MUI will free the complete broker when the application is disposed, no need
for you to free your objects yourself.

To receive input from your objects, you will also need to install a
[MUIA_Application_BrokerHook](MUI_Application.md/#MUIA_Application_BrokerHook).

### NOTES
You must be prepared to receive a NULL pointer. In this case, the
commodities interface is not available, maybe because the user installed a
light version of MUI.

### SEE ALSO
[MUIA_Application_BrokerHook](MUI_Application.md/#MUIA_Application_BrokerHook)

## MUIA_Application_BrokerHook
### NAME
[MUIA_Application_BrokerHook](MUI_Application.md/#MUIA_Application_BrokerHook) -- V4 [ISG], `struct Hook *`, 0x80428f4b

### FUNCTION
You specify a pointer to hook structure. The function will be called
whenever a commodities message arrives (between MUI's GetMsg() and
ReplyMsg()).

You receive a pointer to the application object as object in A2 and a
pointer to commodities CxMsg message in A1.

### NOTES
The commodities interface isn't available in the memory saving "light"
version of MUI. Your hook will never be called in this case.

### SEE ALSO
[MUIA_Application_Broker](MUI_Application.md/#MUIA_Application_Broker)

## MUIA_Application_BrokerPort
### NAME
[MUIA_Application_BrokerPort](MUI_Application.md/#MUIA_Application_BrokerPort) -- V6 [..G], `struct MsgPort *`, 0x8042e0ad

### FUNCTION
Get a pointer to the application's commodities message port. If you want to
add own Hotkeys to your application, you need a message port. Instead of
creating your own, you should better use this one.

### NOTES
You must be prepared to receive a NULL pointer. In this case, the
commodities interface is not available, maybe because the user installed a
light version of MUI.

### SEE ALSO
[MUIA_Application_BrokerHook](MUI_Application.md/#MUIA_Application_BrokerHook)

## MUIA_Application_BrokerPri
### NAME
[MUIA_Application_BrokerPri](MUI_Application.md/#MUIA_Application_BrokerPri) -- V6 [I.G], `LONG`, 0x8042c8d0

### FUNCTION
Adjust the priority of an application's broker.

### SEE ALSO
[MUIA_Application_BrokerHook](MUI_Application.md/#MUIA_Application_BrokerHook)

## MUIA_Application_Commands
### NAME
[MUIA_Application_Commands](MUI_Application.md/#MUIA_Application_Commands) -- V4 [ISG], `struct MUI_Command *`, 0x80428648

### FUNCTION
This attribute allows an application to include its own set of ARexx
commands. You specify a pointer to an array of MUI_Command structures, which
look like this:

```c++
struct MUI_Command
{
  char        *mc_Name;
  char        *mc_Template;
  LONG         mc_Parameters;
  struct Hook *mc_Hook;
  LONG         mc_Reserved[5];
};
```

**`mc_Name`**
     contains the name of your command. Commands are not case sensitive.

**`mc_Template`**
     an argument template that follows the same rules as
     dos.library/ReadArgs(). It may be NULL, in which case your
     command doesn't need any parameters.

**`mc_Parameters`**
     the number of parameters specified in the template array.

**`mc_Hook`**
     a pointer to the callback hook defining the function to be called.

You may specify any number of MUI_Command structures, but you must terminate
your array with a NULL field.

When a command shows up an application's ARexx port, MUI parses the arguments
according to the given template and calls the hook with the application
object as hook object in A2 and a pointer to an array of longwords
containing the parameters in A1.

The result code of your hook will be replied to ARexx as return code.

If you have some simple ARexx commands that just emulate some user action
(e.g. clicking a button), you can use the magic cookie MC_TEMPLATE_ID for
mc_Template and a return ID value for mc_Parameters. In this case, MUI will
do no argument parsing and instead simply return the specified ID value on
the next call to [MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input).

For more sophisticated possibilities in ARexx callback hooks, please refer
to [MUIA_Application_RexxMsg](MUI_Application.md/#MUIA_Application_RexxMsg) and [MUIA_Application_RexxString](MUI_Application.md/#MUIA_Application_RexxString).

### EXAMPLE
```c++
static struct MUI_Command commands[] =
{
  { "rescan", MC_TEMPLATE_ID, ID_RESCAN, NULL     },
  { "select", "PATTERN/A"   , 1        , &selhook },
  { NULL    , NULL          , NULL     , NULL     }
};
```

### SEE ALSO
[MUIA_Application_RexxMsg](MUI_Application.md/#MUIA_Application_RexxMsg), [MUIA_Application_RexxString](MUI_Application.md/#MUIA_Application_RexxString)

## MUIA_Application_Copyright
### NAME
[MUIA_Application_Copyright](MUI_Application.md/#MUIA_Application_Copyright) -- V4 [I.G], `STRPTR`, 0x8042ef4d

### FUNCTION
A copyright string, containing the year and the company.

### EXAMPLE
see [MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title)

### SEE ALSO
[MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title), [MUIA_Application_Version](MUI_Application.md/#MUIA_Application_Version), [MUIA_Application_Author](MUI_Application.md/#MUIA_Application_Author),
[MUIA_Application_Description](MUI_Application.md/#MUIA_Application_Description), [MUIA_Application_Base](MUI_Application.md/#MUIA_Application_Base)

## MUIA_Application_Description
### NAME
[MUIA_Application_Description](MUI_Application.md/#MUIA_Application_Description) -- V4 [I.G], `STRPTR`, 0x80421fc6

### FUNCTION
Short description, about 40 characters. Shown e.g. in commodities exchange.

### EXAMPLE
see [MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title)

### SEE ALSO
[MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title), [MUIA_Application_Version](MUI_Application.md/#MUIA_Application_Version), [MUIA_Application_Author](MUI_Application.md/#MUIA_Application_Author),
[MUIA_Application_Copyright](MUI_Application.md/#MUIA_Application_Copyright), [MUIA_Application_Base](MUI_Application.md/#MUIA_Application_Base)

## MUIA_Application_DiskObject
### NAME
[MUIA_Application_DiskObject](MUI_Application.md/#MUIA_Application_DiskObject) -- V4 [ISG], `struct DiskObject *`, 0x804235cb

### FUNCTION
Pointer to a struct DiskObject, e.g. obtained from GetDiskObject(). If
present, MUI will use this object for the AppIcon when your application
gets iconified.

Otherwise MUI will try to locate "env:sys/dev_mui.info" and, if not present,
fall back to a default icon.

### EXAMPLE
```c++
dobj = GetDiskObject("PROGDIR:MyApp");
...
MUIA_Application_DiskObject, dobj,
...

/* note that you have to free dobj yourself! */
```

### SEE ALSO
[MUIA_Application_Iconified](MUI_Application.md/#MUIA_Application_Iconified)

## MUIA_Application_DoubleStart
### NAME
[MUIA_Application_DoubleStart](MUI_Application.md/#MUIA_Application_DoubleStart) -- V4 [..G], `BOOL`, 0x80423bc6

### FUNCTION
This attribute is set automatically when the user tries to start a
[MUIA_Application_SingleTask](MUI_Application.md/#MUIA_Application_SingleTask) application twice. You can react on this and
take appropriate actions, e.g. pop up a requester or quit yourself.

### SEE ALSO
[MUIA_Application_SingleTask](MUI_Application.md/#MUIA_Application_SingleTask)

## MUIA_Application_DropObject
### NAME
[MUIA_Application_DropObject](MUI_Application.md/#MUIA_Application_DropObject) -- V5 [IS.], `Object *`, 0x80421266

### FUNCTION
If your application is iconified and the user drops icons onto the AppIcon,
the object specified here will receive the AppMessage.

### SEE ALSO
[MUIA_Window_AppWindow](MUI_Window.md/#MUIA_Window_AppWindow), [MUIM_CallHook](MUI_Notify.md/#MUIM_CallHook)

## MUIA_Application_ForceQuit
### NAME
[MUIA_Application_ForceQuit](MUI_Application.md/#MUIA_Application_ForceQuit) -- V8 [.SG], `BOOL`, 0x804257df

### FUNCTION
When your input loop receives a MUIV_Application_ReturnID_Quit, you should
query this attribute. In case its TRUE, your program should exit quietly
without popping up any safety requesters or other stuff.

MUI will e.g. set this if the user issued a "QUIT FORCE" ARexx command to
your application.

## MUIA_Application_HelpFile
### NAME
[MUIA_Application_HelpFile](MUI_Application.md/#MUIA_Application_HelpFile) -- V8 [ISG], `STRPTR`, 0x804293f4

### FUNCTION
This attribute allows defining an AmigaGuide style file to be displayed when
the user requests online help.

When the HELP button is pressed and the application defines a
[MUIA_Application_HelpFile](MUI_Application.md/#MUIA_Application_HelpFile), MUI tries to obtain [MUIA_HelpNode](MUI_Notify.md/#MUIA_HelpNode) from the
current object (the one under the mouse pointer). If [MUIA_HelpNode](MUI_Notify.md/#MUIA_HelpNode) is not
defined, MUI continues asking the parent object for this attribute (usually
a group, but remember: the parent of a windows root object is the window
itself, the parent of a window is the application).

When a non NULL [MUIA_HelpNode](MUI_Notify.md/#MUIA_HelpNode) is found, the same procedure is applied to
[MUIA_HelpLine](MUI_Notify.md/#MUIA_HelpLine). Then MUI puts the application to sleep and displays the file
at the position specified with [MUIA_HelpNode](MUI_Notify.md/#MUIA_HelpNode) and/or [MUIA_HelpLine](MUI_Notify.md/#MUIA_HelpLine).

This behaviour allows you to define one [MUIA_Application_HelpFile](MUI_Application.md/#MUIA_Application_HelpFile) for your
application object  and different help nodes and lines for your
application's windows and/or gadgets.

### EXAMPLE
```c++
ApplicationObject,
  ...
  MUIA_Application_HelpFile, "progdir:myapp.guide",
  ...,
  SubWindow, WindowObject,
    MUIA_Window_Title, "Prefs Window",
    ...,
    MUIA_HelpNode, "prefs-section",
    ...,
    End,

  SubWindow, WindowObject,
    MUIA_Window_Title, "Play Window",
    ...
    MUIA_HelpNode, "play-section",
    ...
    WindowContents, VGroup,
      ...,
      Child, StringObject,
        MUIA_HelpNode, "play-string",
        ...,
        End,
      End,
    End,
  End;
```

In this case, the user will get the prefs-section chapter of "myapp.guide"
when he requests help in the Prefs window, the play-string chapter when he
requests help over the string gadget in the Play window or the play-section
chapter somewhere else in the Play window.

### NOTES
Since muimaster.library V8, this attribute replaces the old and obsolete
[MUIA_HelpFile](MUI_Notify.md/#MUIA_HelpFile) attribute. MUI no longer supports the possibility to specify
different help files for different parts of your application. This step was
necessary due to some other internal changes and enhancements.

### SEE ALSO
[MUIA_HelpNode](MUI_Notify.md/#MUIA_HelpNode), [MUIA_HelpLine](MUI_Notify.md/#MUIA_HelpLine)

## MUIA_Application_Iconified
### NAME
[MUIA_Application_Iconified](MUI_Application.md/#MUIA_Application_Iconified) -- V4 [.SG], `BOOL`, 0x8042a07f

### FUNCTION
Setting this attribute to TRUE causes the application to become iconified.
Every open window will be closed and a (configurable) AppIcon will appear
on the workbench.

Same thing happens when the user hits the iconify gadget in the window
border or uses commodities Exchange to hide your application's interface.

There is no way for you to prevent your application from being iconified.
However, you can react on the iconification by listening to the
[MUIA_Application_Iconified](MUI_Application.md/#MUIA_Application_Iconified) attribute with notification. This allows you to
free some resources you don't need in iconified state.

When an application is iconified and you try to open a window, the window
won't open immediately. Instead MUI remembers this action and opens the
window once the application is uniconified again.

### EXAMPLE
```c++
/* inform the main input loop of iconification events */

#define ID_HIDE 42
#define ID_SHOW 24

DoMethod(app,MUIM_Notify,
  MUIA_Application_Iconified, TRUE,
  app, 2, MUIM_Application_ReturnID, ID_HIDE);

DoMethod(app,MUIM_Notify,
  MUIA_Application_Iconified, FALSE,
  app, 2, MUIM_Application_ReturnID, ID_SHOW);
```

### SEE ALSO
[MUIA_Application_DiskObject](MUI_Application.md/#MUIA_Application_DiskObject)

## MUIA_Application_IconifyTitle
### NAME
[MUIA_Application_IconifyTitle](MUI_Application.md/#MUIA_Application_IconifyTitle) -- V18 [ISG], `STRPTR`, 0x80422cb8

### FUNCTION
Setting this attribute lets you use a different name than the application's
title for the iconification icon and/or menu. The supplied name will be copied
internally.

Defaults to the same name as supplied for [MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title).

### SEE ALSO
[MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title)

## MUIA_Application_Menu
### NAME
[MUIA_Application_Menu](MUI_Application.md/#MUIA_Application_Menu) -- V4 [I.G], `struct NewMenu *`, 0x80420e1f **(OBSOLETE)**

### FUNCTION
Obsolete, use [MUIA_Application_Menustrip](MUI_Application.md/#MUIA_Application_Menustrip) instead.

### SEE ALSO
[MUIA_Application_Menustrip](MUI_Application.md/#MUIA_Application_Menustrip)

## MUIA_Application_MenuAction
### NAME
[MUIA_Application_MenuAction](MUI_Application.md/#MUIA_Application_MenuAction) -- V4 [..G], `ULONG`, 0x80428961

### FUNCTION
Whenever a menu item is selected, this attribute will be set to the
corresponding UserData field of the gadtools NewMenu structure. This allows
reacting on menu items via broadcasting.

### SEE ALSO
[MUIA_Application_Menu](MUI_Application.md/#MUIA_Application_Menu), [MUIA_Application_MenuAction](MUI_Application.md/#MUIA_Application_MenuAction)

## MUIA_Application_MenuHelp
### NAME
[MUIA_Application_MenuHelp](MUI_Application.md/#MUIA_Application_MenuHelp) -- V4 [..G], `ULONG`, 0x8042540b

### FUNCTION
Whenever a menu item is selected with the help key, this attribute will be
set to the corresponding UserData field of the gadtools NewMenu structure.
Together with [MUIM_Application_ShowHelp](MUI_Application.md/#MUIM_Application_ShowHelp) this allows creation of menu help
texts.

### SEE ALSO
[MUIA_Application_Menu](MUI_Application.md/#MUIA_Application_Menu), [MUIA_Application_ShowHelp](MUI_Application.md/#MUIA_Application_ShowHelp)

## MUIA_Application_Menustrip
### NAME
[MUIA_Application_Menustrip](MUI_Application.md/#MUIA_Application_Menustrip) -- V8 [I.G], `Object *`, 0x804252d9

### FUNCTION
Specify a menu strip object for the application. The object is treated as a
child of the application and will be disposed when the application is
disposed.

Menustrip objects defined for the application are used as menu for every
window of the application, as long as the window doesn't define its private
menu.

[MUIA_Application_Menustrip](MUI_Application.md/#MUIA_Application_Menustrip) replaces the old and obsolete
[MUIA_Application_Menu](MUI_Application.md/#MUIA_Application_Menu) tag.

Usually, you will create the menu object with MUI's builtin object library
from a gadtools NewMenu structure, but its also OK to define the menu tree
"by hand" using the Family class.

## MUIA_Application_RexxHook
### NAME
[MUIA_Application_RexxHook](MUI_Application.md/#MUIA_Application_RexxHook) -- V7 [ISG], `struct Hook *`, 0x80427c42

### FUNCTION
When specified, MUI calls this hook whenever a rexx message  arrives and MUI
can't map it to a builtin or a programmer specified command. The hook will
be called with a pointer to itself in A0, a pointer to the application
object in A2 and a pointer to a struct RexxMsg in A1.

The return code from the hook is used as result code when replying the
message, the secondary result can be set with [MUIA_Application_RexxString](MUI_Application.md/#MUIA_Application_RexxString).

### SEE ALSO
[MUIA_Application_Commands](MUI_Application.md/#MUIA_Application_Commands)

## MUIA_Application_RexxMsg
### NAME
[MUIA_Application_RexxMsg](MUI_Application.md/#MUIA_Application_RexxMsg) -- V4 [..G], `struct RxMsg *`, 0x8042fd88

### FUNCTION
Within an ARexx callback hook, you can obtain a pointer to the RexxMsg that
came with the command. This allows you to use some ARexx support functions
coming with amiga.lib.

### SEE ALSO
[MUIA_Application_Commands](MUI_Application.md/#MUIA_Application_Commands), [MUIA_Application_RexxString](MUI_Application.md/#MUIA_Application_RexxString)

## MUIA_Application_RexxString
### NAME
[MUIA_Application_RexxString](MUI_Application.md/#MUIA_Application_RexxString) -- V4 [.S.], `STRPTR`, 0x8042d711

### FUNCTION
ARexx allows returning a string as result of a function call. This attribute
allows setting the result string within an ARexx callback hook.

The string is temporarily copied.

### SEE ALSO
[MUIA_Application_Commands](MUI_Application.md/#MUIA_Application_Commands), [MUIA_Application_RexxMsg](MUI_Application.md/#MUIA_Application_RexxMsg)

## MUIA_Application_SingleTask
### NAME
[MUIA_Application_SingleTask](MUI_Application.md/#MUIA_Application_SingleTask) -- V4 [I..], `BOOL`, 0x8042a2c8

### FUNCTION
Boolean value to indicate whether or not your application is a single task
program. When set to TRUE, MUI will refuse to create more than one
application object.

In this case, the already running application gets its
[MUIA_Application_DoubleStart](MUI_Application.md/#MUIA_Application_DoubleStart) attribute set to TRUE. You  can listen to this
and take appropriate actions, e.g. pop up a requester.

Examples for single task applications are the system preferences program.
It doesn't make sense for them to run more than once.

### SEE ALSO
[MUIA_Application_DoubleStart](MUI_Application.md/#MUIA_Application_DoubleStart)

## MUIA_Application_Sleep
### NAME
[MUIA_Application_Sleep](MUI_Application.md/#MUIA_Application_Sleep) -- V4 [.SG], `BOOL`, 0x80425711

### FUNCTION
This attribute can be used to put a whole application to sleep. All open
windows get disabled and a busy pointer appears.

This attribute contains a nesting count, if you tell your application to
sleep twice, you will have to tell it to wake up twice as well.

If you need to do some time consuming actions, you always should set this
attribute to inform the user that you are currently unable to handle input.

A sleeping application's windows cannot be resized.

### NOTES
Only opened windows will be put to sleep. However, leaving the sleep state
will affect all windows regardless of the current open state.

### EXAMPLE
```c++
set(app, MUIA_Application_Sleep, TRUE); // go to bed
calc_fractals();
set(app, MUIA_Application_Sleep, FALSE); // wake up
```

### SEE ALSO
[MUIM_Application_InputBuffered](MUI_Application.md/#MUIM_Application_InputBuffered), [MUIA_Window_Sleep](MUI_Window.md/#MUIA_Window_Sleep)

## MUIA_Application_Title
### NAME
[MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title) -- V4 [I.G], `STRPTR`, 0x804281b8

### FUNCTION
This tag defines the title of an application. The title is e.g. shown in
Commodities Exchange or in the MUI preferences program.

An application title shall not contain any version information, just the
pure title. Also, special characters such as ":/()#?*..." are not allowed.

You should use a quite long and unique name for your applications. Naming it
"Viewer" or "Browser" is not a wise choice.

The length of the name must not exceed 30 characters!

### EXAMPLE
```c++
ApplicationObject,
  MUIA_Application_Title, "WbMan",
  MUIA_Application_Version, "$VER: WbMan 0.24 (19.7.93)",
  MUIA_Application_Copyright, "© 1993 by Klaus Melchior",
  MUIA_Application_Author, "Klaus Melchior",
  MUIA_Application_Description, "Manages the WBStartup.",
  MUIA_Application_Base, "WBMAN",
  ...
```

### SEE ALSO
[MUIA_Application_Version](MUI_Application.md/#MUIA_Application_Version), [MUIA_Application_Copyright](MUI_Application.md/#MUIA_Application_Copyright),
[MUIA_Application_Author](MUI_Application.md/#MUIA_Application_Author), [MUIA_Application_Description](MUI_Application.md/#MUIA_Application_Description), [MUIA_Application_Base](MUI_Application.md/#MUIA_Application_Base)

## MUIA_Application_UseCommodities
### NAME
[MUIA_Application_UseCommodities](MUI_Application.md/#MUIA_Application_UseCommodities) -- V10 [I..], `BOOL`, 0x80425ee5

### FUNCTION
When set to FALSE, the application will run without a commodities interface.
Think very well before using this tag!

### SEE ALSO
[MUIA_Application_UseRexx](MUI_Application.md/#MUIA_Application_UseRexx)

## MUIA_Application_UsedClasses
### NAME
[MUIA_Application_UsedClasses](MUI_Application.md/#MUIA_Application_UsedClasses) -- V20 [ISG], `STRPTR *`, 0x8042e9a7

### FUNCTION
Tell the MUI system what external classes your application might use.

You have to pass a pointer to a NULL terminated string array which lists each of
the external classes used by your application. For example, if your program uses
the Listtree class, add "Listtree.mcc" to the array.

Although MUI does not strictly require this information to run your application,
you should nevertheless make it available. With the aid of this attribute, MUI
will be able to determine which GUI preferences pages should be presented to the
user when he adjusts your application specific MUI settings.

If you do not inform MUI about your external classes, MUI will present lots of
unnecessary pages that won't affect your application at all. Any MUI program
should therefore use this tag.

### NOTES
You only have to supply names of external classes (i.e. classes that end in
".mcc"). There is no need to supply default MUI classes which end in ".mui".
Also, do not specify preferences classes (".mcp") here. MUI can automatically
determine the required preferences classes for each custom class.

If your program does not need any external classes at all, supply an empty
string array:
```c++
static CONST_STRPTR UsedClasses[] = { NULL };
```

### EXAMPLE
```c++
/* application uses Listtree, Pophotkey, Popport,
Popposition, Textinput & Busy classes */

static CONST_STRPTR UsedClasses[] =
{
  "Listtree.mcc",
  "Pophotkey.mcc",
  "Popport.mcc",
  "Textinput.mcc",
  "Textinputscroll.mcc",
  "Busy.mcc",
  NULL
};

...
app = ApplicationObject,
  ...
  MUIA_Application_UsedClasses, UsedClasses,
  ...
  End;
```

### SEE ALSO
[MUIM_Application_OpenConfigWindow](MUI_Application.md/#MUIM_Application_OpenConfigWindow)

## MUIA_Application_UseRexx
### NAME
[MUIA_Application_UseRexx](MUI_Application.md/#MUIA_Application_UseRexx) -- V10 [I..], `BOOL`, 0x80422387

### FUNCTION
When set to FALSE, the application will run without an ARexx interface.
Think very well before using this tag!

### SEE ALSO
[MUIA_Application_UseCommodities](MUI_Application.md/#MUIA_Application_UseCommodities)

## MUIA_Application_UseScreenNotify
### NAME
[MUIA_Application_UseScreenNotify](MUI_Application.md/#MUIA_Application_UseScreenNotify) -- V20 [I..], `BOOL`, 0x80420861

### FUNCTION
When set to FALSE, the application will not automatically close and reopen
its windows when the Workbench screen is to be closed, i.e. due to changed
system preferences. This will then require user interaction to let the
Workbench close its screen.

## MUIA_Application_Version
### NAME
[MUIA_Application_Version](MUI_Application.md/#MUIA_Application_Version) -- V4 [I.G], `STRPTR`, 0x8042b33f

### FUNCTION
Define a version string for an application. This string should follow
standard version string conventions, but must **NOT** contain a leading
"\0".

### EXAMPLE
see [MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title)

### SEE ALSO
[MUIA_Application_Title](MUI_Application.md/#MUIA_Application_Title), [MUIA_Application_Copyright](MUI_Application.md/#MUIA_Application_Copyright), [MUIA_Application_Author](MUI_Application.md/#MUIA_Application_Author),
[MUIA_Application_Description](MUI_Application.md/#MUIA_Application_Description), [MUIA_Application_Base](MUI_Application.md/#MUIA_Application_Base)

## MUIA_Application_Window
### NAME
[MUIA_Application_Window](MUI_Application.md/#MUIA_Application_Window) -- V4 [I..], `Object *`, 0x8042bfe0

### FUNCTION
A pointer to a MUI object of Window class. An application may have any
number of subwindows, each of them being a child of the application.

When the application receives some kind of user input through its IDCMP, it
diverts the message down to its children, as long as they are opened.

Things like iconification or preferences changes cause the application
object to temporarily close every open window (and reopen it later). Your
main program normally doesn't need to deal with these things.

As with the children of group class, it's common to use a call to
MUI_NewObject() as value for this attribute. No error checking needs to be
done, the application object handles every failure automatically.

When you dispose your application, its subwindows will also get deleted.
Thus, the only thing to do to remove your application is a

```c++
MUI_DisposeObject(ApplicationObject);
```

Every window, every gadget, every memory will be freed by this single call.

### EXAMPLE
Please refer to one of the example programs.

## MUIA_Application_WindowList
### NAME
[MUIA_Application_WindowList](MUI_Application.md/#MUIA_Application_WindowList) -- V13 [..G], `struct List *`, 0x80429abe

### FUNCTION
This attribute returns a pointer to the exec list structure which contains
the children (i.e. windows) of an application. Parse this with
intuition.library/NextObject()!

### NOTES
The returned list is strictly read-only!

## MUIM_Application_AboutMUI
### NAME
[MUIM_Application_AboutMUI](MUI_Application.md/#MUIM_Application_AboutMUI) -- V14, 0x8042d21d

### SYNOPSIS
`DoMethod(obj, MUIM_Application_AboutMUI, Object *refwindow);`

### FUNCTION
Show the MUI about window. Please include that in all your applications and
link with a menu item called "About MUI...".

### INPUTS
**`Object *refwindow`**
     pointer to a window object as reference. If non-NULL, the MUI
     about window is centered according to this window. Note that
     this points to a MUI window object, not to a struct Window.

### EXAMPLE
```c++
Object *aboutmenu = (Object *)DoMethod(strip, MUIM_FindUData, MEN_ABOUT);
DoMethod(aboutmenu,
  MUIM_Notify, MUIA_Menuitem_Trigger, MUIV_EveryTime,
  MUIV_Notify_Application, 2,
  MUIM_Application_AboutMUI, mywinobj);
```

## MUIM_Application_AddInputHandler
### NAME
[MUIM_Application_AddInputHandler](MUI_Application.md/#MUIM_Application_AddInputHandler) -- V11, 0x8042f099

### SYNOPSIS
`DoMethod(obj, MUIM_Application_AddInputHandler, struct MUI_InputHandlerNode *ihnode);`

### FUNCTION
Up to MUI 2.3, it was not easy to build custom classes which should react on
signals of private message ports. For example, a clock class would want to
be notified every second to update its display. Old versions of MUI forced
you to Wait() for a timer signal in the main loop and notify the custom
class.

Since MUI 3, the existance of so called "input handlers" (don't mix up with
input.device input handler) eliminates the need of dealing with the main
loop in these cases. A class can create message ports and react on their
signals on its own without interferring the main program.

For a clock class, this would mean that you simply create the object into
any MUI window and it starts updating itself every second automatically. A
game class could open the gameport.device and react on joystick messages, an
HTML class could talk to network ports all on its own.

All this helps to further encapsulate your program into subclasses and make
it a lot more easy to maintain. Let me repeat the main loop of an ideal MUI
application here:

```c++
ULONG sigs = 0;

while(DoMethod(app, MUIM_Application_NewInput, &sigs) != MUIV_Application_ReturnID_Quit)
{
  if(sigs)
  {
    sigs = Wait(sigs | SIGBREAKF_CTRL_C);
    if (sigs & SIGBREAKF_CTRL_C) break;
  }
}
```

To be able to react on signals, you must fill out a MUI_InputHandlerNode
structure (probably located in your class' instance data) and call
[MUIM_Application_AddInputHandler](MUI_Application.md/#MUIM_Application_AddInputHandler) with the structure as parameter. From now
on, your class will receive the specified method whenever one of the given
signals arrives.

Since we're talking about a method of application class here, it's clear
that you cannot call it until you know about your application object. Good
places for [MUIM_Application_AddInputHandler](MUI_Application.md/#MUIM_Application_AddInputHandler)/RemInputHandler are probably the
[MUIM_Setup](MUI_Area.md/#MUIM_Setup)/[MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup) methods of your class.

### INPUTS
**`struct MUI_InputHandlerNode *ihnode`**
     pointer to an initialized MUI_InputHandlerNode structure.

The MUI_InputHandlerNode structure consists of these fields:
**`ihn_Object`**
     fill in a pointer to your object.

**`ihn_Signals`**
     signals you wish to be notified on. You can set more than one bit here.

**`ihn_Flags`**
     a combination of these public flags:
       * MUIIHNF_TIMER: set ihn_Millis to number of 1/1000 sec ticks you
         want to be triggered.
       * MUIIHNF_TIMER_SCALE10: ihn_Millis is in 1/100 seconds instead.
       * MUIIHNF_TIMER_SCALE100: ihn_Millis is in 1/10 seconds instead.
     Setting both SCALE10|SCALE100 makes ihn_Millis 1/1 seconds.

**`ihn_Method`**
     method that you want to receive when one of ihn_Signals is set.

### RESULT
[MUIM_Application_AddInputHandler](MUI_Application.md/#MUIM_Application_AddInputHandler) cannot fail, the result value of the method
is currently undefined.

### NOTES
You must match each AddInputHandler with exactly one RemInputHandler method.
Do not add a MUI_InputHandlerNode which is currently in use.

IMPORTANT: Your trigger method might also be called when none of your
signals arrived. You **MUST** make sure that you check your conditions in the
trigger method (if (GetMsg(port) ... or if (CheckIO(req)) ...). Also, please
make these checks quick and return FALSE as fast as possible when none of
your conditions was met. Return TRUE if you have "used" the trigger method.

TIMER
Since muimaster.library V13, MUIs application class implements a builtin
timer. By using this one instead of creating your own IO requests, you avoid
the problem of having each instance of your object allocating a signal bit.

To make use of this timer, use the above described procedure of initializing
and adding your MUI_InputHandlerNode structure, but set the MUIIHNF_TIMER in
ihn_Flags. Furthermore, specify the number of milliseconds after which you
want to receive your method in ihn_Millis. Note that ihn_Millis is in fact
part of a union placed at the same memory location as ihn_Signals, do not
use ihn_Signals when MUIIHNF_TIMER is set.

Besides from MUIIHNF_TIMER and ihn_Millis instead of ihn_Signals, using the
timer is similiar to other input handlers. Removing with
[MUIM_Application_RemInputHandler](MUI_Application.md/#MUIM_Application_RemInputHandler) is not different at all.

### EXAMPLE
OM_NEW:
```c++
  data->port = CreateMsgPort();
  data->req = CreateIORequest(data->port,sizeof(struct timerequest));
  OpenDevice(TIMERNAME,UNIT_VBLANK,(struct IORequest *)data->req,0);
  data->ihnode.ihn_Object  = obj;
  data->ihnode.ihn_Signals = IO_SIGMASK(data->req);
  data->ihnode.ihn_Flags   = 0;
  data->ihnode.ihn_Method  = MY_TRIGGER_METHOD;
```

OM_DISPOSE:
```c++
  CloseDevice((struct IORequest *)data->req);
  DeleteIORequest(data->req);
  DeleteMsgPort(data->port);
```

[MUIM_Setup](MUI_Area.md/#MUIM_Setup):
```c++
  data->req->tr_node.io_Command = TR_ADDREQUEST;
  data->req->tr_time.tv_secs    = 1;
  data->req->tr_time.tv_micro   = 0;
  SendIO((struct IORequest *)data->req);
  DoMethod(_app(obj), MUIM_Application_AddInputHandler, &data->ihnode);
```

[MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup):
```c++
  DoMethod(_app(obj), MUIM_Application_RemInputHandler, &data->ihnode);
  if (!CheckIO(data->req)) AbortIO(data->req);
  WaitIO(data->req);
```

MY_TRIGGER_METHOD:
```c++
  if(CheckIO(data->req))
  {
    WaitIO(data->req);

    /* update display or do anything else here ... */

    /* send a new timer event */
    data->req->tr_node.io_Command = TR_ADDREQUEST;
    data->req->tr_time.tv_secs    = 1;
    data->req->tr_time.tv_micro   = 0;
    SendIO((struct IORequest *)data->req);

    return TRUE;
  }

  returnFALSE;
```

### SEE ALSO
[MUIM_Application_RemInputHandler](MUI_Application.md/#MUIM_Application_RemInputHandler), [MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input)

## MUIM_Application_BuildSettingsPanel
### NAME
[MUIM_Application_BuildSettingsPanel](MUI_Application.md/#MUIM_Application_BuildSettingsPanel) -- V20, 0x8042b58f

### SYNOPSIS
`DoMethod(obj, MUIM_Application_BuildSettingsPanel, ULONG number);`

### FUNCTION
Implement this method if your application provides built in settings panels.
See Animal demo for details.

## MUIM_Application_CheckRefresh
### NAME
[MUIM_Application_CheckRefresh](MUI_Application.md/#MUIM_Application_CheckRefresh) -- V11, 0x80424d68

### SYNOPSIS
`DoMethod(obj, MUIM_Application_CheckRefresh);`

### FUNCTION
This method checks all currently open windows if they need refreshing and
refreshes them if necessary.

You won't need to call this method if you are within your traditional MUI
main loop. However, if you e.g. spawn some kind of synchronous requester
(AslRequest), MUI cannot react on IDCMP_REFRESHWINDOW messages.

The result is that the user may see a damaged MUI window if he moves around
a file requester and MUI is configured for simple refresh.

[MUIA_Application_CheckRefresh](MUI_Application.md/#MUIA_Application_CheckRefresh) is the solution for this problem. Just open
your requesters with

```c++
ASLFR_UserData, ApplicationObject,
ASLFR_IntuiMsgFunc, &IntuiMsgHook,
```

and let IntuiMsgHook point to something like this:

```c++
VOID SAVEDS ASM IntuiMsgFunc(REG(a1, struct IntuiMessage *imsg), REG(a2, struct FileRequester *req))
{
  if(imsg->Class == IDCMP_REFRESHWINDOW)
    DoMethod(req->fr_UserData, MUIM_Application_CheckRefresh);
}
```

### RESULT
Windows with damage will be refreshed. This may result in MUI calling
[MUIM_Draw](MUI_Area.md/#MUIM_Draw) of some of your custom classes. The result value of this method is
undefined.

### SEE ALSO
[MUIM_Application_InputBuffered](MUI_Application.md/#MUIM_Application_InputBuffered)

## MUIM_Application_DefaultConfigItem
### NAME
[MUIM_Application_DefaultConfigItem](MUI_Application.md/#MUIM_Application_DefaultConfigItem) -- V20, 0x8042d934

### SYNOPSIS
`DoMethod(obj, MUIM_Application_DefaultConfigItem, ULONG cfgid);`

### FUNCTION
Override this method and return a sensible value if your application can
provide default values for specific configuration items which differ from
the global default values.

This method will be called whenever MUI needs to obtain the default value of
configuration items which are specific to applications.

See Animal demo for details.

## MUIM_Application_Execute
### NAME
[MUIM_Application_Execute](MUI_Application.md/#MUIM_Application_Execute) -- V20, 0x804253f3

### SYNOPSIS
`DoMethod(obj, MUIM_Application_Execute);`

### FUNCTION
[MUIM_Application_Execute](MUI_Application.md/#MUIM_Application_Execute) implements the ideal main loop of a MUI
application for simplicity.

Basically the method looks like this

```c++
ULONG signals = 0L;
while(DoMethod(obj, MUIM_Application_NewInput, &signals) != MUIV_Application_ReturnID_Quit)
{
  if(signals != 0)
  {
    signals = Wait(signals | SIGBREAKF_CTRL_C);
    if(signals & SIGBREAKF_CTRL_C)
      break;
  }
}
```

This method does exactly the same as [MUIM_Application_Run](MUI_Application.md/#MUIM_Application_Run).

### SEE ALSO
[MUIM_Application_NewInput](MUI_Application.md/#MUIM_Application_NewInput), [MUIM_Application_Run](MUI_Application.md/#MUIM_Application_Run)

## MUIM_Application_GetMenuCheck
### NAME
[MUIM_Application_GetMenuCheck](MUI_Application.md/#MUIM_Application_GetMenuCheck) -- V4, 0x8042c0a7 **(OBSOLETE)**

### SYNOPSIS
`DoMethod(obj, MUIM_Application_GetMenuCheck, ULONG MenuID);`

### FUNCTION
Ask whether a checkmark menu item has its checkmark set or cleared. The
application will ask its subwindows for a menu item with the given ID and
return the state of the first item it finds.

### INPUTS
**`ULONG MenuID`**
     the value you wrote into the UserData field of struct NewMenu.

### SEE ALSO
[MUIM_Application_SetMenuCheck](MUI_Application.md/#MUIM_Application_SetMenuCheck), [MUIA_Application_Menu](MUI_Application.md/#MUIA_Application_Menu)

## MUIM_Application_GetMenuState
### NAME
[MUIM_Application_GetMenuState](MUI_Application.md/#MUIM_Application_GetMenuState) -- V4, 0x8042a58f **(OBSOLETE)**

### SYNOPSIS
`DoMethod(obj, MUIM_Application_GetMenuState, ULONG MenuID);`

### FUNCTION
Ask whether a menu item is enabled or disabled. The application will ask its
subwindows for a menu item with the given id and return the state of the
first item it finds.

### INPUTS
**`ULONG MenuID`**
     the value you wrote into the UserData field of struct NewMenu.

### SEE ALSO
[MUIM_Application_SetMenuState](MUI_Application.md/#MUIM_Application_SetMenuState), [MUIA_Application_Menu](MUI_Application.md/#MUIA_Application_Menu)

## MUIM_Application_Input
### NAME
[MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input) -- V4, 0x8042d0f5 **(OBSOLETE)**

### SYNOPSIS
`DoMethod(obj, MUIM_Application_Input, ULONG *signal);`

### FUNCTION
The MUI system itself does not wait for any user input. It just tells your
application which signal bits it has allocated, then it's up to you to call
MUIs input handle function when one of these signals gets set.

In a simple MUI application you would just Wait() for these signals and call
MUI when one is received. However, you can perfectly allocate some signal
bits yourself and include them in your Wait() command. You needn't even
Wait(), your application could maybe calculate some fractal graphics or copy
disks, the only important thing is that you call MUI's input method when one
of the MUI allocated signals arrives.

The usual way of communication with your user interface is via return IDs.
Every action happening to the GUI can create return IDs, e.g. pressing a
button or trying to close a window. MUI buffers these IDs and uses them as
result codes for the input method. Thats where you can get it from and take
the appropriate actions.

Now let's have a look on a usual input loop of a MUI application. Imagine you
have a Play and a Cancel button and have previously told them to return
ID_PLAY and ID_CANCEL when pressed (see [MUIM_Notify](MUI_Notify.md/#MUIM_Notify) and
[MUIM_Application_ReturnID](MUI_Application.md/#MUIM_Application_ReturnID) on information about these topics). Your input
loop would look like this:

```c++
while(running)
{
  ULONG signals;

  switch(DoMethod(app, MUIM_Application_Input, &signals))
  {
    case ID_PLAY:
      PlaySound();
      break;

    case ID_CANCEL:
    case MUIV_Application_ReturnID_Quit:
      running = FALSE;
      break;
  }

  if (running && signals) Wait(signals);
}
```

So what is happening here?

First, you have to call the [MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input) method. You supply the
address of a ULONG as parameter, thats where MUI fills in the signals it
needs. Note that you can call the input method at any time, regardless of
signal setting. MUI will simply return when there is nothing to do.

In case the user pressed the Play or the Cancel button,
[MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input) will return ID_PLAY or ID_CANCEL. Otherwise you will
receive a 0, that's why you cannot use 0 as one of your ID values.

There is one predefined ID called MUIV_Application_ReturnID_Quit. This will
be sent to you when someone tried to quit your application from outside,
e.g. via commodities exchange or the ARexx "quit" command. It is required
that your application handles this id, just treat as if the user clicked on
a "Quit" button or selected a "Quit" menu item.

After handling the return value, you have to examine if MUI wants you to
wait for any signals. If this is the case (signals != 0), just wait for it.
If MUI puts a 0 into signals it wants to tell you to immediately call the
input method again, maybe some other return IDs have received and need to be
handled. You **MUST** check this because Wait()ing on a zero signal mask is
not a good idea!

Note: It is very important that you call the input method whenever a signal
arrives. MUI needs this to correctly refresh its windows, handle resizing
and iconification operations and commodities and ARexx messages. If you
don't, you will annoy your user!

If your program needs to be in a state where you are for some reasons unable
to call the input method for a considerable amount of time (maybe half a
second or more), you should put your application to sleep. See
[MUIA_Application_Sleep](MUI_Application.md/#MUIA_Application_Sleep) on how to do this.

### INPUTS
**`ULONG *signal`**
     a pointer to a ULONG value containing the result of Wait().

### SEE ALSO
[MUIA_Application_Sleep](MUI_Application.md/#MUIA_Application_Sleep), [MUIM_Application_InputBuffered](MUI_Application.md/#MUIM_Application_InputBuffered),
[MUIM_Application_NewInput](MUI_Application.md/#MUIM_Application_NewInput)

## MUIM_Application_InputBuffered
### NAME
[MUIM_Application_InputBuffered](MUI_Application.md/#MUIM_Application_InputBuffered) -- V4, 0x80427e59

### SYNOPSIS
`DoMethod(obj, MUIM_Application_InputBuffered);`

### FUNCTION
Imagine your application does some time consuming operation, e.g. copying a
disk, and you are for some reasons unable to react on return IDs during this
period. One solution would be to simply put your application to sleep, it
will get a busy pointer and the user knows whats going on.

However, this will make it impossible for the user to resize your
application's windows or iconify it, he will have to wait until you are done
with your operation.

[MUIM_Application_InputBuffered](MUI_Application.md/#MUIM_Application_InputBuffered) offers a solution for this problem. Using
this method, you needn't set to sleep your application. Just call it on a
regular basis and MUI will be able to handle all actions concerning the GUI.
You do not need to pay attention on return values, they remain on an
internal stack until your next call to the non buffered input method.

### EXAMPLE
```c++
for (track=0; track<80; track++)
{
  read_track();
  DoMethod(app, MUIM_Application_InputBuffered);
  write_track();
  DoMethod(app, MUIM_Application_InputBuffered);
}
```

### SEE ALSO
[MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input), [MUIA_Application_Sleep](MUI_Application.md/#MUIA_Application_Sleep)

## MUIM_Application_Load
### NAME
[MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load) -- V4, 0x8042f90d

### SYNOPSIS
`DoMethod(obj, MUIM_Application_Load, CONST_STRPTR name);`

### FUNCTION
[MUIM_Application_Save](MUI_Application.md/#MUIM_Application_Save), [MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load) and [MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID) offer an easy
way of saving and loading a programs configuration.

Each object with a non NULL [MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID) will get its contents saved during
[MUIM_Application_Save](MUI_Application.md/#MUIM_Application_Save) and restored during [MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load). This makes
it very easy to design a configuration window with "Save", "Use" and
"Cancel" buttons to allow saving & loading of settings. When the application
starts, you would just have to call [MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load) and the stored
settings will be read and installed.

Not all classes are able to import and export their contents. Currently,
you may define a [MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID) for

  * String class   - [MUIA_String_Contents](MUI_String.md/#MUIA_String_Contents) is ex/imported.
  * Radio class    - [MUIA_Radio_Active](MUI_Radio.md/#MUIA_Radio_Active) is ex/imported.
  * Cycle class    - [MUIA_Cycle_Active](MUI_Cycle.md/#MUIA_Cycle_Active) is ex/imported.
  * List class     - [MUIA_List_Active](MUI_List.md/#MUIA_List_Active) is ex/imported.
  * Text class     - [MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents) is ex/imported.
  * Numeric class  - [MUIA_Numeric_Value](MUI_Numeric.md/#MUIA_Numeric_Value) is ex/imported.
  * Area class     - [MUIA_Selected](MUI_Area.md/#MUIA_Selected) is ex/imported (e.g. for Checkmark gadgets)
  * Menuitem class - [MUIA_Menuitem_Checked](MUI_Menuitem.md/#MUIA_Menuitem_Checked) is ex/imported (V9).
  * Group class    - [MUIA_Group_ActivePage](MUI_Group.md/#MUIA_Group_ActivePage) is ex/imported (V8).

### INPUTS
**`CONST_STRPTR name`**
     name of the file you wish to load the settings from. Usually you
     won't need to think of a real name but instead use one of the magic
     cookies MUIV_Application_Load_ENV or MUIV_Application_Load_ENVARC.

### EXAMPLE
see the sample program "Settings.c"

### SEE ALSO
[MUIM_Application_Save](MUI_Application.md/#MUIM_Application_Save), [MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID), [MUIM_Export](MUI_Notify.md/#MUIM_Export), [MUIM_Import](MUI_Notify.md/#MUIM_Import)

## MUIM_Application_NewInput
### NAME
[MUIM_Application_NewInput](MUI_Application.md/#MUIM_Application_NewInput) -- V11, 0x80423ba6

### SYNOPSIS
`DoMethod(obj, MUIM_Application_NewInput, ULONG *signal);`

### FUNCTION
This is an enhanced replacement for [MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input). It depends on
receiving the return value from your Wait() or 0 as input to be able to
perform the necessary actions more efficient.

[MUIM_Application_NewInput](MUI_Application.md/#MUIM_Application_NewInput) is generally preferrable over
[MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input).

### INPUTS
**`ULONG *signal`**
     a pointer to a ULONG value containing the result of Wait().

### EXAMPLE
```c++
/*
** This is the ideal input loop for an object oriented MUI
** application. Everything is encapsulated in classes, no
** return IDs need to be used, we just check if the program
** shall terminate.
** Note that MUIM_Application_NewInput expects sigs to
** contain the result from Wait() (or 0). This makes the
** input loop significantly faster.
*/

{
  ULONG sigs = 0;

  while(DoMethod(app, MUIM_Application_NewInput, &sigs) != MUIV_Application_ReturnID_Quit)
  {
    if (sigs)
    {
      sigs = Wait(sigs | SIGBREAKF_CTRL_C);
      if (sigs & SIGBREAKF_CTRL_C) break;
    }
  }
}
```

### SEE ALSO
[MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input)


## MUIM_Application_OpenConfigWindow
### NAME
[MUIM_Application_OpenConfigWindow](MUI_Application.md/#MUIM_Application_OpenConfigWindow) -- V11, 0x804299ba

### SYNOPSIS
`DoMethod(obj, MUIM_Application_OpenConfigWindow, ULONG flags, STRPTR classid);`

### FUNCTION
Since MUI 3, applications can open their own MUI configuration window to
allow users to adjust the local preferences without the need of an external
program. Programmers are supposed to include a "Settings/MUI..." menu item
which simply calls [MUIM_Application_OpenConfigWindow](MUI_Application.md/#MUIM_Application_OpenConfigWindow). MUI will then
automatically show the preferences window without blocking the rest of the
program.

### INPUTS
**`ULONG flags`**
     currently no flags are defined; pass 0 for the time being.

## MUIM_Application_PushMethod
### NAME
[MUIM_Application_PushMethod](MUI_Application.md/#MUIM_Application_PushMethod) -- V4, 0x80429ef8

### SYNOPSIS
`DoMethod(obj, MUIM_Application_PushMethod, Object *dest, LONG count, /* ... */);`

### FUNCTION
Usually, you may not talk to the MUI system from two tasks at the same time.
[MUIM_Application_PushMethod](MUI_Application.md/#MUIM_Application_PushMethod) provides some kind of solution for this problem.

This (and only this) method may be called from a second task. It takes
another method as parameter and puts in onto a private stack of the
application object. The next time [MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input) is called, the
pushed method will be executed in the context of the current task.

### INPUTS
**`Object *dest`**
     object on which to perform the pushed method.

**`LONG count`**
     number of following arguments.

**`...`**
     the destination method.

### RESULT
Identifier of a pushed method or FALSE otherwise.

### EXAMPLE
```c++
/* set a status line from a sub task */
ULONG methodid = DoMethod(app, MUIM_Application_PushMethod,
  txstatus, 3,
  MUIM_Set, MUIA_Text_Contents, "reading...");
```

### NOTES
[MUIM_Application_PushMethod](MUI_Application.md/#MUIM_Application_PushMethod) has a limit of 7 arguments!

### SEE ALSO
[MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input)

## MUIM_Application_RemInputHandler
### NAME
[MUIM_Application_RemInputHandler](MUI_Application.md/#MUIM_Application_RemInputHandler) -- V11, 0x8042e7af

### SYNOPSIS
`DoMethod(obj, MUIM_Application_RemInputHandler, struct MUI_InputHandlerNode *ihnode);`

### FUNCTION
Remove an input handler. MUI will no longer call your trigger method after
you have removed the MUI_InputHandlerNode. You can add/remove input handler
nodes any time as long as you know about your application object.

### INPUTS
**`struct MUI_InputHandlerNode *ihnode`**
     input handler node structure you passed to [MUIM_Application_AddInputHandler](MUI_Application.md/#MUIM_Application_AddInputHandler)
     previously.

### RESULT
[MUIM_Application_RemInputHandler](MUI_Application.md/#MUIM_Application_RemInputHandler) cannot fail, the result value of the method
is currently undefined.

### SEE ALSO
[MUIM_Application_AddInputHandler](MUI_Application.md/#MUIM_Application_AddInputHandler), [MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input)

## MUIM_Application_ReturnID
### NAME
[MUIM_Application_ReturnID](MUI_Application.md/#MUIM_Application_ReturnID) -- V4, 0x804276ef

### SYNOPSIS
`DoMethod(obj, MUIM_Application_ReturnID, ULONG retid);`

### FUNCTION
Tell MUI to return the given ID with the next call to
[MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input).

Together with the MUI's notification mechanism, this method connects your
user interface and your program. If you e.g. want to be informed if the user
presses a "Play" button, you would have define an ID for this action and set
up a notification event with [MUIM_Notify](MUI_Notify.md/#MUIM_Notify).

You can use any long word as return id, except from -255 up to 0. These
values are reserved for MUI's internal use and for special return values
like MUIV_Application_ReturnID_Quit.

Note that MUI will put all incoming return IDs onto a private fifo stack and
feed this stack to its input methods result code later.

### NOTES
The usage of ReturnIDs is no good MUI programming style. You should build
your application with subclasses and hooks instead! See the
PublicScreenManager source code for an example of good MUI programming!

### EXAMPLE
```c++
/* inform me if a button is pressed (actually released, */
/* since this is the way amiga buttons are handled)     */

#define ID_PLAYBUTTON 42

...

DoMethod(buttonobj, MUIM_Notify,
  MUIA_Pressed, FALSE,
  appobj, 2, MUIM_Application_ReturnID, ID_PLAYBUTTON);

...

while(running)
{
  switch(DoMethod(appobj, MUIM_Application_Input, &sigs))
  {
    case ID_PLAYBUTTON:
      printf("Ok, let's play a game...");
      break;
  }
}
```

### SEE ALSO
[MUIM_Application_Input](MUI_Application.md/#MUIM_Application_Input), [MUIM_Notify](MUI_Notify.md/#MUIM_Notify)

## MUIM_Application_Run
### NAME
[MUIM_Application_Run](MUI_Application.md/#MUIM_Application_Run) -- V20, 0x90420103

### SYNOPSIS
`DoMethod(obj, MUIM_Application_Run);`

### FUNCTION
[MUIM_Application_Run](MUI_Application.md/#MUIM_Application_Run) implements the ideal main loop of an MUI application
for simplicity.

Basically the method looks like this

```c++
ULONG signals = 0L;
while(DoMethod(obj, MUIM_Application_NewInput, &signals) != MUIV_Application_ReturnID_Quit)
{
  if(signals != 0)
  {
    signals = Wait(signals | SIGBREAKF_CTRL_C);
    if(signals & SIGBREAKF_CTRL_C)
      break;
  }
}
```

This method does exactly the same as [MUIM_Application_Execute](MUI_Application.md/#MUIM_Application_Execute).

### SEE ALSO
[MUIM_Application_Execute](MUI_Application.md/#MUIM_Application_Execute), [MUIM_Application_NewInput](MUI_Application.md/#MUIM_Application_NewInput)

## MUIM_Application_Save
### NAME
[MUIM_Application_Save](MUI_Application.md/#MUIM_Application_Save) -- V4, 0x804227ef

### SYNOPSIS
`DoMethod(obj, MUIM_Application_Save, CONST_STRPTR name);`

### FUNCTION
[MUIM_Application_Save](MUI_Application.md/#MUIM_Application_Save), [MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load) and [MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID) offer an easy
way of saving and loading a programs configuration.

Each gadget with a non NULL [MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID) will get its contents saved during
[MUIM_Application_Save](MUI_Application.md/#MUIM_Application_Save) and restored during [MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load). This makes
it very easy to design a configuration window with "Save", "Use" and
"Cancel" buttons to allow the user storing the settings. When the
application starts, you would just have to call [MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load) and
the stored settings will be read and installed.

Not all classes are able to import and export their contents. Currently, you
may define a [MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID) for

  * String class   - [MUIA_String_Contents](MUI_String.md/#MUIA_String_Contents) is ex/imported.
  * Radio class    - [MUIA_Radio_Active](MUI_Radio.md/#MUIA_Radio_Active) is ex/imported.
  * Cycle class    - [MUIA_Cycle_Active](MUI_Cycle.md/#MUIA_Cycle_Active) is ex/imported.
  * List class     - [MUIA_List_Active](MUI_List.md/#MUIA_List_Active) is /ex/imported.
  * Text class     - [MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents) is ex/imported.
  * Numeric class  - [MUIA_Numeric_Value](MUI_Numeric.md/#MUIA_Numeric_Value) is ex/imported.
  * Area class     - [MUIA_Selected](MUI_Area.md/#MUIA_Selected) is ex/imported (e.g. for Checkmark gadgets)
  * Menuitem class - [MUIA_Menuitem_Checked](MUI_Menuitem.md/#MUIA_Menuitem_Checked) is ex/imported (V9).
  * Group class    - [MUIA_Group_ActivePage](MUI_Group.md/#MUIA_Group_ActivePage) is ex/imported (V8).

### INPUTS
**`CONST_STRPTR name`**
     name of the file you wish to save the settings to. Usually you won't
     need to think of a real name but instead use one of the magic cookies
     MUIV_Application_Save_ENV or MUIV_Application_Save_ENVARC.
     This will save your application's settings somewhere in ENV:mui/ or
     ENVARC:mui/, you needn't worry about it.

### EXAMPLE
see the sample program "Settings.c"

### SEE ALSO
[MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load), [MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID), [MUIM_Export](MUI_Notify.md/#MUIM_Export), [MUIM_Import](MUI_Notify.md/#MUIM_Import)

## MUIM_Application_SetConfigItem
### NAME
[MUIM_Application_SetConfigItem](MUI_Application.md/#MUIM_Application_SetConfigItem) -- V11, 0x80424a80

### SYNOPSIS
`DoMethod(obj, MUIM_Application_SetConfigItem, ULONG item, CONST_APTR data);`

### FUNCTION
Private method, only for PSI.

## MUIM_Application_SetMenuCheck
### NAME
[MUIM_Application_SetMenuCheck](MUI_Application.md/#MUIM_Application_SetMenuCheck) -- V4, 0x8042a707 **(OBSOLETE)**

### SYNOPSIS
`DoMethod(obj, MUIM_Application_SetMenuCheck, ULONG MenuID, LONG stat);`

### FUNCTION
Set or clear the checkmark of a menu item. The application will ask its
subwindows for menu items with the given ID and set/clear all found entries.

### INPUTS
**`ULONG MenuID`**
     the value you wrote into the UserData field of struct NewMenu.

**`LONG stat`**
     TRUE to set checkmark, FALSE to clear

### SEE ALSO
[MUIM_Application_GetMenuCheck](MUI_Application.md/#MUIM_Application_GetMenuCheck), [MUIA_Application_Menu](MUI_Application.md/#MUIA_Application_Menu)

## MUIM_Application_SetMenuState
### NAME
[MUIM_Application_SetMenuState](MUI_Application.md/#MUIM_Application_SetMenuState) -- V4, 0x80428bef **(OBSOLETE)**

### SYNOPSIS
`DoMethod(obj, MUIM_Application_SetMenuState, ULONG MenuID, LONG stat);`

### FUNCTION
Enable or disable a menu item. The application will ask its subwindows for
menu items with the given ID and enable/disable all found entries.

### INPUTS
**`ULONG MenuID`**
     the value you wrote into the UserData field of struct NewMenu.

**`LONG stat`**
     TRUE to enable item, FALSE to disable.

### SEE ALSO
[MUIM_Application_GetMenuState](MUI_Application.md/#MUIM_Application_GetMenuState), [MUIA_Application_Menu](MUI_Application.md/#MUIA_Application_Menu)

## MUIM_Application_ShowHelp
### NAME
[MUIM_Application_ShowHelp](MUI_Application.md/#MUIM_Application_ShowHelp) -- V4, 0x80426479

### SYNOPSIS
`DoMethod(obj, MUIM_Application_ShowHelp, Object *window, CONST_STRPTR name, CONST_STRPTR node, LONG line);`

### FUNCTION
Show an AmigaGuide help file. The application will be put to sleep until the
file is displayed.

Usually, you don't need to call this method directly. MUI comes with a
sophisticated online help system, you just need to supply your gadgets with
help nodes and everything will be handled automatically.

### INPUTS
**`Object *window`**
     Help will appear on this windows screen. May be NULL,
     help will appear on default public screen then. May
     also be (Object *)0xffffffff, MUI will use the first
     open child window of the application as reference for
     the screen (since muimaster.library V18).

**`CONST_STRPTR name`**
     name of the help file. If set to NULL, MUI will use
     the contents of [MUIA_Application_HelpFile](MUI_Application.md/#MUIA_Application_HelpFile) instead
     (since muimaster.library V18).

**`CONST_STRPTR node`**
     name of a node in this help file.

**`LONG line`**
     line number.

### SEE ALSO
[MUIA_HelpFile](MUI_Notify.md/#MUIA_HelpFile), [MUIA_HelpNode](MUI_Notify.md/#MUIA_HelpNode), [MUIA_HelpLine](MUI_Notify.md/#MUIA_HelpLine)

## MUIM_Application_UnpushMethod
### NAME
[MUIM_Application_UnpushMethod](MUI_Application.md/#MUIM_Application_UnpushMethod) -- V20, 0x804211dd

### SYNOPSIS
`DoMethod(obj, MUIM_Application_UnpushMethod, Object *targetobj, ULONG methodid, ULONG method);`

### FUNCTION
Kill a method scheduled for execution by [MUIM_Application_PushMethod](MUI_Application.md/#MUIM_Application_PushMethod). This
method will work only if the method wasn't executed yet. Each method in a
queue is matched to the values supplied. If any of arguments is 0/NULL it is
not taken into account. If all arguments are 0/NULL then all methods will be
removed from the queue!

### INPUTS
**`Object *targetobj`**
     object which was a target for [MUIM_Application_PushMethod](MUI_Application.md/#MUIM_Application_PushMethod).

**`ULONG methodid`**
     method identifier returned by [MUIM_Application_PushMethod](MUI_Application.md/#MUIM_Application_PushMethod).

**`ULONG method`**
     method which was supposed to be executed.

### RESULT
Number of methods removed from a queue

### EXAMPLE
```c++
ULONG methodid = DoMethod(appobj, MUIM_Application_PushMethod,
  obj, 1, MUIM_TestMethod);

/* kill all methods pushed for "obj" */
DoMethod(appobj, MUIM_Application_UnpushMethod, obj, 0, 0);

/* kill only one method */
DoMethod(appobj, MUIM_Application_UnpushMethod, NULL, methodid, 0);

/* same thing, but with different params */
DoMethod(appobj, MUIM_Application_UnpushMethod, obj, methodid, 0);

/* kill all MUIM_TestMethod methods pushed for an object */
DoMethod(appobj, MUIM_Application_UnpushMethod, obj, 0, MUIM_TestMethod);
```

### SEE ALSO
[MUIM_Application_PushMethod](MUI_Application.md/#MUIM_Application_PushMethod)

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
