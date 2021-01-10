# Prop.mui
## Super class
[Gadget.mui](MUI_Gadget.md)
## Background
Prop class generates the well known proportional gadgets. It offers the same
attributes as a usual boopsi gadget of propgclass. However, MUI's prop
gadgets allow using any imagery for the knob and for the background.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Prop_DeltaFactor](MUI_Prop.md/#MUIA_Prop_DeltaFactor)|V4|ISG|`LONG`
[MUIA_Prop_Entries](MUI_Prop.md/#MUIA_Prop_Entries)|V4|ISG|`LONG`
[MUIA_Prop_First](MUI_Prop.md/#MUIA_Prop_First)|V4|ISG|`LONG`
[MUIA_Prop_Horiz](MUI_Prop.md/#MUIA_Prop_Horiz)|V4|I.G|`BOOL`
[MUIA_Prop_Slider](MUI_Prop.md/#MUIA_Prop_Slider)|V4|ISG|`BOOL` **(OBSOLETE)**
[MUIA_Prop_UseWinBorder](MUI_Prop.md/#MUIA_Prop_UseWinBorder)|V13|I..|`LONG`
[MUIA_Prop_Visible](MUI_Prop.md/#MUIA_Prop_Visible)|V4|ISG|`LONG`

## Methods
Method|Version
------|-------
[MUIM_Prop_Decrease](MUI_Prop.md/#MUIM_Prop_Decrease)|V16
[MUIM_Prop_Increase](MUI_Prop.md/#MUIM_Prop_Increase)|V16

## MUIA_Prop_DeltaFactor
### NAME
[MUIA_Prop_DeltaFactor](MUI_Prop/#MUIA_Prop_DeltaFactor) -- V4 [ISG], `LONG`, 0x80427c5e

### FUNCTION
Set or get an additional delta factor to speed up keyboard navigation. All
"fast" movements, like "alt+cursor up", will be multiplied by this factor.

Defaults to 1.

### SEE ALSO
[MUIA_Prop_Visible](MUI_Prop/#MUIA_Prop_Visible), [MUIA_Prop_Entries](MUI_Prop/#MUIA_Prop_Entries)

## MUIA_Prop_Entries
### NAME
[MUIA_Prop_Entries](MUI_Prop/#MUIA_Prop_Entries) -- V4 [ISG], `LONG`, 0x8042fbdb

### FUNCTION
Set or get the total number of entries.

### SEE ALSO
[MUIA_Prop_Horiz](MUI_Prop/#MUIA_Prop_Horiz), [MUIA_Prop_Visible](MUI_Prop/#MUIA_Prop_Visible), [MUIA_Prop_First](MUI_Prop/#MUIA_Prop_First)

## MUIA_Prop_First
### NAME
[MUIA_Prop_First](MUI_Prop/#MUIA_Prop_First) -- V4 [ISG], `LONG`, 0x8042d4b2

### FUNCTION
Set or get the number of the first entry.

### SEE ALSO
[MUIA_Prop_Horiz](MUI_Prop/#MUIA_Prop_Horiz), [MUIA_Prop_Visible](MUI_Prop/#MUIA_Prop_Visible), [MUIA_Prop_Entries](MUI_Prop/#MUIA_Prop_Entries)

## MUIA_Prop_Horiz
### NAME
[MUIA_Prop_Horiz](MUI_Prop/#MUIA_Prop_Horiz) -- V4 [I.G], `BOOL`, 0x8042f4f3

### FUNCTION
Determine if you want a horizontal or a vertical prop gadget.

Defaults to FALSE, i.e. vertical.

### SEE ALSO
[MUIA_Prop_Entries](MUI_Prop/#MUIA_Prop_Entries), [MUIA_Prop_First](MUI_Prop/#MUIA_Prop_First), [MUIA_Prop_Visible](MUI_Prop/#MUIA_Prop_Visible)

## MUIA_Prop_Slider
### NAME
[MUIA_Prop_Slider](MUI_Prop/#MUIA_Prop_Slider) -- V4 [ISG], `BOOL`, 0x80429c3a **(OBSOLETE)**

### FUNCTION
OBSOLETE. DO NOT USE. PREVIOUSLY:
Indicate that this prop gadget is used in a slider. MUI might then use
different imagery. Since you really should use the slider class when
creating sliders, you normally don't need to care about this attribute.

## MUIA_Prop_UseWinBorder
### NAME
[MUIA_Prop_UseWinBorder](MUI_Prop/#MUIA_Prop_UseWinBorder) -- V13 [I..], `LONG`, 0x8042deee

### SPECIAL INPUTS
  * MUIV_Prop_UseWinBorder_None
  * MUIV_Prop_UseWinBorder_Left
  * MUIV_Prop_UseWinBorder_Right
  * MUIV_Prop_UseWinBorder_Bottom

### FUNCTION
If you set this attribute to one of

MUIV_Prop_UseWinBorder_Left,
MUIV_Prop_UseWinBorder_Right,
MUIV_Prop_UseWinBorder_Bottom,

some very special magic will take place with this proportional gadget. In fact,
it will not eat any display space at all or render anything, it stays invisible
in your windows GUI. Instead, the gadgets control and display will be linked to
one of the scrollbars in the window border.

There is no difference in talking to the object, you can use all prop gadget
attributes regardless whether its a real prop gadget or just a window border
link. Of course, gadgets in window borders will use the intuition look
regardless what the user has configured.

### NOTES
You **MUST** enable border scrollers for the parent window with the
corresponding attributes (see below) before using [MUIA_Prop_UseWinBorder](MUI_Prop/#MUIA_Prop_UseWinBorder).

Obviously, you can only link exactly one prop gadget to one window scroller.
Linking more than one gadget to the same window scroller will result in big
confusion.

To simplify programming, the classes Scrollbar class and Listview class also
accept the [MUIA_Prop_UseWinBorder](MUI_Prop/#MUIA_Prop_UseWinBorder) attribute and pass it on when creating their
prop gadgets. This allows you to do something like

```c++
WindowObject,
  MUIA_Window_UseRightBorderScroller, TRUE,
  MUIA_Window_RootObject, VGroup,
    Child, ListviewObject,
      MUIA_Prop_UseWinBorder, MUIV_Prop_UseWinBorder_Right,
      ...
```

to create a listview thats controllable with a scrollbar in the right window
border.

Scrollgroup class (for virtual groups) features another attribute called
[MUIA_Scrollgroup_UseWinBorder](MUI_Scrollgroup/#MUIA_Scrollgroup_UseWinBorder), TRUE/FALSE to allow control of virtual group from
window borders.

### SEE ALSO
[MUIA_Window_UseBottomBorderScroller](MUI_Window/#MUIA_Window_UseBottomBorderScroller), [MUIA_Window_UseLeftBorderScroller](MUI_Window/#MUIA_Window_UseLeftBorderScroller),
[MUIA_Window_UseRightBorderScroller](MUI_Window/#MUIA_Window_UseRightBorderScroller), [MUIA_Scrollgroup_UseWinBorder](MUI_Scrollgroup/#MUIA_Scrollgroup_UseWinBorder)

## MUIA_Prop_Visible
### NAME
[MUIA_Prop_Visible](MUI_Prop/#MUIA_Prop_Visible) -- V4 [ISG], `LONG`, 0x8042fea6

### FUNCTION
Set or get the number of visible entries.

### SEE ALSO
[MUIA_Prop_Horiz](MUI_Prop/#MUIA_Prop_Horiz), [MUIA_Prop_Entries](MUI_Prop/#MUIA_Prop_Entries), [MUIA_Prop_First](MUI_Prop/#MUIA_Prop_First)

## MUIM_Prop_Decrease
### NAME
[MUIM_Prop_Decrease](MUI_Prop/#MUIM_Prop_Decrease) -- V16, 0x80420dd1

### SYNOPSIS
`DoMethod(obj, MUIM_Prop_Decrease, LONG amount);`

### FUNCTION
This method decreases the value of a proportional gadget by the specified
amount. Negative values are ok. Range checking is done automatically.

### INPUTS
**`LONG amount`**
     amount to substract from the gadgets current position.

### SEE ALSO
[MUIM_Prop_Increase](MUI_Prop/#MUIM_Prop_Increase), [MUIA_Prop_First](MUI_Prop/#MUIA_Prop_First)

## MUIM_Prop_Increase
### NAME
[MUIM_Prop_Increase](MUI_Prop/#MUIM_Prop_Increase) -- V16, 0x8042cac0

### SYNOPSIS
`DoMethod(obj, MUIM_Prop_Increase, LONG amount);`

### FUNCTION
This method increases the value of a proportional gadget by the specified
amount. Negative values are ok. Range checking is done automatically.

### INPUTS
**`LONG amount`**
     amount to add to the gadgets current position.

### SEE ALSO
[MUIM_Prop_Decrease](MUI_Prop/#MUIM_Prop_Decrease), [MUIA_Prop_First](MUI_Prop/#MUIA_Prop_First)

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
