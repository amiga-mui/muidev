# Dirlist.mui
## Super class
[List.mui](MUI_List.md)
## Background
Dirlist class provides a quick and easy way of showing entries in a
directory. It features lots of control attributes, many of them known from
the popular ASL file requester.

This class is **NOT** intended to replace asl.library! Nobody wants to see
every MUI application coming with another selfmade file requester. Please
continue using ASL for real file requesting purposes!

However, sometimes it may be useful to have a little directory list placed
somewhere in your user interface. Imagine an answering machine tool that
stores incoming calls in a preconfigured directory. Using a dirlist object,
you can include the GUI for selecting a call in your window with lots of
other gadgets like "Play", "Delete", etc.

Dirlist class offers all of a files attributes: name, size, date, time,
flags and comment. Using the [MUIA_List_Format](MUI_List.md/#MUIA_List_Format) attribute, you can control
which of them shall be displayed.

If you want to read the entries of your directory, just send the dirlist
object a [MUIM_List_GetEntry](MUI_List.md/#MUIM_List_GetEntry) method. You will receive a pointer to a struct
FileInfoBlock which remains valid until your next call to
[MUIM_List_GetEntry](MUI_List.md/#MUIM_List_GetEntry).
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Dirlist_AcceptPattern](MUI_Dirlist.md/#MUIA_Dirlist_AcceptPattern)|V4|ISG|`STRPTR`
[MUIA_Dirlist_Directory](MUI_Dirlist.md/#MUIA_Dirlist_Directory)|V4|ISG|`STRPTR`
[MUIA_Dirlist_DrawersOnly](MUI_Dirlist.md/#MUIA_Dirlist_DrawersOnly)|V4|IS.|`BOOL`
[MUIA_Dirlist_ExAllType](MUI_Dirlist.md/#MUIA_Dirlist_ExAllType)|V20|I.G|`ULONG`
[MUIA_Dirlist_FilesOnly](MUI_Dirlist.md/#MUIA_Dirlist_FilesOnly)|V4|IS.|`BOOL`
[MUIA_Dirlist_FilterDrawers](MUI_Dirlist.md/#MUIA_Dirlist_FilterDrawers)|V4|IS.|`BOOL`
[MUIA_Dirlist_FilterHook](MUI_Dirlist.md/#MUIA_Dirlist_FilterHook)|V4|IS.|`struct Hook *`
[MUIA_Dirlist_MultiSelDirs](MUI_Dirlist.md/#MUIA_Dirlist_MultiSelDirs)|V6|IS.|`BOOL`
[MUIA_Dirlist_NumBytes](MUI_Dirlist.md/#MUIA_Dirlist_NumBytes)|V4|..G|`LONG`
[MUIA_Dirlist_NumBytes64](MUI_Dirlist.md/#MUIA_Dirlist_NumBytes64)|V20|..G|`int64 *`
[MUIA_Dirlist_NumDrawers](MUI_Dirlist.md/#MUIA_Dirlist_NumDrawers)|V4|..G|`LONG`
[MUIA_Dirlist_NumFiles](MUI_Dirlist.md/#MUIA_Dirlist_NumFiles)|V4|..G|`LONG`
[MUIA_Dirlist_Path](MUI_Dirlist.md/#MUIA_Dirlist_Path)|V4|..G|`STRPTR`
[MUIA_Dirlist_Pattern](MUI_Dirlist.md/#MUIA_Dirlist_Pattern)|V20|IS.|`STRPTR`
[MUIA_Dirlist_RejectIcons](MUI_Dirlist.md/#MUIA_Dirlist_RejectIcons)|V4|IS.|`BOOL`
[MUIA_Dirlist_RejectPattern](MUI_Dirlist.md/#MUIA_Dirlist_RejectPattern)|V4|ISG|`STRPTR`
[MUIA_Dirlist_SortDirs](MUI_Dirlist.md/#MUIA_Dirlist_SortDirs)|V4|IS.|`LONG`
[MUIA_Dirlist_SortHighLow](MUI_Dirlist.md/#MUIA_Dirlist_SortHighLow)|V4|IS.|`BOOL`
[MUIA_Dirlist_SortType](MUI_Dirlist.md/#MUIA_Dirlist_SortType)|V4|IS.|`LONG`
[MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status)|V4|..G|`LONG`

## Methods
Method|Version
------|-------
[MUIM_Dirlist_Rename](MUI_Dirlist.md/#MUIM_Dirlist_Rename)|V21
[MUIM_Dirlist_ReRead](MUI_Dirlist.md/#MUIM_Dirlist_ReRead)|V4
[MUIM_Dirlist_SetComment](MUI_Dirlist.md/#MUIM_Dirlist_SetComment)|V21
[MUIM_Dirlist_SetProtection](MUI_Dirlist.md/#MUIM_Dirlist_SetProtection)|V21

## MUIA_Dirlist_AcceptPattern
### NAME
[MUIA_Dirlist_AcceptPattern](MUI_Dirlist.md/#MUIA_Dirlist_AcceptPattern) -- V4 [ISG], `STRPTR`, 0x8042760a

FUNCTIONS
Entries not matching this pattern are rejected. Note that the pattern has to
be parsed with dos.library/ParsePatternNoCase().
Since V20 empty strings are handled like no pattern string.

### SEE ALSO
[MUIA_Dirlist_RejectPattern](MUI_Dirlist.md/#MUIA_Dirlist_RejectPattern), [MUIA_Dirlist_FilterDrawers](MUI_Dirlist.md/#MUIA_Dirlist_FilterDrawers)

## MUIA_Dirlist_Directory
### NAME
[MUIA_Dirlist_Directory](MUI_Dirlist.md/#MUIA_Dirlist_Directory) -- V4 [ISG], `STRPTR`, 0x8042ea41

### FUNCTION
Set a new directory for the dirlist object. Since reading a directory can
take a long long time, MUI delegates this work to a sub task.

Setting this attribute causes the object to clear the current directory (if
any) and start loading a new one. [MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status) will be set to
MUIV_Dirlist_Status_Reading and the sub task will be launched.

By listening to [MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status), you can learn if the directory reading
is completed or if something went wrong.

A value of NULL just clears the current directory and sets
[MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status) to MUIV_Dirlist_Status_Invalid.

### EXAMPLE
```c++
set(dirobj, MUIA_Dirlist_Directory, "ftp:incoming");
```

### SEE ALSO
[MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status)

## MUIA_Dirlist_DrawersOnly
### NAME
[MUIA_Dirlist_DrawersOnly](MUI_Dirlist.md/#MUIA_Dirlist_DrawersOnly) -- V4 [IS.], `BOOL`, 0x8042b379

### FUNCTION
Indicate whether you only want drawers to be displayed.

### SEE ALSO
[MUIA_Dirlist_Directory](MUI_Dirlist.md/#MUIA_Dirlist_Directory), [MUIA_Dirlist_FilesOnly](MUI_Dirlist.md/#MUIA_Dirlist_FilesOnly)

## MUIA_Dirlist_ExAllType
### NAME
[MUIA_Dirlist_ExAllType](MUI_Dirlist.md/#MUIA_Dirlist_ExAllType) -- V20 [I.G], `ULONG`, 0x8042cd7c

### FUNCTION
Set an ExAll() type to use. If you need the ExAllData structure in a Dirlist
hook, set the type you need here, then get the attribute again to make sure
your type is supported by MUI. Note that you might get a higher type back.

### EXAMPLE
```c++
dirobj = DirlistObject, MUIA_Dirlist_ExAllType, ED_OWNER, End;
if(xget(dirobj, MUIA_Dirlist_ExAllType) >= ED_OWNER)
{
  /* all fine */
}
```

### SEE ALSO
[MUIA_Dirlist_FilterHook](MUI_Dirlist.md/#MUIA_Dirlist_FilterHook)

## MUIA_Dirlist_FilesOnly
### NAME
[MUIA_Dirlist_FilesOnly](MUI_Dirlist.md/#MUIA_Dirlist_FilesOnly) -- V4 [IS.], `BOOL`, 0x8042896a

### FUNCTION
Indicate whether you only want files to be displayed.

### SEE ALSO
[MUIA_Dirlist_Directory](MUI_Dirlist.md/#MUIA_Dirlist_Directory), [MUIA_Dirlist_DrawersOnly](MUI_Dirlist.md/#MUIA_Dirlist_DrawersOnly)

## MUIA_Dirlist_FilterDrawers
### NAME
[MUIA_Dirlist_FilterDrawers](MUI_Dirlist.md/#MUIA_Dirlist_FilterDrawers) -- V4 [IS.], `BOOL`, 0x80424ad2

### FUNCTION
Indicate whether you want drawers matched agains [MUIA_Dirlist_RejectPattern](MUI_Dirlist.md/#MUIA_Dirlist_RejectPattern)
and [MUIA_Dirlist_AcceptPattern](MUI_Dirlist.md/#MUIA_Dirlist_AcceptPattern).

Defaults to FALSE.

### SEE ALSO
[MUIA_Dirlist_RejectPattern](MUI_Dirlist.md/#MUIA_Dirlist_RejectPattern), [MUIA_Dirlist_AcceptPattern](MUI_Dirlist.md/#MUIA_Dirlist_AcceptPattern)

## MUIA_Dirlist_FilterHook
### NAME
[MUIA_Dirlist_FilterHook](MUI_Dirlist.md/#MUIA_Dirlist_FilterHook) -- V4 [IS.], `struct Hook *`, 0x8042ae19

### FUNCTION
A hook to call for each file encountered. If the function returns TRUE, the
file is included in the file list, otherwise it is rejected and not
displayed. The function receives the following parameters:

**`struct Hook *hook (in A0)`**
     the hook itself.

**`Object *obj (in A2)`**
     the Dirlist object.

**`struct ExAllData *exd (in A1)`**
     a pointer to an initialized ExAllData structure. This one is
     valid up to the ed_Comment field.

All other filter attributes are ignored when a [MUIA_Dirlist_FilterHook](MUI_Dirlist.md/#MUIA_Dirlist_FilterHook) is
set.

### SEE ALSO
[MUIA_Dirlist_Directory](MUI_Dirlist.md/#MUIA_Dirlist_Directory)

## MUIA_Dirlist_MultiSelDirs
### NAME
[MUIA_Dirlist_MultiSelDirs](MUI_Dirlist.md/#MUIA_Dirlist_MultiSelDirs) -- V6 [IS.], `BOOL`, 0x80428653

### FUNCTION
Allows multi selection of directories.

Defaults to FALSE.

### SEE ALSO
[MUIA_Dirlist_FilterDrawers](MUI_Dirlist.md/#MUIA_Dirlist_FilterDrawers)

## MUIA_Dirlist_NumBytes
### NAME
[MUIA_Dirlist_NumBytes](MUI_Dirlist.md/#MUIA_Dirlist_NumBytes) -- V4 [..G], `LONG`, 0x80429e26

### FUNCTION
When [MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status) is MUIV_Dirlist_Valid, you can obtain the number of
bytes occupied by the directory from this tag.

### SEE ALSO
[MUIA_Dirlist_NumFiles](MUI_Dirlist.md/#MUIA_Dirlist_NumFiles), [MUIA_Dirlist_NumDrawers](MUI_Dirlist.md/#MUIA_Dirlist_NumDrawers)

## MUIA_Dirlist_NumBytes64
### NAME
[MUIA_Dirlist_NumBytes64](MUI_Dirlist.md/#MUIA_Dirlist_NumBytes64) -- V20 [..G], `int64 *`, 0x80428050

### FUNCTION
When [MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status) is MUIV_Dirlist_Valid, you can obtain the number of
bytes occupied by the directory from this tag as 64bit value.

### SEE ALSO
[MUIA_Dirlist_NumFiles](MUI_Dirlist.md/#MUIA_Dirlist_NumFiles), [MUIA_Dirlist_NumDrawers](MUI_Dirlist.md/#MUIA_Dirlist_NumDrawers)

## MUIA_Dirlist_NumDrawers
### NAME
[MUIA_Dirlist_NumDrawers](MUI_Dirlist.md/#MUIA_Dirlist_NumDrawers) -- V4 [..G], `LONG`, 0x80429cb8

### FUNCTION
When [MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status) is MUIV_Dirlist_Valid, you can obtain the number of
drawers in the displayed directory from this tag.

### SEE ALSO
[MUIA_Dirlist_NumFiles](MUI_Dirlist.md/#MUIA_Dirlist_NumFiles), [MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status)

## MUIA_Dirlist_NumFiles
### NAME
[MUIA_Dirlist_NumFiles](MUI_Dirlist.md/#MUIA_Dirlist_NumFiles) -- V4 [..G], `LONG`, 0x8042a6f0

### FUNCTION
When [MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status) is MUIV_Dirlist_Valid, you can obtain the number of
files in the displayed directory from this tag.

### SEE ALSO
[MUIA_Dirlist_NumDrawers](MUI_Dirlist.md/#MUIA_Dirlist_NumDrawers), [MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status)

## MUIA_Dirlist_Path
### NAME
[MUIA_Dirlist_Path](MUI_Dirlist.md/#MUIA_Dirlist_Path) -- V4 [..G], `STRPTR`, 0x80426176

### FUNCTION
When [MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status) is MUIV_Dirlist_Valid and you have an active entry
in the list ([MUIA_List_Active](MUI_List.md/#MUIA_List_Active) not equal MUIV_List_Active_Off), you will
receive a pointer to the complete path specification of the selected file.
Otherwise you get a NULL.

### SEE ALSO
[MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status)

## MUIA_Dirlist_Pattern
### NAME
[MUIA_Dirlist_Pattern](MUI_Dirlist.md/#MUIA_Dirlist_Pattern) -- V20 [IS.], `STRPTR`, 0x8042c761

### FUNCTION
Set a DOS pattern to match all found file names against. The given pattern
string will be used in a case insensitive way if neither the accept nor the
reject pattern excluded the file from inclusion.

### EXAMPLE
```c++
set(dirobj, MUIA_Dirlist_Pattern, "#?.png");
```

### SEE ALSO
[MUIA_Dirlist_AcceptPattern](MUI_Dirlist.md/#MUIA_Dirlist_AcceptPattern), [MUIA_Dirlist_RejectPattern](MUI_Dirlist.md/#MUIA_Dirlist_RejectPattern)

## MUIA_Dirlist_RejectIcons
### NAME
[MUIA_Dirlist_RejectIcons](MUI_Dirlist.md/#MUIA_Dirlist_RejectIcons) -- V4 [IS.], `BOOL`, 0x80424808

### FUNCTION
Indicate whether you want icons (*.info files) to be rejected.

### SEE ALSO
[MUIA_Dirlist_Directory](MUI_Dirlist.md/#MUIA_Dirlist_Directory)

## MUIA_Dirlist_RejectPattern
### NAME
[MUIA_Dirlist_RejectPattern](MUI_Dirlist.md/#MUIA_Dirlist_RejectPattern) -- V4 [ISG], `STRPTR`, 0x804259c7

### FUNCTION
Entries matching this pattern are rejected. Note that the pattern has to be
parsed with dos.library/ParsePatternNoCase().
Since V20 empty strings are handled like no pattern string.

### SEE ALSO
[MUIA_Dirlist_AcceptPattern](MUI_Dirlist.md/#MUIA_Dirlist_AcceptPattern), [MUIA_Dirlist_FilterDrawers](MUI_Dirlist.md/#MUIA_Dirlist_FilterDrawers)

## MUIA_Dirlist_SortDirs
### NAME
[MUIA_Dirlist_SortDirs](MUI_Dirlist.md/#MUIA_Dirlist_SortDirs) -- V4 [IS.], `LONG`, 0x8042bbb9

### SPECIAL INPUTS
  * MUIV_Dirlist_SortDirs_First
  * MUIV_Dirlist_SortDirs_Last
  * MUIV_Dirlist_SortDirs_Mix

### FUNCTION
Adjust the place where directories shall be displayed.

### SEE ALSO
[MUIA_Dirlist_SortHighLow](MUI_Dirlist.md/#MUIA_Dirlist_SortHighLow), [MUIA_Dirlist_SortType](MUI_Dirlist.md/#MUIA_Dirlist_SortType)

## MUIA_Dirlist_SortHighLow
### NAME
[MUIA_Dirlist_SortHighLow](MUI_Dirlist.md/#MUIA_Dirlist_SortHighLow) -- V4 [IS.], `BOOL`, 0x80421896

### FUNCTION
Indicate if you want to sort your directory reversely.

### SEE ALSO
[MUIA_Dirlist_SortType](MUI_Dirlist.md/#MUIA_Dirlist_SortType), [MUIA_Dirlist_SortDirs](MUI_Dirlist.md/#MUIA_Dirlist_SortDirs)

## MUIA_Dirlist_SortType
### NAME
[MUIA_Dirlist_SortType](MUI_Dirlist.md/#MUIA_Dirlist_SortType) -- V4 [IS.], `LONG`, 0x804228bc

### SPECIAL INPUTS
  * MUIV_Dirlist_SortType_Name
  * MUIV_Dirlist_SortType_Date
  * MUIV_Dirlist_SortType_Size
  * MUIV_Dirlist_SortType_Comment
  * MUIV_Dirlist_SortType_Flags
  * MUIV_Dirlist_SortType_Type
  * MUIV_Dirlist_SortType_Used
  * MUIV_Dirlist_SortType_Time
  * MUIV_Dirlist_SortType_DateTime
  * MUIV_Dirlist_SortType_Count

### FUNCTION
Indicate what fields should be used as sort criteria.

### SEE ALSO
[MUIA_Dirlist_SortDirs](MUI_Dirlist.md/#MUIA_Dirlist_SortDirs), [MUIA_Dirlist_SortHighLow](MUI_Dirlist.md/#MUIA_Dirlist_SortHighLow)

## MUIA_Dirlist_Status
### NAME
[MUIA_Dirlist_Status](MUI_Dirlist.md/#MUIA_Dirlist_Status) -- V4 [..G], `LONG`, 0x804240de

### SPECIAL INPUTS
  * MUIV_Dirlist_Status_Invalid
  * MUIV_Dirlist_Status_Reading
  * MUIV_Dirlist_Status_Valid

### FUNCTION
Read the status of the dirlist object. The result is one of

**`MUIV_Dirlist_Status_Invalid`**
     object contains no valid directory.

**`MUIV_Dirlist_Status_Reading`**
     object is currently reading a new directory.

**`MUIV_Dirlist_Status_Valid`**
     object contains a valid directory.

### SEE ALSO
[MUIA_Dirlist_Directory](MUI_Dirlist.md/#MUIA_Dirlist_Directory)

## MUIM_Dirlist_Rename
### NAME
[MUIM_Dirlist_Rename](MUI_Dirlist.md/#MUIM_Dirlist_Rename) -- V21, 0x8042d336

### SYNOPSIS
`DoMethod(obj, MUIM_Dirlist_Rename, LONG row, CONST_STRPTR newname);`

### FUNCTION
Rename the file or directory associated with the specified row to the new
name.

### INPUTS
**`LONG row`**
     row of entry to be renamed.

**`CONST_STRPTR newname`**
     new name of entry.

### RESULT
Zero on success or IoErr() value in case of failure.

### SEE ALSO
dos.library/IoErr(), dos.library/Rename()

## MUIM_Dirlist_ReRead
### NAME
[MUIM_Dirlist_ReRead](MUI_Dirlist.md/#MUIM_Dirlist_ReRead) -- V4, 0x80422d71

### SYNOPSIS
`DoMethod(obj, MUIM_Dirlist_ReRead);`

### FUNCTION
Force the dirlist object to reread the current directory.

### EXAMPLE
```c++
if(NewCallReceived())
  DoMethod(dirlistobj, MUIM_Dirlist_ReRead);
```

### SEE ALSO
[MUIA_Dirlist_Directory](MUI_Dirlist.md/#MUIA_Dirlist_Directory)

## MUIM_Dirlist_SetComment
### NAME
[MUIM_Dirlist_SetComment](MUI_Dirlist.md/#MUIM_Dirlist_SetComment) -- V21, 0x8042b378

### SYNOPSIS
`DoMethod(obj, MUIM_Dirlist_SetComment, LONG row, CONST_STRPTR comment);`

### FUNCTION
Set the comment of the file or directory associated with the specified row
to the new comment.

### INPUTS
**`LONG row`**
     row of entry to be commented.

**`CONST_STRPTR comment`**
     new comment of entry.

### RESULT
Zero on success or IoErr() value in case of failure.

### SEE ALSO
dos.library/IoErr(), dos.library/SetComment()

## MUIM_Dirlist_SetProtection
### NAME
[MUIM_Dirlist_SetProtection](MUI_Dirlist.md/#MUIM_Dirlist_SetProtection) -- V21, 0x804202bb

### SYNOPSIS
`DoMethod(obj, MUIM_Dirlist_SetProtection, LONG row, ULONG flags);`

### FUNCTION
Set the protection bits the file or directory associated with the specified
row to the new value.

### INPUTS
**`LONG row`**
     row of entry to set the protection bits for.

**`ULONG flags`**
     new protection bits.

### RESULT
Zero on success or IoErr() value in case of failure.

### SEE ALSO
dos.library/IoErr(), dos.library/SetProtection()

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
