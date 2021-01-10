# Poppen.mui
## Super class
[Pendisplay.mui](MUI_Pendisplay.md)
## Background
Poppen class adds input capabilities to its super class Pendisplay. It
should be used if your application allows users to configure some custom
pens for rendering.

A Poppen object will appear as kind of a button which displays the currently
selected color. When the user hits the button, a Popup window containing a
Penadjust object opens up and lets the user choose change the color.

You can control the window title of the popup window using the
[MUIA_Window_Title](MUI_Window.md/#MUIA_Window_Title) on the Poppen object. It will remember its value and use
it when creating the popup window.

As most MUI popups, the Penadjust popup window runs asynchronously and stays
there until the user terminates it with "OK" or "Cancel". Furthermore, if
the popup window is automatically cancelled if the pop button receives a
[MUIM_Cleanup](MUI_Area.md/#MUIM_Cleanup) method.

Anyway, you don't have to care about the internals of this class. Just
create it like

```c++
obj = MUI_NewObject(MUIC_Poppen,
  MUIA_CycleChain , 1,
  MUIA_Window_Title, "Color of Followed Links",
  TAG_DONE);
```

somewhere in your prefs window and everything will be fine. You can get/set
the current color from a Poppen object by using the [MUIA_Pendisplay_Spec](MUI_Pendisplay.md/#MUIA_Pendisplay_Spec)
attribute. The resulting struct MUI_SpenSpec may then be saved somewhere in
your preferences and used as parameter for MUI_ObtainPen() and
MUI_ReleasePen().

You can find some example code on using this class in the Class2 demo of the
MUI distribution.
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
