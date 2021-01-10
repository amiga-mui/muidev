# Palette.mui
## Super class
[Group.mui](MUI_Group.md)
## Background
OBSOLETE!
There are better ways to define colors now. Check out Poppen class for an
example.

OLD DOCUMENTATION:
Palette class generates a (big) group of objects, alltogether making up a
powerful palette requester. Due to the new color selection schemes of
Kickstart 3.x, you won't get a "traditional" palette requester with 2^n
fields to fill in. These things really stop making sense on nice 256 or true
color screens.

Instead, MUI's palette class allows defining a list of colors that the user
should be able to adjust. Within a public screen manager, this would e.g. be
the DrawInfo pens for a specific screen, within a terminal program maybe the
eight ANSI colors.

Palette class uses a listview to let the user choose the desired color, a
coloradjust object to adjust this color and a colorfield object that always
shows the current color.

The user will also be able to concatenate several colors in the list,
defining a single color for several entries.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Palette_Entries](MUI_Palette.md/#MUIA_Palette_Entries)|V6|I.G|`struct MUI_Palette_Entry *`
[MUIA_Palette_Groupable](MUI_Palette.md/#MUIA_Palette_Groupable)|V6|ISG|`BOOL`
[MUIA_Palette_Names](MUI_Palette.md/#MUIA_Palette_Names)|V6|ISG|`STRPTR *`

## MUIA_Palette_Entries
### NAME
[MUIA_Palette_Entries](MUI_Palette.md/#MUIA_Palette_Entries) -- V6 [I.G], `struct MUI_Palette_Entry *`, 0x8042a3d8

### FUNCTION
Specify the colors that the user should be able to adjust with this palette
object.

You supply an array of MUI_Palette_Structures here, each entry defining one
color:

```c++
struct MUI_Palette_Entry
{
  LONG  mpe_ID;
  ULONG mpe_Red;
  ULONG mpe_Green;
  ULONG mpe_Blue;
  LONG  mpe_Group;
};
```

**`mpe_ID`**
     This entry is not used by palette class, you can put in whatever
     you want, except the value MUIV_Palette_Entry_End (==-1), which
     terminates the array.

**`mpe_Red`**
     32-bit red component of the current color. This field will be
     changed by palette class whenever the user edits the color.

**`mpe_Green`**
     32-bit green component of the current color. This field will be
     changed by palette class whenever the user edits the color.

**`mpe_Blue`**
     32-bit blue component of the current color. This field will be
     changed by palette class whenever the user edits the color.

**`mpe_Group`**
     Entries with the same mpe_Group value are concatenated. Whenever
     a new color in the listview is selected, all other colors with
     the same mpe_Group get selected as well and get adjusted all at
     once.
     Entry concatenation can be changed by the user, as long as you
     don't disable this feature with the [MUIA_Palette_Groupable](MUI_Palette.md/#MUIA_Palette_Groupable)
     attribute.

### EXAMPLE
```c++
static struct MUI_Palette_Entry SystemDefaultPalette[] =
{
  { TEXTPEN,          0x00000000, 0x00000000, 0x00000000, 2 },
  { SHINEPEN,         0xffffffff, 0xffffffff, 0xffffffff, 4 },
  { SHADOWPEN,        0x00000000, 0x00000000, 0x00000000, 5 },
  { FILLPEN,          0x66666666, 0x88888888, 0xbbbbbbbb, 3 },
  { FILLTEXTPEN,      0xffffffff, 0xffffffff, 0xffffffff, 6 },
  { BACKGROUNDPEN,    0x00000000, 0x00000000, 0x00000000, 7 },
  { HIGHLIGHTTEXTPEN, 0xffffffff, 0xffffffff, 0xffffffff, 8 },
  { BARDETAILPEN,     0x00000000, 0x00000000, 0x00000000, 9 },
  { BARBLOCKPEN,      0xffffffff, 0xffffffff, 0xffffffff, 1 },
  { BARTRIMPEN,       0x00000000, 0x00000000, 0x00000000, 0 },
  { MUIV_Palette_Entry_End, 0, 0, 0, 0 },
};
```

### SEE ALSO
[MUIA_Palette_Names](MUI_Palette.md/#MUIA_Palette_Names)

## MUIA_Palette_Groupable
### NAME
[MUIA_Palette_Groupable](MUI_Palette.md/#MUIA_Palette_Groupable) -- V6 [ISG], `BOOL`, 0x80423e67

### FUNCTION
Enables/disables palette color grouping.

Defaults to TRUE.

### SEE ALSO
[MUIA_Palette_Entries](MUI_Palette.md/#MUIA_Palette_Entries)

## MUIA_Palette_Names
### NAME
[MUIA_Palette_Names](MUI_Palette.md/#MUIA_Palette_Names) -- V6 [ISG], `STRPTR *`, 0x8042c3a2

### FUNCTION
Specify the names of a palette objects color entries. Without names, the
color listview just displays "Color <n>" for each entry. If you supply an
array of names here, they are displayed instead. The names array must have
as many entries as the array of MUI_Palette_Entry structures (without its
terminator).

### EXAMPLE
```c++
static struct MUI_Palette_Entry ColorEntries[] =
{
  { TEXTPEN,          0x00000000, 0x00000000, 0x00000000, 2 },
  { SHINEPEN,         0xffffffff, 0xffffffff, 0xffffffff, 4 },
  { SHADOWPEN,        0x00000000, 0x00000000, 0x00000000, 5 },
  { FILLPEN,          0x66666666, 0x88888888, 0xbbbbbbbb, 3 },
  { FILLTEXTPEN,      0xffffffff, 0xffffffff, 0xffffffff, 6 },
  { BACKGROUNDPEN,    0x00000000, 0x00000000, 0x00000000, 7 },
  { HIGHLIGHTTEXTPEN, 0xffffffff, 0xffffffff, 0xffffffff, 8 },
  { BARDETAILPEN,     0x00000000, 0x00000000, 0x00000000, 9 },
  { BARBLOCKPEN,      0xffffffff, 0xffffffff, 0xffffffff, 1 },
  { BARTRIMPEN,       0x00000000, 0x00000000, 0x00000000, 0 },
  { MUIV_Palette_Entry_End, 0, 0, 0, 0 },
};

static const char *ColorNames[] =
{
  "Text"                ,
  "Bright Edges"        ,
  "Dark Edges"          ,
  "Active Window Bars"  ,
  "Active Window Titles",
  "Background"          ,
  "Important Text"      ,
  "Menu Text"           ,
  "Menu Background"     ,
  "Menu Line"
};

po = PaletteObject,
  MUIA_Palette_Entries, ColorEntries,
  MUIA_Palette_Names, ColorNames,
  End;
```

### SEE ALSO
[MUIA_Palette_Entries](MUI_Palette.md/#MUIA_Palette_Entries)

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
