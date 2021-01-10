# Scrollgroup.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
Scrollgroup objects can be used to supply virtual groups with scrollbars.
These scrollbars automatically adjust according to the virtual and display
sizes of the underlying virtual group. When scrolling is unnecessary (i.e.
the virtual group is completely visible), the scrollers might get disabled
or even disappear completely, depending on the users preferences settings.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Scrollgroup_AutoBars](MUI_Scrollgroup.md/#MUIA_Scrollgroup_AutoBars)|V20|ISG|`BOOL`
[MUIA_Scrollgroup_Contents](MUI_Scrollgroup.md/#MUIA_Scrollgroup_Contents)|V4|I.G|`Object *`
[MUIA_Scrollgroup_FreeHoriz](MUI_Scrollgroup.md/#MUIA_Scrollgroup_FreeHoriz)|V9|I..|`BOOL`
[MUIA_Scrollgroup_FreeVert](MUI_Scrollgroup.md/#MUIA_Scrollgroup_FreeVert)|V9|I..|`BOOL`
[MUIA_Scrollgroup_HorizBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_HorizBar)|V16|..G|`Object *`
[MUIA_Scrollgroup_NoHorizBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_NoHorizBar)|V20|ISG|`BOOL`
[MUIA_Scrollgroup_NoVertBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_NoVertBar)|V20|ISG|`BOOL`
[MUIA_Scrollgroup_UseWinBorder](MUI_Scrollgroup.md/#MUIA_Scrollgroup_UseWinBorder)|V13|I..|`BOOL`
[MUIA_Scrollgroup_VertBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_VertBar)|V16|..G|`Object *`

## MUIA_Scrollgroup_AutoBars
### NAME
[MUIA_Scrollgroup_AutoBars](MUI_Scrollgroup.md/#MUIA_Scrollgroup_AutoBars) -- V20 [ISG], `BOOL`, 0x8042f50e

### FUNCTION
Specify if a scroll group's scrollbars should appear and vanish on demand.

Defaults to FALSE.

## MUIA_Scrollgroup_Contents
### NAME
[MUIA_Scrollgroup_Contents](MUI_Scrollgroup.md/#MUIA_Scrollgroup_Contents) -- V4 [I.G], `Object *`, 0x80421261

### FUNCTION
You have to specify an object of Virtgroup class here.

## MUIA_Scrollgroup_FreeHoriz
### NAME
[MUIA_Scrollgroup_FreeHoriz](MUI_Scrollgroup.md/#MUIA_Scrollgroup_FreeHoriz) -- V9 [I..], `BOOL`, 0x804292f3

### FUNCTION
Specify if a scroll group should be horizontally moveable.

Defaults to TRUE.

## MUIA_Scrollgroup_FreeVert
### NAME
[MUIA_Scrollgroup_FreeVert](MUI_Scrollgroup.md/#MUIA_Scrollgroup_FreeVert) -- V9 [I..], `BOOL`, 0x804224f2

### FUNCTION
Specify if a scroll group should be vertically moveable.

Defaults to TRUE.

## MUIA_Scrollgroup_HorizBar
### NAME
[MUIA_Scrollgroup_HorizBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_HorizBar) -- V16 [..G], `Object *`, 0x8042b63d

### FUNCTION
Returns the object pointer of a scrollgroup's scrollbar object for
horizontal scrolling. Can be NULL in a vertical only scrollgroup.

### SEE ALSO
[MUIA_Scrollgroup_VertBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_VertBar), [MUIA_Scrollgroup_FreeHoriz](MUI_Scrollgroup.md/#MUIA_Scrollgroup_FreeHoriz),
[MUIA_Scrollgroup_FreeVert](MUI_Scrollgroup.md/#MUIA_Scrollgroup_FreeVert)

## MUIA_Scrollgroup_NoHorizBar
### NAME
[MUIA_Scrollgroup_NoHorizBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_NoHorizBar) -- V20 [ISG], `BOOL`, 0x8042cab1

### FUNCTION
Don't add a horizontal scrollbar even if is would be needed.

### SEE ALSO
[MUIA_Scrollgroup_AutoBars](MUI_Scrollgroup.md/#MUIA_Scrollgroup_AutoBars), [MUIA_Scrollgroup_NoVertBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_NoVertBar)

## MUIA_Scrollgroup_NoVertBar
### NAME
[MUIA_Scrollgroup_NoVertBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_NoVertBar) -- V20 [ISG], `BOOL`, 0x804264c3

### FUNCTION
Don't add a vertical scrollbar even if is would be needed.

### SEE ALSO
[MUIA_Scrollgroup_AutoBars](MUI_Scrollgroup.md/#MUIA_Scrollgroup_AutoBars), [MUIA_Scrollgroup_NoVertBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_NoVertBar)

## MUIA_Scrollgroup_UseWinBorder
### NAME
[MUIA_Scrollgroup_UseWinBorder](MUI_Scrollgroup.md/#MUIA_Scrollgroup_UseWinBorder) -- V13 [I..], `BOOL`, 0x804284c1

### FUNCTION
If you set this to TRUE, MUI will automatically make this scrollgroup
controllable from gadgets in the window border. MUI will use the right
border scroller if the virtual group is allowed to move vertically and the
bottom border scroller if the virtual group is allowed to move horizontally.

### NOTES
You must set the corresponding window attributes (see below) for your parent
window to use this feature.

This attribute is not the same as [MUIA_Prop_UseWinBorder](MUI_Prop.md/#MUIA_Prop_UseWinBorder). The latter one
allows to specify a border directly whereas [MUIA_Scrollgroup_UseWinBorder](MUI_Scrollgroup.md/#MUIA_Scrollgroup_UseWinBorder) is
just a BOOLEAN. MUI will decide which borders to use according to the
FreeHoriz and FreeVert settings.

### SEE ALSO
[MUIA_Window_UseBottomBorderScroller](MUI_Window.md/#MUIA_Window_UseBottomBorderScroller), [MUIA_Window_UseLeftBorderScroller](MUI_Window.md/#MUIA_Window_UseLeftBorderScroller),
[MUIA_Window_UseRightBorderScroller](MUI_Window.md/#MUIA_Window_UseRightBorderScroller), [MUIA_Prop_UseWinBorder](MUI_Prop.md/#MUIA_Prop_UseWinBorder),
[MUIA_Scrollgroup_FreeHoriz](MUI_Scrollgroup.md/#MUIA_Scrollgroup_FreeHoriz), [MUIA_Scrollgroup_FreeVert](MUI_Scrollgroup.md/#MUIA_Scrollgroup_FreeVert)

## MUIA_Scrollgroup_VertBar
### NAME
[MUIA_Scrollgroup_VertBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_VertBar) -- V16 [..G], `Object *`, 0x8042cdc0

### FUNCTION
Returns the object pointer of a scrollgroup's scrollbar object for vertical
scrolling. Can be NULL in a horizontall only scrollgroup.

### SEE ALSO
[MUIA_Scrollgroup_HorizBar](MUI_Scrollgroup.md/#MUIA_Scrollgroup_HorizBar), [MUIA_Scrollgroup_FreeHoriz](MUI_Scrollgroup.md/#MUIA_Scrollgroup_FreeHoriz),
[MUIA_Scrollgroup_FreeVert](MUI_Scrollgroup.md/#MUIA_Scrollgroup_FreeVert)

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
