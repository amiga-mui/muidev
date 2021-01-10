# Floattext.mui
## Super class
[List.mui](MUI_List.md)
## Background
Floattext class is a subclass of list class that takes a big text string as
input and splits it up into several lines to be dislayed. Formatting
capabilities include paragraphs an justified text with word wrap.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Floattext_Justify](MUI_Floattext.md/#MUIA_Floattext_Justify)|V4|ISG|`BOOL`
[MUIA_Floattext_KeepStyles](MUI_Floattext.md/#MUIA_Floattext_KeepStyles)|V20|I..|`BOOL`
[MUIA_Floattext_SkipChars](MUI_Floattext.md/#MUIA_Floattext_SkipChars)|V4|IS.|`STRPTR`
[MUIA_Floattext_TabSize](MUI_Floattext.md/#MUIA_Floattext_TabSize)|V4|IS.|`LONG`
[MUIA_Floattext_Text](MUI_Floattext.md/#MUIA_Floattext_Text)|V4|ISG|`STRPTR`

## Methods
Method|Version
------|-------
[MUIM_Floattext_Append](MUI_Floattext.md/#MUIM_Floattext_Append)|V20

## MUIA_Floattext_Justify
### NAME
[MUIA_Floattext_Justify](MUI_Floattext.md/#MUIA_Floattext_Justify) -- V4 [ISG], `BOOL`, 0x8042dc03

### FUNCTION
Indicate whether you want your the text aligned to the left and right
border. MUI will try to insert spaces between words to reach this goal.

If you want right aligned or centered text, use the [MUIA_List_Format](MUI_List.md/#MUIA_List_Format)
attribute.

### SEE ALSO
[MUIA_Floattext_Text](MUI_Floattext.md/#MUIA_Floattext_Text), [MUIA_List_Format](MUI_List.md/#MUIA_List_Format)

## MUIA_Floattext_KeepStyles
### NAME
[MUIA_Floattext_KeepStyles](MUI_Floattext.md/#MUIA_Floattext_KeepStyles) -- V20 [I..], `BOOL`, 0x80427b9f

### FUNCTION
If set to TRUE any active text styles at the end of a paragraph will be kept
instead of being reset back to plain text.

Defaults to FALSE.

### SEE ALSO
[MUIA_Floattext_Text](MUI_Floattext.md/#MUIA_Floattext_Text)

## MUIA_Floattext_SkipChars
### NAME
[MUIA_Floattext_SkipChars](MUI_Floattext.md/#MUIA_Floattext_SkipChars) -- V4 [IS.], `STRPTR`, 0x80425c7d

### FUNCTION
Defines an array of characters that shall be skipped when displaying the
text. If you e.g. want to display a fido message and know it has some CTRL-A
control characters in it, you could set this attribute to "\1" to prevent
Floattext class from displaying unreadable crap.

### SEE ALSO
[MUIA_Floattext_Text](MUI_Floattext.md/#MUIA_Floattext_Text)

## MUIA_Floattext_TabSize
### NAME
[MUIA_Floattext_TabSize](MUI_Floattext.md/#MUIA_Floattext_TabSize) -- V4 [IS.], `LONG`, 0x80427d17

### FUNCTION
Adjust the tab size for a text. The tab size is measured in spaces, so if
you plan to use tabs not only at the beginning of a paragraph, you should
consider using the fixed width font.

Defaults to 8.

### SEE ALSO
[MUIA_Floattext_Text](MUI_Floattext.md/#MUIA_Floattext_Text)

## MUIA_Floattext_Text
### NAME
[MUIA_Floattext_Text](MUI_Floattext.md/#MUIA_Floattext_Text) -- V4 [ISG], `STRPTR`, 0x8042d16a

### FUNCTION
Strings of characters to be displayed as floattext. This string may contain
linefeeds to mark the end of paragraphs or tab characters for indention.

MUI will automatically format the text according to the width of the
floattext object. If a word does not fit into the current line, it will be
wrapped.

If you plan to use tabs not only at the beginning of a line you should
consider using the configured fixed width font.

MUI copies the complete string into a private buffer, you don't need to keep
your text in memory. If memory is low, nothing will be displayed. That's why
you always have to be prepared for handling a NULL pointer when getting back
[MUIA_Floattext_Text](MUI_Floattext.md/#MUIA_Floattext_Text).

Setting [MUIA_Floattext_Text](MUI_Floattext.md/#MUIA_Floattext_Text) to NULL means to clear the current text.

Please note that justification and word wrap with proportional fonts is a
complicated operation and may take a considerable amount of time, especially
with long texts on slow machines.

Any active text styles (i.e. bold text or colors) will be reset at the end
of a paragraph indicated by a line feed character (0x0a, \n). However, it is
possible to switch off this behaviour by setting the attribute
[MUIA_Floattext_KeepStyles](MUI_Floattext.md/#MUIA_Floattext_KeepStyles) to TRUE.

### EXAMPLE
```c++
char *text = AllocVec(filesize, MEMF_ANY);

Read(file,text,filesize);

fto = FloattextObject,
  MUIA_Floattext_Text, text,
  End;

FreeVec(text);

/* ... if you need your text later, you can get it   */
/* with a simple get(fto, MUIA_Floattext_Text, &text); */
```

### SEE ALSO
[MUIA_Floattext_Justify](MUI_Floattext.md/#MUIA_Floattext_Justify), [MUIA_Floattext_TabSize](MUI_Floattext.md/#MUIA_Floattext_TabSize), [MUIA_Floattext_SkipChars](MUI_Floattext.md/#MUIA_Floattext_SkipChars),
[MUIA_Floattext_KeepStyles](MUI_Floattext.md/#MUIA_Floattext_KeepStyles)

## MUIM_Floattext_Append
### NAME
[MUIM_Floattext_Append](MUI_Floattext.md/#MUIM_Floattext_Append) -- V20, 0x8042a221

### SYNOPSIS
`DoMethod(obj, MUIM_Floattext_Append, CONST_STRPTR Text);`

### FUNCTION
Appends the given text to the already existing text. The additional text
will be copied to a private buffer.

### INPUTS
**`CONST_STRPTR Text`**
     text to be appended.

### RESULT
A boolean value indicating whether the append operation succeeded or not.

### EXAMPLE
```c++
set(obj, MUIA_Floattext_Text, "Hello");
/* the object will now display the text "Hello" */
DoMethod(obj, MUIM_Floattext_Append, " World!");
/* the object will now display the text "Hello World!" */
```

### SEE ALSO
[MUIA_Floattext_Text](MUI_Floattext.md/#MUIA_Floattext_Text)

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
