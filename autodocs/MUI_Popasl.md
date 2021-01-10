# Popasl.mui
## Super class
[Popstring.mui](MUI_Popstring.md)
## Background
As a subclass of popstring class, popasl can be used to pop up any kinds of
standard system asl requesters. A seperate task is spawned to handle these
requesters, the application continues to run.

Using an asl popup class, you don't need to worry about handling asl
requesters. MUI will automatically open one when the popup button is pressed
and update the corresponding string gadget when the user terminates the
requester. From the programmers point of view, all you have to do is to
handle the string gadgets contents.

IMPORTANT: At object creation time, you can use all ASL library tags as
well. They will be passed to the AllocAslRequest() call without further
interpretation, but some of the tags may get overloaded by Popasl's normal
requester opening procedure - namely ASLFR_InitialFile and
ASLFR_InitialDrawer. These can be changed by using [MUIA_Popasl_StartHook](MUI_Popasl.md/#MUIA_Popasl_StartHook).
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Popasl_Active](MUI_Popasl.md/#MUIA_Popasl_Active)|V7|..G|`BOOL`
[MUIA_Popasl_StartHook](MUI_Popasl.md/#MUIA_Popasl_StartHook)|V7|ISG|`struct Hook *`
[MUIA_Popasl_StopHook](MUI_Popasl.md/#MUIA_Popasl_StopHook)|V7|ISG|`struct Hook *`
[MUIA_Popasl_Type](MUI_Popasl.md/#MUIA_Popasl_Type)|V7|I.G|`ULONG`

## MUIA_Popasl_Active
### NAME
[MUIA_Popasl_Active](MUI_Popasl.md/#MUIA_Popasl_Active) -- V7 [..G], `BOOL`, 0x80421b37

### FUNCTION
Popasl creates asynchronous popups. Requesters are opened in a seperately
spawned task and don't disturb the rest of the application. You can ask for
the state of a requester by querying the [MUIA_Popasl_Active](MUI_Popasl.md/#MUIA_Popasl_Active) attribute. It
will return TRUE when the requester is currently open, FALSE otherwise.

Common use for this attribute is to prevent an application from being
terminated while a requester is open. If you try to dispose the popasl
object with a currently open requester, MUI will freeze your task as long as
the requester stays there.

### EXAMPLE
```c++
case MUIV_Application_ReturnID_Quit:
{
  LONG active;

  get(pop1, MUIA_Popasl_Active, &active);
  if(!active) get(pop2, MUIA_Popasl_Active, &active);
  if(!active) get(pop3, MUIA_Popasl_Active, &active);
  if(!active) get(pop4, MUIA_Popasl_Active, &active);

  if(active)
    MUI_Request(app,window, 0, NULL, "OK",
                "Cannot quit now, still some asl popups opened.");
  else
    running = FALSE;
}
break;
```

### SEE ALSO
[MUIA_Popasl_StartHook](MUI_Popasl.md/#MUIA_Popasl_StartHook), [MUIA_Popasl_StopHook](MUI_Popasl.md/#MUIA_Popasl_StopHook), [MUIA_Popasl_Type](MUI_Popasl.md/#MUIA_Popasl_Type)

## MUIA_Popasl_StartHook
### NAME
[MUIA_Popasl_StartHook](MUI_Popasl.md/#MUIA_Popasl_StartHook) -- V7 [ISG], `struct Hook *`, 0x8042b703

### FUNCTION
Before popasl class opens the asl requester, it has to get some kind of
parameters describing its initial contents. A file popup would e.g. need to
split the string gadgets contents into path and file name part and pass
these as ASLFR_InititalFile and ASLFR_InitialDrawer to the requester.

The [MUIA_Popasl_StartHook](MUI_Popasl.md/#MUIA_Popasl_StartHook) tag describes a hook function that will be called
immediately before the requester is opened. It will receive a pointer to
itself in A0, a pointer to the popasl object in A2 and a pointer to a
taglist in A1. This taglist already contains some tags:

```c++
ASLFR/FO/..._Screen          : parent screen
ASLFR/FO/..._PrivateIDCMP    : TRUE
ASLFR/FO/..._InititalLeftEdge: left edge of popasl object
ASLFR/FO/..._InititalTopEdge : bottom edge of popasl object
ASLFR/FO/..._InititalWidth   : width of popasl object, only present when the
                               popup is called for the first time.
```

You may add other tags to the list, but beware that the maximum allowed
number of tags is 15. If you need more, use the TAG_MORE tag.

Since the asl requester will run in a seperate task, you should not change
the state of the ASLFR_PrivateIDCMP tag!

If your hook returns TRUE, popasl class opens the requester with the given
taglist. A return value of FALSE should be used when something went wrong,
no requester will be opened in this case.

For file and font requester, popasl class will fall back to a default tag
handling when no start hook is specified. A file name is automatically split
into path and file part and passed to the requester a ASLFR_InitialFile and
ASLFR_InitialDrawer. A font requester splits a string like "topaz/8" into
font name and size for ASLFO_InitialName and ASLFO_InitialSize.

### SEE ALSO
[MUIA_Popasl_StopHook](MUI_Popasl.md/#MUIA_Popasl_StopHook), [MUIA_Popasl_Type](MUI_Popasl.md/#MUIA_Popasl_Type)

## MUIA_Popasl_StopHook
### NAME
[MUIA_Popasl_StopHook](MUI_Popasl.md/#MUIA_Popasl_StopHook) -- V7 [ISG], `struct Hook *`, 0x8042d8d2

### FUNCTION
When the requester terminates, [MUIA_Popasl_StopHook](MUI_Popasl.md/#MUIA_Popasl_StopHook) will be called with a
pointer to itself in A0, a pointer to the popasl object in A2 and a pointer
to the asl requester structure in A1. The hook can then parse the requester
structure and set the string gadgets contents respectively.

For file and font requesters, a default handling is provided.

### SEE ALSO
[MUIA_Popasl_StartHook](MUI_Popasl.md/#MUIA_Popasl_StartHook), [MUIA_Popasl_Type](MUI_Popasl.md/#MUIA_Popasl_Type)

## MUIA_Popasl_Type
### NAME
[MUIA_Popasl_Type](MUI_Popasl.md/#MUIA_Popasl_Type) -- V7 [I.G], `ULONG`, 0x8042df3d

### FUNCTION
This tag allows to set the type of asl requester. Pass the same value you
would use for AllocAslRequest(), e.g. ASL_FileRequest, ASL_FontRequest or
ASL_ScreenModeRequest.

For ASL_FileRequest and ASL_FontRequest, popasl class offers a standard
start/stop handling. When a file requester is opened, MUI splits the string
gadgets contents into a path and a file name and uses these as initial
parameters for the requester. Font popups translate a font into a name/size
pair, e.g. "topaz/8". You can override these translations by specifying a
[MUIA_Popasl_StartHook](MUI_Popasl.md/#MUIA_Popasl_StartHook) and a [MUIA_Popasl_StopHook](MUI_Popasl.md/#MUIA_Popasl_StopHook).

For ASL_ScreenModeRequest, no standard handling is available. Using such a
popup without Start and Stop hooks won't make much sense.

### SEE ALSO
[MUIA_Popasl_StartHook](MUI_Popasl.md/#MUIA_Popasl_StartHook), [MUIA_Popasl_StopHook](MUI_Popasl.md/#MUIA_Popasl_StopHook)

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
