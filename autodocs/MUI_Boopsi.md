# Boopsi.mui
## Super class
[Gadget.mui](MUI_Gadget.md)
## Background
MUI's Boopsi class provides an interface to standard, system style BOOPSI
gadgets. Since BOOPSI's gadgetclass misses some important features needed
for an automatic layout system like MUI, there are several problems with
such an interface. MUI tries to solve these problems with some additional
attributes.

Coming with release 3.x of the Amiga operating system are some very nice
BOOPSI gadgets such as "colorwheel.gadget" or "gradientslider.gadget". With
MUI's Boopsi class, you can use these gadgets just as if they were MUI
objects.

You can talk to a MUIized BOOPSI object as if it was the BOOPSI object
itself. MUI will pass through all attributes and try to be completely
transparent. Additionally, if a BOOPSI object generates notification events
via IDCMP_UPDATE, MUI turns them into MUI notification events. Thus, you can
e.g. react on the change of WHEEL_Saturation in a MUI colorwheel BOOPSI
gadget as on any other MUI attribute.

An example program "BoopsiDoor.c" is provided to show how this magic works.

### NOTES
OS 3.0/3.1 colorwheel.gadget can accidently render itself one pixel
too big, overwriting other parts of the window. As a workaround, MUI
will subtract one from the width/height before passing it on to a
colorwheel BOOPSI object.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Boopsi_Class](MUI_Boopsi.md/#MUIA_Boopsi_Class)|V4|ISG|`struct IClass *`
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)|V4|ISG|`STRPTR`
[MUIA_Boopsi_MaxHeight](MUI_Boopsi.md/#MUIA_Boopsi_MaxHeight)|V4|ISG|`ULONG`
[MUIA_Boopsi_MaxWidth](MUI_Boopsi.md/#MUIA_Boopsi_MaxWidth)|V4|ISG|`ULONG`
[MUIA_Boopsi_MinHeight](MUI_Boopsi.md/#MUIA_Boopsi_MinHeight)|V4|ISG|`ULONG`
[MUIA_Boopsi_MinWidth](MUI_Boopsi.md/#MUIA_Boopsi_MinWidth)|V4|ISG|`ULONG`
[MUIA_Boopsi_Object](MUI_Boopsi.md/#MUIA_Boopsi_Object)|V4|..G|`Object *`
[MUIA_Boopsi_Remember](MUI_Boopsi.md/#MUIA_Boopsi_Remember)|V4|I..|`ULONG`
[MUIA_Boopsi_Smart](MUI_Boopsi.md/#MUIA_Boopsi_Smart)|V9|I..|`BOOL`
[MUIA_Boopsi_TagDrawInfo](MUI_Boopsi.md/#MUIA_Boopsi_TagDrawInfo)|V4|ISG|`ULONG`
[MUIA_Boopsi_TagScreen](MUI_Boopsi.md/#MUIA_Boopsi_TagScreen)|V4|ISG|`ULONG`
[MUIA_Boopsi_TagWindow](MUI_Boopsi.md/#MUIA_Boopsi_TagWindow)|V4|ISG|`ULONG`

## MUIA_Boopsi_Class
### NAME
[MUIA_Boopsi_Class](MUI_Boopsi.md/#MUIA_Boopsi_Class) -- V4 [ISG], `struct IClass *`, 0x80426999

### FUNCTION
Pointer to the (private) class you want to create a BOOPSI object from.
Only useful if you previously generated your own BOOPSI class with
MakeClass().

Of course you may not free the class until you're done with your object.

### SEE ALSO
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

## MUIA_Boopsi_ClassID
### NAME
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID) -- V4 [ISG], `STRPTR`, 0x8042bfa3

### FUNCTION
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID) specifies the name for the public BOOPSI class you want
to create an object of. It will only be used when [MUIA_Boopsi_Class](MUI_Boopsi.md/#MUIA_Boopsi_Class) is NULL.

The public class must be in memory before you can create an instance of it,
you will have to open the required class library by hand.

Note the string given to [MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID) must remain valid until you're
done with the object.

### EXAMPLE
```c++
/* Complete example code can be found in BoopsiDoor.c */

cwbase = OpenLibrary("gadgets/colorwheel.gadget",0);

Wheel = BoopsiObject,  /* MUI and Boopsi tags mixed */
  NeXTFrame,
  MUIA_Boopsi_ClassID  , "colorwheel.gadget",
  MUIA_Boopsi_MinWidth , 30, /* BOOPSI objects don't know */
  MUIA_Boopsi_MinHeight, 30, /* their sizes, so we help   */
  MUIA_Boopsi_Remember , WHEEL_Saturation, /* keep important values */
  MUIA_Boopsi_Remember , WHEEL_Hue,        /* during window resize  */
  MUIA_Boopsi_TagScreen, WHEEL_Screen, /* this magic fills in */
  WHEEL_Screen         , NULL,         /* the screen pointer  */
  GA_Left     , 0,
  GA_Top      , 0, /* MUI will automatically     */
  GA_Width    , 0, /* fill in the correct values */
  GA_Height   , 0,
  ICA_TARGET  , ICTARGET_IDCMP, /* needed for notification */
  End;
...

MUI_DisposeObject(wheel);
CloseLibrary(cwbase);
```

### SEE ALSO
[MUIA_Boopsi_Class](MUI_Boopsi.md/#MUIA_Boopsi_Class)

## MUIA_Boopsi_MaxHeight
### NAME
[MUIA_Boopsi_MaxHeight](MUI_Boopsi.md/#MUIA_Boopsi_MaxHeight) -- V4 [ISG], `ULONG`, 0x8042757f

### FUNCTION
For MUI's automatic layout system, it's required that objects know their
minimum and maximums sizes. Since BOOPSI gadgets don't support this feature,
you will have to help MUI and adjust these values by hand.

Defaults:
  [MUIA_Boopsi_MinWidth](MUI_Boopsi.md/#MUIA_Boopsi_MinWidth)  - 1 pixel
  [MUIA_Boopsi_MinHeight](MUI_Boopsi.md/#MUIA_Boopsi_MinHeight) - 1 pixel
  [MUIA_Boopsi_MaxWidth](MUI_Boopsi.md/#MUIA_Boopsi_MaxWidth)  - unlimited
  [MUIA_Boopsi_MaxHeight](MUI_Boopsi.md/#MUIA_Boopsi_MaxHeight) - unlimited

### EXAMPLE
see [MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

### SEE ALSO
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

## MUIA_Boopsi_MaxWidth
### NAME
[MUIA_Boopsi_MaxWidth](MUI_Boopsi.md/#MUIA_Boopsi_MaxWidth) -- V4 [ISG], `ULONG`, 0x8042bcb1

### FUNCTION
For MUI's automatic layout system, it's required that objects know their
minimum and maximums sizes. Since BOOPSI gadgets don't support this feature,
you will have to help MUI and adjust these values by hand.

Defaults:
  [MUIA_Boopsi_MinWidth](MUI_Boopsi.md/#MUIA_Boopsi_MinWidth)  - 1 pixel
  [MUIA_Boopsi_MinHeight](MUI_Boopsi.md/#MUIA_Boopsi_MinHeight) - 1 pixel
  [MUIA_Boopsi_MaxWidth](MUI_Boopsi.md/#MUIA_Boopsi_MaxWidth)  - unlimited
  [MUIA_Boopsi_MaxHeight](MUI_Boopsi.md/#MUIA_Boopsi_MaxHeight) - unlimited

### EXAMPLE
see [MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

### SEE ALSO
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

## MUIA_Boopsi_MinHeight
### NAME
[MUIA_Boopsi_MinHeight](MUI_Boopsi.md/#MUIA_Boopsi_MinHeight) -- V4 [ISG], `ULONG`, 0x80422c93

### FUNCTION
For MUI's automatic layout system, it's required that objects know their
minimum and maximums sizes. Since BOOPSI gadgets don't support this feature,
you will have to help MUI and adjust these values by hand.

Defaults:
  [MUIA_Boopsi_MinWidth](MUI_Boopsi.md/#MUIA_Boopsi_MinWidth)  - 1 pixel
  [MUIA_Boopsi_MinHeight](MUI_Boopsi.md/#MUIA_Boopsi_MinHeight) - 1 pixel
  [MUIA_Boopsi_MaxWidth](MUI_Boopsi.md/#MUIA_Boopsi_MaxWidth)  - unlimited
  [MUIA_Boopsi_MaxHeight](MUI_Boopsi.md/#MUIA_Boopsi_MaxHeight) - unlimited

### EXAMPLE
see [MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

### SEE ALSO
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

## MUIA_Boopsi_MinWidth
### NAME
[MUIA_Boopsi_MinWidth](MUI_Boopsi.md/#MUIA_Boopsi_MinWidth) -- V4 [ISG], `ULONG`, 0x80428fb2

### FUNCTION
For MUI's automatic layout system, it's required that objects know their
minimum and maximums sizes. Since BOOPSI gadgets don't support this feature,
you will have to help MUI and adjust these values by hand.

Defaults:
  [MUIA_Boopsi_MinWidth](MUI_Boopsi.md/#MUIA_Boopsi_MinWidth)  - 1 pixel
  [MUIA_Boopsi_MinHeight](MUI_Boopsi.md/#MUIA_Boopsi_MinHeight) - 1 pixel
  [MUIA_Boopsi_MaxWidth](MUI_Boopsi.md/#MUIA_Boopsi_MaxWidth)  - unlimited
  [MUIA_Boopsi_MaxHeight](MUI_Boopsi.md/#MUIA_Boopsi_MaxHeight) - unlimited

### EXAMPLE
see [MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

### SEE ALSO
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

## MUIA_Boopsi_Object
### NAME
[MUIA_Boopsi_Object](MUI_Boopsi.md/#MUIA_Boopsi_Object) -- V4 [..G], `Object *`, 0x80420178

### FUNCTION
No input, just an output since this attribute is only getable. What MUI
returns when generating a BoopsiObject is a standard MUI object, not a
pointer to the BOOPSI gadget itself. In case you really need this BOOPSI
gadget pointer, you can obtain it by getting [MUIA_Boopsi_Object](MUI_Boopsi.md/#MUIA_Boopsi_Object) from the MUI
object.

Since MUI passes along every unknown attribute to the BOOPSI gadget, there
should be no need for this tag anyway.

Note that the BOOPSI object pointer is only valid when the window is open!

### SEE ALSO
[MUIA_Boopsi_Class](MUI_Boopsi.md/#MUIA_Boopsi_Class), [MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

## MUIA_Boopsi_Remember
### NAME
[MUIA_Boopsi_Remember](MUI_Boopsi.md/#MUIA_Boopsi_Remember) -- V4 [I..], `ULONG`, 0x8042f4bd

### FUNCTION
Most BOOPSI objects are kind of silly, they don't support automatic resizing
or jumping from screen to screen. Therefor, MUI sometimes needs to dispose
and regenerate a BOOPSI object. This will result in loosing the current
state of the object, e.g. saturation and hue values in a colorwheel.

To solve this problem, you can tell MUI what attributes must be remembered
during dispose/regeneration. For a colorwheel, this would e.g. be
WHEEL_Saturation and WHEEL_Hue.

Before disposing the BOOPSI object, the remember tags are read and stored in
a private buffer. After regeneration, the contents of this buffer are passed
back to the BOOPSI object again.

Note that you can define up to five [MUIA_Boopsi_Remember](MUI_Boopsi.md/#MUIA_Boopsi_Remember) tags.

### BUGS
The remember procedure will not work when the attributes you want to
remember are just pointers to data stored somewhere in the BOOPSI object.

### EXAMPLE
see [MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

### SEE ALSO
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID)

## MUIA_Boopsi_Smart
### NAME
[MUIA_Boopsi_Smart](MUI_Boopsi.md/#MUIA_Boopsi_Smart) -- V9 [I..], `BOOL`, 0x8042b8d7

### FUNCTION
Specify TRUE for smart BOOPSI gadgets that allow resizing, e.g. the
textfield.class. In this case, MUI will not dispose and recreate the object.

## MUIA_Boopsi_TagDrawInfo
### NAME
[MUIA_Boopsi_TagDrawInfo](MUI_Boopsi.md/#MUIA_Boopsi_TagDrawInfo) -- V4 [ISG], `ULONG`, 0x8042bae7

### FUNCTION
Unfortunately, most BOOPSI gadgets need information on the display
environment they will reside in at object creation time. Due to MUI's
concept, this information is not available that early.

To solve this problem, MUI doesn't generate the BOOPSI object instantly,
creation is delayed until the window containing the gadget is opened.

At this time, MUI fills some values about display environment into the
BOOPSI objects creation tag list. You have to tell MUI, what tags are
actually needed.

With [MUIA_Boopsi_TagDrawInfo](MUI_Boopsi.md/#MUIA_Boopsi_TagDrawInfo) you can tell MUI where to fill in a needed
DrawInfo structure.

### EXAMPLE
If your BOOPSI gadget needs a pointer to a DrawInfo structure supplied with
the MYBOOPSI_DrawInfo tag, you would have to specify

```c++
BoopsiObject,
  RecessedFrame,
  ...
  MUIA_Boopsi_TagDrawInfo, MYBOOPSI_DrawInfo,
  ...
  MYBOOPSI_DrawInfo, 0, /* will be filled later by MUI */
  ...
  GA_Left  , 0, /* needs to be there, will */
  GA_Top   , 0, /* be filled later by MUI  */
  GA_Width , 0,
  GA_Height, 0,
  End;
```

### SEE ALSO
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID), [MUIA_Boopsi_TagScreen](MUI_Boopsi.md/#MUIA_Boopsi_TagScreen), [MUIA_Boopsi_TagWindow](MUI_Boopsi.md/#MUIA_Boopsi_TagWindow)

## MUIA_Boopsi_TagScreen
### NAME
[MUIA_Boopsi_TagScreen](MUI_Boopsi.md/#MUIA_Boopsi_TagScreen) -- V4 [ISG], `ULONG`, 0x8042bc71

### FUNCTION
Unfortunately, most BOOPSI gadgets need information on the display
environment they will reside in at object creation time. Due to MUI's
concept, this information is not available that early.

To solve this problem, MUI doesn't generate the BOOPSI object instantly,
creation is delayed until the window containing the gadget is opened.

At this time, MUI fills some values about display environment into the
BOOPSI objects creation tag list. You have to tell MUI, what tags are
actually needed.

With [MUIA_Boopsi_TagScreen](MUI_Boopsi.md/#MUIA_Boopsi_TagScreen) you can tell MUI where to fill in a needed
Screen structure.

### EXAMPLE
If your BOOPSI gadget needs a pointer to a Screen structure supplied with
the MYBOOPSI_Screen tag, you would have to specify

```c++
BoopsiObject,
  RecessedFrame,
  ...
  MUIA_Boopsi_TagScreen, MYBOOPSI_Screen,
  ...
  MYBOOPSI_Screen, 0, /* will be filled later by MUI */
  ...
  GA_Left  , 0, /* needs to be there, will */
  GA_Top   , 0, /* be filled later by MUI  */
  GA_Width , 0,
  GA_Height, 0,
  End;
```

### SEE ALSO
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID), [MUIA_Boopsi_TagDrawInfo](MUI_Boopsi.md/#MUIA_Boopsi_TagDrawInfo), [MUIA_Boopsi_TagWindow](MUI_Boopsi.md/#MUIA_Boopsi_TagWindow)

## MUIA_Boopsi_TagWindow
### NAME
[MUIA_Boopsi_TagWindow](MUI_Boopsi.md/#MUIA_Boopsi_TagWindow) -- V4 [ISG], `ULONG`, 0x8042e11d

### FUNCTION
Unfortunately, most BOOPSI gadgets need information on the display
environment they will reside in at object creation time. Due to MUI's
concept, this information is not available that early.

To solve this problem, MUI doesn't generate the BOOPSI object instantly,
creation is delayed until the window containing the gadget is opened.

At this time, MUI fills some values about display environment into the
BOOPSI objects creation tag list. You have to tell MUI, what tags are
actually needed.

With [MUIA_Boopsi_TagWindow](MUI_Boopsi.md/#MUIA_Boopsi_TagWindow) you can tell MUI where to fill in a needed
Window structure.

### EXAMPLE
If your BOOPSI gadget needs a pointer to a Window structure supplied with
the MYBOOPSI_Window tag, you would have to specify

```c++
BoopsiObject,
  RecessedFrame,
  ...
  MUIA_Boopsi_TagWindow, MYBOOPSI_Window,
  ...
  MYBOOPSI_Window, 0, /* will be filled later by MUI */
  ...
  GA_Left  , 0, /* needs to be there, will */
  GA_Top   , 0, /* be filled later by MUI  */
  GA_Width , 0,
  GA_Height, 0,
  End;
```

### SEE ALSO
[MUIA_Boopsi_ClassID](MUI_Boopsi.md/#MUIA_Boopsi_ClassID), [MUIA_Boopsi_TagDrawInfo](MUI_Boopsi.md/#MUIA_Boopsi_TagDrawInfo), [MUIA_Boopsi_TagWindow](MUI_Boopsi.md/#MUIA_Boopsi_TagWindow)

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
