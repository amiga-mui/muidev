# Numeric.mui
## Super class
[Area.mui](MUI_Area.md)
## Inherited by
* [Knob.mui](MUI_Knob)
* [Levelmeter.mui](MUI_Levelmeter)
* [Numericbutton.mui](MUI_Numericbutton)
* [Slider.mui](MUI_Slider)
## Background
Numeric class is the base class for everything that deals with the input (and
display) of integer numbers. Numeric class itself does not feature any GUI
elements, it just offers some basic attributes and methods which are common to
all types of sliders. Creating direct instances of this class usually doesn't
make any sense. Instead, use one of the included subclasses like Slider class,
Numericbutton class or Knob class to select the type of gadget you need.

Numeric class and the supplied subclasses communicate with a set of methods. By
writing subclasses which override some of them, you can change the behaviour of
all sliders to fit your requirements. You could e.g. enhance the builtin value
formatting code which is limited to simple printf-style strings by replacing the
[MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify) method with something more complicated. Or you turn your
sliders to logarithmic scales by replacing [MUIM_Numeric_ValueToScale](MUI_Numeric/#MUIM_Numeric_ValueToScale) and
[MUIM_Numeric_ScaleToValue](MUI_Numeric/#MUIM_Numeric_ScaleToValue).

Imagine you would like a slider which doesn't only display a users age but also
makes comments depending on the current value, e.g. "13 years (Teenie)" ...
"25 years (Twen)" ... All you have to do is to write a subclass of any of MUI's
builtin slider types which does nothing but replace [MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify) with
your code. See the supplied "Slidorama" demo program to see how this might work.

MUI features several different subclasses of Numeric class: Slider class creates
an ordinary slider like the ones of previous MUI releases. Numericbutton class
creates a space-saving slider, only the value is shown in the user interface as
kind of a button. When the user clicks on this button, a slider pops up to
adjust the value. Knob class displays a very nice designed turning wheel but
also offers popup possibilities for those who don't like turning a knob with the
mouse. "Slidorama" demo shows everything that is available.

All slider gadgets offer configuration options and make it easy for the user to
enable things he likes and disable things he dislikes. However, it's your choice
to decide which basic type of gadget shall be used.

If really none of the supplied subclasses of Numeric class suits your
requirements, you may of course write custom classes for numeric data input. If
you use Numeric class as base class, you won't need to think about the basic
stuff like minimum and maximum values and formatting.

Keyboard control (TAB, cursor keys, [MUIA_ControlChar](MUI_Area/#MUIA_ControlChar)) is handled my Numeric
class automatically, subclasses will not have to care about it.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Numeric_CheckAllSizes](MUI_Numeric.md/#MUIA_Numeric_CheckAllSizes)|V11|ISG|`BOOL`
[MUIA_Numeric_Default](MUI_Numeric.md/#MUIA_Numeric_Default)|V11|ISG|`LONG`
[MUIA_Numeric_Format](MUI_Numeric.md/#MUIA_Numeric_Format)|V11|ISG|`STRPTR`
[MUIA_Numeric_Max](MUI_Numeric.md/#MUIA_Numeric_Max)|V11|ISG|`LONG`
[MUIA_Numeric_Min](MUI_Numeric.md/#MUIA_Numeric_Min)|V11|ISG|`LONG`
[MUIA_Numeric_Reverse](MUI_Numeric.md/#MUIA_Numeric_Reverse)|V11|ISG|`BOOL`
[MUIA_Numeric_RevLeftRight](MUI_Numeric.md/#MUIA_Numeric_RevLeftRight)|V11|ISG|`BOOL`
[MUIA_Numeric_RevUpDown](MUI_Numeric.md/#MUIA_Numeric_RevUpDown)|V11|ISG|`BOOL`
[MUIA_Numeric_Value](MUI_Numeric.md/#MUIA_Numeric_Value)|V11|ISG|`LONG`

## Methods
Method|Version
------|-------
[MUIM_Numeric_Decrease](MUI_Numeric.md/#MUIM_Numeric_Decrease)|V11
[MUIM_Numeric_Increase](MUI_Numeric.md/#MUIM_Numeric_Increase)|V11
[MUIM_Numeric_ScaleToValue](MUI_Numeric.md/#MUIM_Numeric_ScaleToValue)|V11
[MUIM_Numeric_SetDefault](MUI_Numeric.md/#MUIM_Numeric_SetDefault)|V11
[MUIM_Numeric_Stringify](MUI_Numeric.md/#MUIM_Numeric_Stringify)|V11
[MUIM_Numeric_ValueToScale](MUI_Numeric.md/#MUIM_Numeric_ValueToScale)|V11

## MUIA_Numeric_CheckAllSizes
### NAME
[MUIA_Numeric_CheckAllSizes](MUI_Numeric/#MUIA_Numeric_CheckAllSizes) -- V11 [ISG], `BOOL`, 0x80421594

### FUNCTION
Setting this attribute to TRUE will cause all values between
[MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min) and [MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max) to be checked for their textual
dimensions when being formatted using [MUIA_Numeric_Format](MUI_Numeric/#MUIA_Numeric_Format). This might be
necessary if the standard check for some very few certain values does not
yield the largest text dimension and hence would cause graphical errors. The
drawback is that setting up an object with this attribute set to TRUE might
take considerably more time than usual due to the additional overhead.

Defaults to FALSE.

### SEE ALSO
[MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max), [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value), [MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min),
[MUIA_Numeric_Format](MUI_Numeric/#MUIA_Numeric_Format)

## MUIA_Numeric_Default
### NAME
[MUIA_Numeric_Default](MUI_Numeric/#MUIA_Numeric_Default) -- V11 [ISG], `LONG`, 0x804263e8

### FUNCTION
Adjust the default value for a numeric input/display gadget. When the object
receives a [MUIM_Numeric_SetDefault](MUI_Numeric/#MUIM_Numeric_SetDefault) method, it sets its value to the one given
here.

Each type of slider can have a default value to which the user can always return
immediately by some action depending on the implementation of the subclass. Knob
class e.g. resets to defaults after a double click in the knob area.

The default value can also be reached by pressing the toggle key (usually SPACE)
on an active numeric gadget.

Defaults to 0.

### SEE ALSO
[MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max), [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value), [MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min),
[MUIM_Numeric_SetDefault](MUI_Numeric/#MUIM_Numeric_SetDefault)

## MUIA_Numeric_Format
### NAME
[MUIA_Numeric_Format](MUI_Numeric/#MUIA_Numeric_Format) -- V11 [ISG], `STRPTR`, 0x804263e9

### FUNCTION
printf-style string to describe the format of the slider display.

Whenever a subclass of Numeric class thinks its time to render a new value, it
doesn't simply write it to a string but instead calls
[MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify). This method of Numeric class looks for the specified
[MUIA_Numeric_Format](MUI_Numeric/#MUIA_Numeric_Format) in its data structures and fills a string with the
current value. In detail, things work like his:

- Some slider object (e.g. a knob) receives a [MUIM_Draw](MUI_Area/#MUIM_Draw) method.
- The [MUIM_Draw](MUI_Area/#MUIM_Draw) implementation of the knob object reads the current value of
  Numeric class and calls [MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify) with this value.
- [MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify) of numeric class reads the current format and
  sprintf()s the given value to a buffer. The buffer is returned the caller.
- After all this stuff, the [MUIM_Draw](MUI_Area/#MUIM_Draw) implementation receives a nice string as
  result code and finally puts it somewhere into the window.

All this method stuff might sound a bit crazy, but in fact its quite powerful.
If you write a subclass of any of MUI's slider classes which simply replaces
[MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify) with your own code, you can create any string you like
for display in these sliders. You might e.g. want to display a nice formatted
time string (hh:mm:ss) in a slider knob which adjusts a number of seconds. Or
you need to adjust a baudrate from a hand of predefined values. Just overrided
[MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify) and you have the choice how the slider value translates
into a string.

If you don't override [MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify), the method reaches Numeric class w
hich simply does a sprintf() with the defined [MUIA_Numeric_Format](MUI_Numeric/#MUIA_Numeric_Format).

Note well: The maximum length of the result string for [MUIA_Numeric_Format](MUI_Numeric/#MUIA_Numeric_Format) is
limited to 32 characters. If you need more, you **MUST** override the method.

Defaults to "%ld".

### SEE ALSO
[MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max), [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value), [MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min),
[MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify), [MUIM_Numeric_StringifyValue](MUI_Numeric/#MUIM_Numeric_StringifyValue)

## MUIA_Numeric_Max
### NAME
[MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max) -- V11 [ISG], `LONG`, 0x8042d78a

### FUNCTION
Adjust the maximum value for a numeric input/display gadget. Numeric class
will automatically clip its value to make it fit between [MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min)
and MUI_Numeric_Max. Also, minimum and maximum values are used for several
internal calculations such as the maximum space required to display a
numeric value.

You may change [MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min) and [MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max) with SetAttrs(), but
current MUI versions will **NOT** update the objects and with the window's
width or height if your change causes the value display to change it's
minimum and/or maximum pixel sizes. The slider position itself will be
updated though.

MUI treats all values in numeric class as signed longwords, so that's the
limit for all tags.

Defaults to 100.

### NOTES
This attribute replaces the [MUIA_Slider_Max](MUI_Slider/#MUIA_Slider_Max) tag of previous MUI releases.
For compatibility reasons, both have the same hex value. Nevertheless,
always use [MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max) in new code.

Setting [MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max) directly after [MUIA_NoNotify](MUI_Notify/#MUIA_NoNotify)=TRUE will disable a
notification of [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value) in case the new maximum value is smaller
than the current value. The current value will be clipped accordingly to the
new maximum value nevertheless.

### SEE ALSO
[MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min), [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value), [MUIA_Numeric_Default](MUI_Numeric/#MUIA_Numeric_Default),
[MUIM_Numeric_GetPixelSize](MUI_Numeric/#MUIM_Numeric_GetPixelSize), [MUIM_Numeric_ValueToScale](MUI_Numeric/#MUIM_Numeric_ValueToScale),
[MUIM_Numeric_ScaleToValue](MUI_Numeric/#MUIM_Numeric_ScaleToValue)

## MUIA_Numeric_Min
### NAME
[MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min) -- V11 [ISG], `LONG`, 0x8042e404

### FUNCTION
Adjust the minimum value for a numeric input/display gadget. Numeric class
will automatically clip its value to make it fit between [MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min)
and MUI_Numeric_Max. Also, minimum and maximum values are used for several
internal calculations such as the maximum space required to display a
numeric value.

You may change [MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min) and [MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max) with SetAttrs(), but
current MUI versions will **NOT** update the objects and with the window's
width or height if your change causes the value display to change it's
minimum and/or maximum pixel sizes. The slider position itself will be
updated though.

MUI treats all values in numeric class as signed longwords, so that's the
limit for all tags.

Defaults to 0.

### NOTES
This attribute replaces the [MUIA_Slider_Min](MUI_Slider/#MUIA_Slider_Min) tag of previous MUI releases.
For compatibility reasons, both have the same hex value. Nevertheless,
always use [MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min) in new code.

Setting [MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min) directly after [MUIA_NoNotify](MUI_Notify/#MUIA_NoNotify)=TRUE will disable a
notification of [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value) in case the new minimum value is larger
than the current value. The current value will be clipped accordingly to the
new minimum value nevertheless.

### SEE ALSO
[MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max), [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value), [MUIA_Numeric_Default](MUI_Numeric/#MUIA_Numeric_Default),
[MUIM_Numeric_GetPixelSize](MUI_Numeric/#MUIM_Numeric_GetPixelSize), [MUIM_Numeric_ValueToScale](MUI_Numeric/#MUIM_Numeric_ValueToScale),
[MUIM_Numeric_ScaleToValue](MUI_Numeric/#MUIM_Numeric_ScaleToValue)

## MUIA_Numeric_Reverse
### NAME
[MUIA_Numeric_Reverse](MUI_Numeric/#MUIA_Numeric_Reverse) -- V11 [ISG], `BOOL`, 0x8042f2a0

### FUNCTION
Reverse the display of a numeric gadget.

When set to TRUE, the [MUIM_Numeric_ScaleToValue](MUI_Numeric/#MUIM_Numeric_ScaleToValue) and
[MUIM_Numeric_ValueToScale](MUI_Numeric/#MUIM_Numeric_ValueToScale) methods are effected in a way that makes your
gadget behave "reverse". Its minimum numeric value will be mapped to the
maximum scale value of the display and vice versa.

Defaults to FALSE.

### NOTES
This attribute replaces the [MUIA_Slider_Reverse](MUI_Slider/#MUIA_Slider_Reverse) tag of previous MUI
releases. For compatibility reasons, both have the same hex value.
Nevertheless, always use [MUIA_Numeric_Reverse](MUI_Numeric/#MUIA_Numeric_Reverse) in new code.

### SEE ALSO
[MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max), [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value), [MUIA_Numeric_Default](MUI_Numeric/#MUIA_Numeric_Default),
[MUIM_Numeric_ValueToScale](MUI_Numeric/#MUIM_Numeric_ValueToScale), [MUIM_Numeric_ScaleToValue](MUI_Numeric/#MUIM_Numeric_ScaleToValue)

## MUIA_Numeric_RevLeftRight
### NAME
[MUIA_Numeric_RevLeftRight](MUI_Numeric/#MUIA_Numeric_RevLeftRight) -- V11 [ISG], `BOOL`, 0x804294a7

### FUNCTION
Reverse the function of left/right keys.

Under some circumstances it might be desirable to reverse the keyboard
control for a slider gadget. This tag might help.

Defaults to FALSE.

### SEE ALSO
[MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max), [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value), [MUIA_Numeric_Default](MUI_Numeric/#MUIA_Numeric_Default),
[MUIA_Numeric_Reverse](MUI_Numeric/#MUIA_Numeric_Reverse), [MUIA_Numeric_RevUpDown](MUI_Numeric/#MUIA_Numeric_RevUpDown)

## MUIA_Numeric_RevUpDown
### NAME
[MUIA_Numeric_RevUpDown](MUI_Numeric/#MUIA_Numeric_RevUpDown) -- V11 [ISG], `BOOL`, 0x804252dd

### FUNCTION
Reverse the function of up/down keys.

Under some circumstances it might be desirable to reverse the keyboard
control for a slider gadget. This tag might help.

Defaults to FALSE.

### SEE ALSO
[MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max), [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value), [MUIA_Numeric_Default](MUI_Numeric/#MUIA_Numeric_Default),
[MUIA_Numeric_Reverse](MUI_Numeric/#MUIA_Numeric_Reverse), [MUIA_Numeric_RevUpDown](MUI_Numeric/#MUIA_Numeric_RevUpDown)

## MUIA_Numeric_Value
### NAME
[MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value) -- V11 [ISG], `LONG`, 0x8042ae3a

### FUNCTION
Adjust the current value for a numeric input/display gadget. Numeric class
will automatically clip this value to make it fit between [MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min)
and MUI_Numeric_Max.

Whenever a new value is set, the object receices a new [MUIM_Draw](MUI_Area/#MUIM_Draw) method to
get a chance to update its display.

Defaults to 0.

### NOTES
This attribute replaces the [MUIA_Slider_Level](MUI_Slider/#MUIA_Slider_Level) tag of previous MUI releases.
For compatibility reasons, both have the same hex value. Nevertheless,
always use [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value) in new code.

### SEE ALSO
[MUIA_Numeric_Min](MUI_Numeric/#MUIA_Numeric_Min), [MUIA_Numeric_Max](MUI_Numeric/#MUIA_Numeric_Max), [MUIA_Numeric_Default](MUI_Numeric/#MUIA_Numeric_Default),
[MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify)

## MUIM_Numeric_Decrease
### NAME
[MUIM_Numeric_Decrease](MUI_Numeric/#MUIM_Numeric_Decrease) -- V11, 0x804243a7

### SYNOPSIS
`DoMethod(obj, MUIM_Numeric_Decrease, LONG amount);`

### FUNCTION
Decrease the value of a numeric class object.

### INPUTS
**`LONG amount`**
     amount to decrease the number by

### SEE ALSO
[MUIM_Numeric_Increase](MUI_Numeric/#MUIM_Numeric_Increase), [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value)

## MUIM_Numeric_Increase
### NAME
[MUIM_Numeric_Increase](MUI_Numeric/#MUIM_Numeric_Increase) -- V11, 0x80426ecd

### SYNOPSIS
`DoMethod(obj, MUIM_Numeric_Increase, LONG amount);`

### FUNCTION
Increase the value of a numeric class object.

### INPUTS
**`LONG amount`**
     amount to increase the number by

### SEE ALSO
[MUIM_Numeric_Decrease](MUI_Numeric/#MUIM_Numeric_Decrease), [MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value)

## MUIM_Numeric_ScaleToValue
### NAME
[MUIM_Numeric_ScaleToValue](MUI_Numeric/#MUIM_Numeric_ScaleToValue) -- V11, 0x8042032c

### SYNOPSIS
`DoMethod(obj, MUIM_Numeric_ScaleToValue, LONG scalemin, LONG scalemax, LONG scale);`

### FUNCTION
This method takes the given scale value and transform it to something
between the numeric object's min and max values.

### INPUTS
**`LONG scalemin`**
     minimum scale value

**`LONG scalemax`**
     maximum scale value

**`LONG scale`**
     the value to be scaled

### RESULT
The transformed value.

## MUIM_Numeric_SetDefault
### NAME
[MUIM_Numeric_SetDefault](MUI_Numeric/#MUIM_Numeric_SetDefault) -- V11, 0x8042ab0a

### SYNOPSIS
`DoMethod(obj, MUIM_Numeric_SetDefault);`

### FUNCTION
This method does nothing but reset the value to its default. Defaults can be
adjusted through [MUIA_Numeric_Default](MUI_Numeric/#MUIA_Numeric_Default).

Only implementors of custom slider classes will need this method. Sending it
from applications doesn't make any sense.

### SEE ALSO
[MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value), [MUIA_Numeric_Default](MUI_Numeric/#MUIA_Numeric_Default)

## MUIM_Numeric_Stringify
### NAME
[MUIM_Numeric_Stringify](MUI_Numeric/#MUIM_Numeric_Stringify) -- V11, 0x80424891

### SYNOPSIS
`DoMethod(obj, MUIM_Numeric_Stringify, LONG value);`

### FUNCTION
Call this method in your subclass whenever you want to translate a value
into a string. A pointer to a string buffer is returned.

Only implementors of custom slider classes will need this method. Sending it
from applications doesn't make any sense.

### INPUTS
**`LONG value`**
     the value to be converted to a string

### EXAMPLE
... somewhere in your [MUIM_Draw](MUI_Area/#MUIM_Draw) method ...

```c++
get(obj, MUIA_Numeric_Value, &val);
buf = DoMethod(obj, MUIM_Numeric_Stringify, val);
Text(rp, buf, strlen(buf));
```

### SEE ALSO
[MUIA_Numeric_Value](MUI_Numeric/#MUIA_Numeric_Value), [MUIA_Numeric_Format](MUI_Numeric/#MUIA_Numeric_Format)

## MUIM_Numeric_ValueToScale
### NAME
[MUIM_Numeric_ValueToScale](MUI_Numeric/#MUIM_Numeric_ValueToScale) -- V11, 0x80423e4f

### SYNOPSIS
`DoMethod(obj, MUIM_Numeric_ValueToScale, LONG scalemin, LONG scalemax);`

### FUNCTION
This method takes the current value of the numeric object and transforms it
to another scale determined by the parameters.

### INPUTS
**`LONG scalemin`**
     minimum scale value

**`LONG scalemax`**
     maximum scale value

### RESULT
The transformed value.

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
