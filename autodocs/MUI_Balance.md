# Balance.mui
## Super class
[Area.mui](MUI_Area.md)
## Background
The Balance class is very simple. Inserting objects of this class somewhere in
your group (only horizontal or vertical groups, nothing 2-dimensional) allows
your users to dynamically change the weight of your children.

Since MUI5 2018R1 (muimaster.library 21.121) Balance class implements the
additional features of BetterBalance.mcc. This means that the user can save
and restore the balanced weights of the neighboring objects for each Balance
object with a unique [MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID) during [MUIM_Application_Save](MUI_Application.md/#MUIM_Application_Save) and
[MUIM_Application_Load](MUI_Application.md/#MUIM_Application_Load).

Something like this will automatically restore and save the weights of the two
Rectangle objects:

```c++
HGroup,
  Child, RectangleObject, TextFrame, End,
  Child, BalanceObject, MUIA_ObjectID, 0x12345678, End,
  Child, RectangleObject, TextFrame, End,
End,

// restore the formerly saved weights before the window is opened
DoMethod(app, MUIM_Application_Load, MUIV_Application_Load_ENV);

[... main loop ...]

// save the current weight upon application termination
DoMethod(app, MUIM_Application_Save, MUIV_Application_Save_ENV);
```

Of course the application might override [MUIM_Application_SnapshotWindow](MUI_Application.md/#MUIM_Application_SnapshotWindow) to save
the weight during snapshotting the window or provide a special "Save" button for
that purpose.

Refer to the source of the Balancing demo for more details.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Balance_Quiet](MUI_Balance.md/#MUIA_Balance_Quiet)|V20|I..|`LONG`

## MUIA_Balance_Quiet
### NAME
[MUIA_Balance_Quiet](MUI_Balance.md/#MUIA_Balance_Quiet) -- V20 [I..], `LONG`, 0x80427486

### FUNCTION
If set to TRUE the balance object will show its frame only if the mouse is
located over the object. Otherwise it will be invisible.

Defaults to FALSE.

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
