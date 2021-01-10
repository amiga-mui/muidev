# Radio.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
Radio class generates radio button gadgets. They do the same job as cycle
gadgets and eat up more window space, maybe that's the reason  why so few of
them can be found in existing applications.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Radio_Active](MUI_Radio.md/#MUIA_Radio_Active)|V4|ISG|`LONG`
[MUIA_Radio_Entries](MUI_Radio.md/#MUIA_Radio_Entries)|V4|I..|`STRPTR *`

## MUIA_Radio_Active
### NAME
[MUIA_Radio_Active](MUI_Radio.md/#MUIA_Radio_Active) -- V4 [ISG], `LONG`, 0x80429b41

### FUNCTION
This attributes defines the number of the active entry in the radio gadget.
Valid range is from 0 for the first entry to NumEntries-1 for the last.

Setting [MUIA_Radio_Active](MUI_Radio.md/#MUIA_Radio_Active) causes the gadget to be updated. On the other
hand, when the user plays around with the gadget, [MUIA_Radio_Active](MUI_Radio.md/#MUIA_Radio_Active) will
always reflects the current state.

### EXAMPLE
```c++
set(radioobj, MUIA_Radio_Active, 3);
```

### SEE ALSO
[MUIA_Radio_Entries](MUI_Radio.md/#MUIA_Radio_Entries)

## MUIA_Radio_Entries
### NAME
[MUIA_Radio_Entries](MUI_Radio.md/#MUIA_Radio_Entries) -- V4 [I..], `STRPTR *`, 0x8042b6a1

### FUNCTION
Here you can define what entries shall be displayed in your radio gadget. You
must supply a pointer to a string array, containing one entry for each item and
terminated with a NULL.

Remember that radio gadget entries may contain any text formatting code such as
bold, italic or underlined characters.

By default, MUI will place the entries vertically below each other. But since
Radio class is a subclass of Group class, you can use group layout attributes to
adjust the layout to your needs, e.g. [MUIA_Group_Horiz](MUI_Group.md/#MUIA_Group_Horiz), TRUE for a horizontal
radio button row or even [MUIA_Group_Rows](MUI_Group.md/#MUIA_Group_Rows)/Columns for a more fancy layout.

If you use these layout features, keep in mind that Radio class creates exactly
one child object for each entry.

### EXAMPLE
```c++
static const char *RA_GroupTitleColor[] =
{
  "normal",
  "highlight",
  "3-dimensional",
  NULL
};

CY_Title = RadioObject,
  MUIA_Radio_Entries, RA_GroupTitleColor,
  End;
```

### SEE ALSO
[MUIA_Radio_Active](MUI_Radio.md/#MUIA_Radio_Active), [MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents)

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
