# Panel.mui
## Super class
[Group.mui](MUI_Group.md)
## Inherited by
* [Filepanel.mui](MUI_Filepanel.md)
* [Fontpanel.mui](MUI_Fontpanel.md)
* [Screenmodepanel.mui](MUI_Screenmodepanel.md)
## Background
Panel class is an abstract base class for ASL like selectors.
## Methods
Method|Version
------|-------
[MUIM_Panel_Run](MUI_Panel.md/#MUIM_Panel_Run)|V21

## MUIM_Panel_Run
### NAME
[MUIM_Panel_Run](MUI_Panel.md/#MUIM_Panel_Run) -- V21, 0x8042d789

### SYNOPSIS
`DoMethod(obj, MUIM_Panel_Run, Object *app, Object *win);`

### FUNCTION
This method opens the panel window and eventually "runs" the panel
asynchronously to the main MUI application in a separate process.

If your panel needs some special setup then do that before passing the method to
Panel class. Vice versa if your panel needs some special cleanup then do that
after the method returns from Panel class.

### INPUTS
**`Object *app`**
     the application object to let the panel run asynchronously to the main
     application.

**`Object *win`**
     the window object containing the panel object.

### NOTES
If the window could be opened successfully by this method it will stay open
afterwards, e.g. for inspection of its position and size.

### RESULT
A boolean value indicating whether "running" the panel succeeded or not.

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
