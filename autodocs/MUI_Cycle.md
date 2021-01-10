# Cycle.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
Cycle class generates the well known cycle gadgets. However, MUI cycle
gadgets feature a (configurable) popup menu to avoid clicking through many
entries.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Cycle_Active](MUI_Cycle.md/#MUIA_Cycle_Active)|V4|ISG|`LONG`
[MUIA_Cycle_Entries](MUI_Cycle.md/#MUIA_Cycle_Entries)|V4|IS.|`STRPTR *`

## MUIA_Cycle_Active
### NAME
[MUIA_Cycle_Active](MUI_Cycle.md/#MUIA_Cycle_Active) -- V4 [ISG], `LONG`, 0x80421788

### SPECIAL INPUTS
  * MUIV_Cycle_Active_Next
  * MUIV_Cycle_Active_Prev

### FUNCTION
This attributes defines the number of the active entry in the cycle gadget.
Valid range is from 0 for the first entry to NumEntries-1 for the last.

Setting [MUIA_Cycle_Active](MUI_Cycle.md/#MUIA_Cycle_Active) causes the gadget to be updated. On the other
hand, when the user plays around with the gadget, [MUIA_Cycle_Active](MUI_Cycle.md/#MUIA_Cycle_Active) will
always reflect the current state.

Using MUIV_Cycle_Active_Next and MUIV_Cycle_Active_Prev as attribute value
during set causes the gadget to cycle through its entries in the given
direction.

### EXAMPLE
```c++
set(cycleobj, MUIA_Cycle_Active, 3);
```

### SEE ALSO
[MUIA_Cycle_Entries](MUI_Cycle.md/#MUIA_Cycle_Entries)

## MUIA_Cycle_Entries
### NAME
[MUIA_Cycle_Entries](MUI_Cycle.md/#MUIA_Cycle_Entries) -- V4 [IS.], `STRPTR *`, 0x80420629

### FUNCTION
Here you can define what entries shall be displayed in your cycle gadget.
You must supply a pointer to a string array, containing one entry for each
item and terminated with a NULL.

Remember that cycle gadget entries may contain any text formatting code such
as bold, italic or underlined characters.

Cycle gadgets set the preparse string for all entries to "\33c", this means
that they will automatically appear centered. Of course you can override
this by simply preceding your entries with own formatting code.

### EXAMPLE
```c++
static const char *CYA_GroupTitleColor[] =
{
  "normal",
  "highlight",
  "3-dimensional",
  NULL
};

CY_Title = CycleObject,
  MUIA_Cycle_Entries, CYA_GroupTitleColor,
  End;
```

### SEE ALSO
[MUIA_Cycle_Active](MUI_Cycle.md/#MUIA_Cycle_Active), [MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents)

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
