# Virtgroup.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
Virtgroup class generates special kinds of group objects whose children can
be a lot larger than the actual group. The group acts as a (small) window
through which a rectangle area of its contents is visible.

During layout, MUI tries to place the children of a virtual group in the
visible part. If this is impossible, space is extended as long as all
children fit.

Virtual groups themselves don't offer any scrollbars to allow user
interaction. These things are handled by scrollgroup class. Usually, you
don't want to use a virtual group without a scrollgroup.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Virtgroup_Height](MUI_Virtgroup.md/#MUIA_Virtgroup_Height)|V6|..G|`LONG`
[MUIA_Virtgroup_Input](MUI_Virtgroup.md/#MUIA_Virtgroup_Input)|V11|I..|`BOOL`
[MUIA_Virtgroup_Left](MUI_Virtgroup.md/#MUIA_Virtgroup_Left)|V6|ISG|`LONG`
[MUIA_Virtgroup_Top](MUI_Virtgroup.md/#MUIA_Virtgroup_Top)|V6|ISG|`LONG`
[MUIA_Virtgroup_TryFit](MUI_Virtgroup.md/#MUIA_Virtgroup_TryFit)|V20|ISG|`BOOL`
[MUIA_Virtgroup_Width](MUI_Virtgroup.md/#MUIA_Virtgroup_Width)|V6|..G|`LONG`

## MUIA_Virtgroup_Height
### NAME
[MUIA_Virtgroup_Height](MUI_Virtgroup.md/#MUIA_Virtgroup_Height) -- V6 [..G], `LONG`, 0x80423038

### FUNCTION
Read the virtual height of a virtual group.

This attribute is quite senseless, better use a scrollgroup object to
control the virtual group.

### SEE ALSO
[MUIA_Virtgroup_Width](MUI_Virtgroup.md/#MUIA_Virtgroup_Width), [MUIA_Virtgroup_Left](MUI_Virtgroup.md/#MUIA_Virtgroup_Left), [MUIA_Virtgroup_Top](MUI_Virtgroup.md/#MUIA_Virtgroup_Top)

## MUIA_Virtgroup_Input
### NAME
[MUIA_Virtgroup_Input](MUI_Virtgroup.md/#MUIA_Virtgroup_Input) -- V11 [I..], `BOOL`, 0x80427f7e

### FUNCTION
Specify if a virtual group should be moveable by clicking into it and
dragging the mouse.

Defaults to TRUE.

## MUIA_Virtgroup_Left
### NAME
[MUIA_Virtgroup_Left](MUI_Virtgroup.md/#MUIA_Virtgroup_Left) -- V6 [ISG], `LONG`, 0x80429371

### FUNCTION
Get/set the virtual left edge of a virtual group. The left edge will
automatically be clipped to be between 0 and (VirtualWidth-DisplayWidth).

This attribute is quite senseless, better use a scrollgroup object to
control the virtual group.

### SEE ALSO
[MUIA_Virtgroup_Width](MUI_Virtgroup.md/#MUIA_Virtgroup_Width), [MUIA_Virtgroup_Height](MUI_Virtgroup.md/#MUIA_Virtgroup_Height), [MUIA_Virtgroup_Top](MUI_Virtgroup.md/#MUIA_Virtgroup_Top)

## MUIA_Virtgroup_Top
### NAME
[MUIA_Virtgroup_Top](MUI_Virtgroup.md/#MUIA_Virtgroup_Top) -- V6 [ISG], `LONG`, 0x80425200

### FUNCTION
Get/set the virtual top edge of a virtual group. The top edge will
automatically be clipped to be between 0 and (VirtualTop-DisplayTop).

This attribute is quite senseless, better use a scrollgroup object to
control the virtual group.

### SEE ALSO
[MUIA_Virtgroup_Width](MUI_Virtgroup.md/#MUIA_Virtgroup_Width), [MUIA_Virtgroup_Height](MUI_Virtgroup.md/#MUIA_Virtgroup_Height), [MUIA_Virtgroup_Left](MUI_Virtgroup.md/#MUIA_Virtgroup_Left)

## MUIA_Virtgroup_TryFit
### NAME
[MUIA_Virtgroup_TryFit](MUI_Virtgroup.md/#MUIA_Virtgroup_TryFit) -- V20 [ISG], `BOOL`, 0x80429427

### FUNCTION
During a layout, the virtgroup will first try to force a window size large
enough to fit the whole object. In case it still would not fit, the window
gets resized to the maximum allowed by the screen size.

## MUIA_Virtgroup_Width
### NAME
[MUIA_Virtgroup_Width](MUI_Virtgroup.md/#MUIA_Virtgroup_Width) -- V6 [..G], `LONG`, 0x80427c49

### FUNCTION
Read the virtual width of a virtual group.

This attribute is quite senseless, better use a scrollgroup object to
control the virtual group.

### SEE ALSO
[MUIA_Virtgroup_Height](MUI_Virtgroup.md/#MUIA_Virtgroup_Height), [MUIA_Virtgroup_Left](MUI_Virtgroup.md/#MUIA_Virtgroup_Left), [MUIA_Virtgroup_Top](MUI_Virtgroup.md/#MUIA_Virtgroup_Top)

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
