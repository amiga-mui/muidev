# Register.mui
## Super class
[Group.mui](MUI_Group)
## Inherited by
* [Penadjust.mui](MUI_Penadjust)
## Background
Register class is a special class for handling multi page groups. Using this
class, you only have to supply an array of strings, describing the
children's titles. How these titles are visualized, either with a cycle
gadget of with a register-like group, is the choice of the user.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Register_Frame](MUI_Register.md/#MUIA_Register_Frame)|V7|I.G|`BOOL` **(OBSOLETE)**
[MUIA_Register_Titles](MUI_Register.md/#MUIA_Register_Titles)|V7|ISG|`STRPTR *`

## MUIA_Register_Frame
### NAME
[MUIA_Register_Frame](MUI_Register/#MUIA_Register_Frame) -- V7 [I.G], `BOOL`, 0x8042349b **(OBSOLETE)**

### FUNCTION

OLD AND OBSOLETE DOCUMENTATION
Specify TRUE if your want your group to be framed. If the user specified
cycle gadget looking, you will get a group frame, otherwise you won't get
any frame at all since register groups are framed anyway.

### SEE ALSO
[MUIA_Register_Titles](MUI_Register/#MUIA_Register_Titles)

## MUIA_Register_Titles
### NAME
[MUIA_Register_Titles](MUI_Register/#MUIA_Register_Titles) -- V7 [ISG], `STRPTR *`, 0x804297ec

### SPECIAL INPUTS
  * MUIV_Register_Titles_UData
  * MUIV_Register_Titles_Frame

### FUNCTION
NULL terminated array of strings describing the titles of your groups
children. This array must contain exactly as many entries as your group has
children.

### EXAMPLE
```c++
static const char *titles[] = { "Eyes", "Ears", "Noses", "Feet", NULL };

obj = RegisterGroup(titles),
  Child, ...,
  Child, ...,
  Child, ...,
  Child, ...,
  End;
```

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
