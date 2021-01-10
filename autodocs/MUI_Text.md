# Text.mui
## Super class
[Area.mui](MUI_Area)
## Inherited by
* [Fontdisplay.mui](MUI_Fontdisplay)
## Background
Text class allows generating objects that contain some kind of text. You can
control the outfit of your text with some special control characters,
including italics, bold, underline and color codes. Format codes align text
either left, centered or right, linefeeds allow multiline text fields.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Text_Contents](MUI_Text.md/#MUIA_Text_Contents)|V4|ISG|`STRPTR`
[MUIA_Text_ControlChar](MUI_Text.md/#MUIA_Text_ControlChar)|V20|ISG|`char`
[MUIA_Text_Copy](MUI_Text.md/#MUIA_Text_Copy)|V20|ISG|`BOOL`
[MUIA_Text_Data](MUI_Text.md/#MUIA_Text_Data)|V21|ISG|`Object *`
[MUIA_Text_HiChar](MUI_Text.md/#MUIA_Text_HiChar)|V4|I..|`char`
[MUIA_Text_Marking](MUI_Text.md/#MUIA_Text_Marking)|V20|I.G|`BOOL`
[MUIA_Text_PreParse](MUI_Text.md/#MUIA_Text_PreParse)|V4|ISG|`STRPTR`
[MUIA_Text_SetMax](MUI_Text.md/#MUIA_Text_SetMax)|V4|I..|`BOOL`
[MUIA_Text_SetMin](MUI_Text.md/#MUIA_Text_SetMin)|V4|I..|`BOOL`
[MUIA_Text_SetVMax](MUI_Text.md/#MUIA_Text_SetVMax)|V11|IS.|`BOOL`
[MUIA_Text_Shorten](MUI_Text.md/#MUIA_Text_Shorten)|V20|ISG|`LONG`
[MUIA_Text_Shortened](MUI_Text.md/#MUIA_Text_Shortened)|V20|..G|`BOOL`

## MUIA_Text_Contents
### NAME
[MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents) -- V4 [ISG], `STRPTR`, 0x8042f8dc

### FUNCTION
String to be displayed in a text object.

If the string is larger than available display space, it will be clipped.
Setting [MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents) to NULL results in an empty text object.

The string is copied into a private buffer (unless [MUIA_Text_Copy](MUI_Text/#MUIA_Text_Copy) is set to
FALSE), you can destroy the original string after using this tag.

Whenever MUI prints strings, they may contain some special character
sequences defining format, color and style of the text.

**`'\n'`**
     start a new line. With this character you can e.g. create multiline buttons.

**`'\t'`**
     insert a TAB character. The TAB will be as wide as four space characters.

**`ESC -`**
     disable text engine, following characters will be rendered without further
     parsing.

**`ESC u`**
     enable the underline soft style.

**`ESC U`**
     disable the underline soft style.

**`ESC b`**
     enable the bold soft style.

**`ESC i`**
     enable the italic soft style.

**`ESC t`**
     enable the outline soft style.

**`ESC T`**
     disable the outline soft style.

**`ESC s`**
     enable the shadow soft style.

**`ESC S`**
     disable the shadow soft style.

**`ESC g`**
     enable the ghost soft style.

**`ESC G`**
     disable the ghost soft style.

**`ESC n`**
     set the soft style back to normal.

**`ESC B`**
     enable JAM2 drawing mode. This must be set to make use of the set
     background color.

**`ESC F`**
     disable JAM2 drawing mode. The following text will be rendered
     using the text color only, no matter which background color is set.
     This is active by default.

**`ESC V`**
     enable INVERSVID drawing mode.

**`ESC v`**
     disable INVERSVID drawing mode.

**`ESC h`**
     disable the rendering of embedded images and objects.

**`ESC H`**
     enable the rendering of embedded images and objects. This is active
     by default.

**`ESC M`**
     use MARKTEXT pen as front pen.

**`ESC m`**
     use MARK pen as front pen.

**`ESC <n>`**
     use pen number n (2..9) as front pen. n must be a valid DrawInfo
     pen as specified in "intuition/screens.h".

**`ESC c`**
     center current (and following) line(s). This sequence is only valid
     at the beginning of a string or directly following a newline
     character.

**`ESC r`**
     right justify current (and following) line(s). This sequence is
     only valid at the beginning of a string or directly following a
     newline character.

**`ESC l`**
     left justify current (and following) line(s). This sequence is only
     valid at the beginning of a string or directly following a newline
     character.

**`ESC I[s]`**
     draw MUI image with specification <s>. See Autodocs of image class
     for image spec definition. Appending ",STATE=1" to the image spec
     will draw the image in selected state if that is possible. This
     requires the image to be have multiple images. This is true for
     name extensions like ".mb0/1", ".mf0/1" or ".mim".

**`ESC p[p]`**
     background pen number

**`ESC P[p]`**
     text pen number

**`ESC p[RRGGBB]`**
     direct RGB color value specifying background color on truecolor displays.

**`ESC P[RRGGBB]`**
     ESC P[AARRGGBB]::
     ESC P[AA------]::
     direct (A)RGB value specifying text color on truecolor displays.
     When AA------ is used, currently set color is not altered, only its alpha
     value (transparency).

**`ESC A[x]`**
     draw raw ARGB data taken from struct MUI_AlphaData pointed to by
     <x>, i.e. "\033A[deadbeef]". The address may be prefixed with a '$'.

**`ESC O[x]`**
     ESC O[x,width]::
     draw a MUI object pointed to by <x>, i.e. "\033O[deadbeef]".
     The address may be prefixed with a '$'. The additional width value
     is optional. If it is omitted the object will be queried for its
     minimum width.

Note: These rules apply to all MUI strings, not only to a text object's
contents. You can e.g. format the columns of a listview or include
images in a cycle gadget's entries.

### EXAMPLE
```c++
MUIA_Text_Contents, "\33c\33bMUI\33n\nis magic"
```

would look like     |    MUI   |  <-- bold
                    | is magic |  <-- normal

### SEE ALSO
[MUIA_Text_Data](MUI_Text/#MUIA_Text_Data), [MUIA_Text_SetMin](MUI_Text/#MUIA_Text_SetMin), [MUIA_Text_SetMax](MUI_Text/#MUIA_Text_SetMax), [MUIA_Text_PreParse](MUI_Text/#MUIA_Text_PreParse)

## MUIA_Text_ControlChar
### NAME
[MUIA_Text_ControlChar](MUI_Text/#MUIA_Text_ControlChar) -- V20 [ISG], `char`, 0x8042e6d0

### FUNCTION
If the character given here exists in the displayed string (no matter if
upper or lower case), it will be underlined. This makes it easy to create
macros such as KeyButton() that specify the control char and the underline
char at the same time.

In contrast to [MUIA_Text_HiChar](MUI_Text/#MUIA_Text_HiChar) the underlining does NOT happen by inserting
text styles as this might break other active styles.

### SEE ALSO
[MUIA_Text_HiChar](MUI_Text/#MUIA_Text_HiChar), [MUIA_ControlChar](MUI_Area/#MUIA_ControlChar)

## MUIA_Text_Copy
### NAME
[MUIA_Text_Copy](MUI_Text/#MUIA_Text_Copy) -- V20 [ISG], `BOOL`, 0x80427727

### FUNCTION
When set to FALSE, the contents will not be copied to a private buffer.

Defaults to TRUE, unless [MUIA_Text_HiChar](MUI_Text/#MUIA_Text_HiChar) is also specified.

### SEE ALSO
[MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents), [MUIA_Text_HiChar](MUI_Text/#MUIA_Text_HiChar)

## MUIA_Text_Data
### NAME
[MUIA_Text_Data](MUI_Text/#MUIA_Text_Data) -- V21 [ISG], `Object *`, 0x80424838

### FUNCTION
This attribute specifies the object's text wrapped in a Textdata object
instead of directly as a string. This allows to set arbitrarily encoded text
that will be converted to the local charset on the fly. The conversion will
be done by invoking the Textdata object's [MUIM_Textdata_Convert](MUI_Textdata/#MUIM_Textdata_Convert) method. If
this attribute is omitted or passed a NULL pointer the normal text specified
via [MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents) will be used.

Defaults to NULL.

### NOTES
The Text object automatically takes ownership of the supplied Textdata
object and will dispose it itself whenever this is required. Do NOT dispose
it yourself. Replacing an already existing Textdata object with a new one
will return the ownership to you and it is your responsibility to dispose
the old object to avoid memory leaks.

### EXAMPLE
```c++
// include the string "öäüÖÄÜß" as UTF8 encoded data
Object *utf8Text = TextObject,
  MUIA_Text_Data, UTextdata("\xc3\xb6\xc3\xa4\xc3\xbc\xc3"
                            "\x96\xc3\x84\xc3\x9c\xc3\x9f"),
End;
```

### SEE ALSO
[MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents), [MUIM_Textdata_Convert](MUI_Textdata/#MUIM_Textdata_Convert)

## MUIA_Text_HiChar
### NAME
[MUIA_Text_HiChar](MUI_Text/#MUIA_Text_HiChar) -- V4 [I..], `char`, 0x804218ff

### FUNCTION
If the character given here exists in the displayed string (no matter if
upper or lower case), it will be underlined. This makes it easy to create
macros such as KeyButton() that specify the control char and the underline
char at the same time.

### SEE ALSO
[MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents), [MUIA_ControlChar](MUI_Area/#MUIA_ControlChar)

## MUIA_Text_Marking
### NAME
[MUIA_Text_Marking](MUI_Text/#MUIA_Text_Marking) -- V20 [I.G], `BOOL`, 0x8042f780

### FUNCTION
This attribute controls whether it is possible to mark the object's text
contents using the mouse and copy them to the clipboard.

Defaults to FALSE.

### SEE ALSO
[MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents)

## MUIA_Text_PreParse
### NAME
[MUIA_Text_PreParse](MUI_Text/#MUIA_Text_PreParse) -- V4 [ISG], `STRPTR`, 0x8042566d

### FUNCTION
String containing format definitions to be parsed before the text from
[MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents) is printed.

Using this tag, you can easily define different formats, colors and styles
without modifying the original string.

### EXAMPLE
```c++
MUIA_Text_PreParse, "\33c\33i",   // centered and italics
MUIA_Text_Contents, "foobar",
```

### SEE ALSO
[MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents)

## MUIA_Text_SetMax
### NAME
[MUIA_Text_SetMax](MUI_Text/#MUIA_Text_SetMax) -- V4 [I..], `BOOL`, 0x80424d0a

### FUNCTION
Boolean value to indicate wether the objects maximal width shall be
calculated to fit the string given with [MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents).

When set to FALSE, maximum width is not limited.

For a text object that needs to be updated (e.g. some information about your
program's status) you would probably set [MUIA_Text_SetMax](MUI_Text/#MUIA_Text_SetMax) to FALSE to allow
resizing of this object.

For a label for one of your gadgets, you might want to give this tag a value
of TRUE to prevent MUI from inserting additional layout space.

Defaults to FALSE.

### EXAMPLE
```c++
TX_Status = TextObject,
  RecessedFrame,
  MUIA_Background, MUII_BACKGROUND,
  MUIA_Text_PreParse, "\33c",
  MUIA_Text_Contents, "running...",
  End;
...
set(TX_Status, MUIA_Text_Contents, "reading...");
...
set(TX_Status, MUIA_Text_Contents, "writing...");
```

### SEE ALSO
[MUIA_Text_SetMin](MUI_Text/#MUIA_Text_SetMin), [MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents)

## MUIA_Text_SetMin
### NAME
[MUIA_Text_SetMin](MUI_Text/#MUIA_Text_SetMin) -- V4 [I..], `BOOL`, 0x80424e10

### FUNCTION
Boolean value to indicate wether the objects minimal width shall be
calculated to fit the string given with [MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents).

When set to FALSE, minimum width will be set to 0 and the displayed string
may be clipped.

Defaults to TRUE.

### SEE ALSO
[MUIA_Text_SetMax](MUI_Text/#MUIA_Text_SetMax), [MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents)

## MUIA_Text_SetVMax
### NAME
[MUIA_Text_SetVMax](MUI_Text/#MUIA_Text_SetVMax) -- V11 [IS.], `BOOL`, 0x80420d8b

### FUNCTION
Settings this to FALSE makes a TextObjects y-size unlimited.

Defaults to TRUE, which means the objects height is fixed.

## MUIA_Text_Shorten
### NAME
[MUIA_Text_Shorten](MUI_Text/#MUIA_Text_Shorten) -- V20 [ISG], `LONG`, 0x80428bbd

### SPECIAL INPUTS
  * MUIV_Text_Shorten_Nothing
  * MUIV_Text_Shorten_Cutoff
  * MUIV_Text_Shorten_Hide
  * MUIV_Text_Shorten_ElideLeft
  * MUIV_Text_Shorten_ElideCenter
  * MUIV_Text_Shorten_ElideRight

### FUNCTION
This attribute controls whether MUI is allowed to shorten the text to be
displayed and how this shortening process will be done.
MUIV_Text_Shorten_Hide will hide all text completely if there is not enough
space.
MUIV_Text_Shorten_ElideLeft/Center/Right will shorten the text by replacing
as many characters as necessary by inserting an ellipsis ("...") at the
specified position.
[MUIA_Text_Shortened](MUI_Text/#MUIA_Text_Shortened) can be used to check whether the text was actually
shortened or not.

Defaults to MUIV_Text_Shorten_Nothing.

### EXAMPLE
```c++
TX_Status = TextObject,
  RecessedFrame,
  MUIA_Background, MUII_BACKGROUND,
  MUIA_Text_PreParse, "\33c",
  MUIA_Text_Contents, "running...",
  MUIA_Text_Shorten, MUIV_Text_Shorten_Hide,
  End;
```

### SEE ALSO
[MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents), [MUIA_Text_Shortened](MUI_Text/#MUIA_Text_Shortened)

## MUIA_Text_Shortened
### NAME
[MUIA_Text_Shortened](MUI_Text/#MUIA_Text_Shortened) -- V20 [..G], `BOOL`, 0x80425a86

### FUNCTION
This attribute can be used to check whether the text object's contents were
shortened to be able to keep up the current GUI layout.

### EXAMPLE
```c++
ULONG shortened;
get(obj, MUIA_Text_Shortened, &shortened);
if(shortened)
  printf("text was shortened\n");
else
  printf("text was displayed with full length\n");
```

### SEE ALSO
[MUIA_Text_Contents](MUI_Text/#MUIA_Text_Contents), [MUIA_Text_Shorten](MUI_Text/#MUIA_Text_Shorten)

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
