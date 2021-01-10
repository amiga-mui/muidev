# Scrollbar.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
The Scrollbar class has no objects and attributes itself. It just connects a
proportional gadget and two button gadgets with approriate imagery to make
up a scrollbar.

Since Scrollbar class is a subclass of Group class, every attribute and
method is passed through to all of its children. Thus, you can talk and
listen to a scrollbar as if it was just a single prop gadget.

You can use the attribute [MUIA_Group_Horiz](MUI_Group.md/#MUIA_Group_Horiz) as with any other group to
determine if the scrollbar should be horizontal or vertical. By default,
a vertical scrollbar is generated.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Scrollbar_IncDecSize](MUI_Scrollbar.md/#MUIA_Scrollbar_IncDecSize)|V20|ISG|`ULONG`
[MUIA_Scrollbar_Type](MUI_Scrollbar.md/#MUIA_Scrollbar_Type)|V11|I..|`LONG`

## MUIA_Scrollbar_IncDecSize
### NAME
[MUIA_Scrollbar_IncDecSize](MUI_Scrollbar.md/#MUIA_Scrollbar_IncDecSize) -- V20 [ISG], `ULONG`, 0x80426c07

### FUNCTION
Set the amount by which the scrollbar position is increased or decreased
whenever one of the arrow buttons is clicked.

Defaults to 1.

## MUIA_Scrollbar_Type
### NAME
[MUIA_Scrollbar_Type](MUI_Scrollbar.md/#MUIA_Scrollbar_Type) -- V11 [I..], `LONG`, 0x8042fb6b

### SPECIAL INPUTS
  * MUIV_Scrollbar_Type_Default
  * MUIV_Scrollbar_Type_Bottom
  * MUIV_Scrollbar_Type_Top
  * MUIV_Scrollbar_Type_Sym
  * MUIV_Scrollbar_Type_None

### FUNCTION
Specify a certain scrollbar type. Normally, you should respect the users
choice and avoid using this attribute.

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
