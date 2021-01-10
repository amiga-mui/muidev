# Aboutmui.mui
## Super class
[Window.mui](MUI_Window)
## Background
This class can be used to display a MUI about window in MUI applications. Add a
"Project/About MUI..." menu item and make it do something like this:

```c++
if(aboutwin == NULL)
{
  aboutwin = AboutmuiObject,
    MUIA_Window_RefWindow, obj,
    MUIA_Aboutmui_Application, MyAppObject,
    End;
}

if(aboutwin != NULL)
  set(aboutwin, MUIA_Window_Open, TRUE);
else
  DisplayBeep(0);
```

You don't have to care about the window any longer, it will take care about
closing itself and will get disposed when the application is removed.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Aboutmui_Application](MUI_Aboutmui.md/#MUIA_Aboutmui_Application)|V11|I..|`Object *`

## MUIA_Aboutmui_Application
### NAME
[MUIA_Aboutmui_Application](MUI_Aboutmui/#MUIA_Aboutmui_Application) -- V11 [I..], `Object *`, 0x80422523

### FUNCTION
Inform the Aboutmui object about the application. If you don't specifiy this,
Aboutmui class will just create a normal window object and will leave the
responsibility about closing itself to the programmer.

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
