# Selectgroup.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
Selectgroup objects combine radio buttons and labels or other visible objects
into a group of selectable options.

Well known example are the selection for the type of list scrollbars in MUI
prefs.

To be acting as a group with fully clickable option items at least one object
per option must have [MUIA_UserData](MUI_Notify.md/#MUIA_UserData) set to [MUIA_Selectgroup_Active](MUI_Selectgroup.md/#MUIA_Selectgroup_Active). Usually this
is done for the Radio button, as this kind of object is able to display the
active state by itself.

### EXAMPLE
```c++
Object *selButton(void)
{
  return ImageObject,
    MUIA_Image_Spec, MUII_RadioButton,
    MUIA_Image_FontMatch, TRUE,
    MUIA_ShowSelState, FALSE,
    MUIA_InputMode, MUIV_InputMode_Immediate,
    // this is the important information
    MUIA_UserData, MUIA_Selectgroup_Active,
  End;
}

// create a selection group with 3 options where the full entry (radio button
// plus label) is clickable
Object *selgroup;
selgroup = MUI_NewObject(MUIC_Selectgroup,
  MUIA_Group_Columns, 2,
  Child, selButton(),
  Child, MUI_MakeObject(MUIO_Label, "Option 1", MUIO_Label_LeftAligned),
  Child, selButton(),
  Child, MUI_MakeObject(MUIO_Label, "Option 2", MUIO_Label_LeftAligned),
  Child, selButton(),
  Child, MUI_MakeObject(MUIO_Label, "Option 3", MUIO_Label_LeftAligned),
TAG_DONE);
```
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Selectgroup_Active](MUI_Selectgroup.md/#MUIA_Selectgroup_Active)|V21|ISG|`LONG`

## MUIA_Selectgroup_Active
### NAME
[MUIA_Selectgroup_Active](MUI_Selectgroup.md/#MUIA_Selectgroup_Active) -- V21 [ISG], `LONG`, 0x80421788

### SPECIAL INPUTS
  * MUIV_Selectgroup_Active_Next
  * MUIV_Selectgroup_Active_Prev

### FUNCTION
This attributes defines the number of the active entry in the selection group.
Valid range is from 0 for the first entry to NumEntries-1 for the last.

Setting [MUIA_Selectgroup_Active](MUI_Selectgroup.md/#MUIA_Selectgroup_Active) causes the gadget to be updated. On the other
hand, when the user plays around with the gadget, [MUIA_Selectgroup_Active](MUI_Selectgroup.md/#MUIA_Selectgroup_Active) will
always reflect the current state.

Using MUIV_Selectgroup_Active_Next and MUIV_Selectgroup_Active_Prev as attribute
value during set causes the gadget to cycle through its entries in the given
direction.

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
