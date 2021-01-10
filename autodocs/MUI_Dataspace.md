# Dataspace.mui
## Super class
[Semaphore.mui](MUI_Semaphore.md)
## Background
The Dataspace class serves as a very simple container for all kinds of data.
You can add data items and reference them later through an ID. Furthermore,
Dataspace class features methods to import/export a complete Dataspace
from/to an IFF file handle.

MUI uses subclasses of dataspace class to handle all its configuration data
and that's probably the main purpose of a dataspace.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Dataspace_Count](MUI_Dataspace.md/#MUIA_Dataspace_Count)|V20|..G|`ULONG`
[MUIA_Dataspace_Pool](MUI_Dataspace.md/#MUIA_Dataspace_Pool)|V11|I..|`APTR`

## Methods
Method|Version
------|-------
[MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add)|V11
[MUIM_Dataspace_Clear](MUI_Dataspace.md/#MUIM_Dataspace_Clear)|V11
[MUIM_Dataspace_Find](MUI_Dataspace.md/#MUIM_Dataspace_Find)|V11
[MUIM_Dataspace_Get](MUI_Dataspace.md/#MUIM_Dataspace_Get)|V21
[MUIM_Dataspace_Merge](MUI_Dataspace.md/#MUIM_Dataspace_Merge)|V11
[MUIM_Dataspace_ReadIFF](MUI_Dataspace.md/#MUIM_Dataspace_ReadIFF)|V11
[MUIM_Dataspace_Remove](MUI_Dataspace.md/#MUIM_Dataspace_Remove)|V11
[MUIM_Dataspace_WriteIFF](MUI_Dataspace.md/#MUIM_Dataspace_WriteIFF)|V11

## MUIA_Dataspace_Count
### NAME
[MUIA_Dataspace_Count](MUI_Dataspace.md/#MUIA_Dataspace_Count) -- V20 [..G], `ULONG`, 0x8042e7ea

### FUNCTION
Determine the number of entries in the Dataspace object.

### SEE ALSO
[MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add), [MUIM_Dataspace_Remove](MUI_Dataspace.md/#MUIM_Dataspace_Remove)

## MUIA_Dataspace_Pool
### NAME
[MUIA_Dataspace_Pool](MUI_Dataspace.md/#MUIA_Dataspace_Pool) -- V11 [I..], `APTR`, 0x80424cf9

### FUNCTION
If you specify a memory pool from exec.library/CreatePool() here, the
dataspace object will use this pool for all its entries.

If you omit this tag or pass NULL, the dataspace object will create its own
memory pool instead.

### SEE ALSO
[MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add), exec.library/CreatePool

## MUIM_Dataspace_Add
### NAME
[MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add) -- V11, 0x80423366

### SYNOPSIS
`DoMethod(obj, MUIM_Dataspace_Add, CONST_APTR data, LONG len, ULONG id);`

### FUNCTION
This method adds a new entry to the dataspace. If an entry with the same ID
already exists, it will be replaced with the new entry.

### INPUTS
**`CONST_APTR data`**
     pointer to a data.

**`LONG len`**
     length of data.

**`ULONG id`**
     reference ID.

A negative length value will assume data to be a NUL terminated string and
will recalculate the length as strlen(data)+1

### RESULT
Returns NULL on failure (probably because of a memory shortage) or some non
NULL value on success.

### SEE ALSO
[MUIM_Dataspace_Remove](MUI_Dataspace.md/#MUIM_Dataspace_Remove), [MUIM_Dataspace_Find](MUI_Dataspace.md/#MUIM_Dataspace_Find)

## MUIM_Dataspace_Clear
### NAME
[MUIM_Dataspace_Clear](MUI_Dataspace.md/#MUIM_Dataspace_Clear) -- V11, 0x8042b6c9

### SYNOPSIS
`DoMethod(obj, MUIM_Dataspace_Clear);`

### FUNCTION
This method clears all the contents of a dataspace. Depending on the state
of the memory pool that the dataspace object uses, this may or may not
result in more free memory.

### INPUTS
none

### RESULT
All entries will be removed from the dataspace. The return value of this
method is currently undefined.

### SEE ALSO
[MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add), [MUIM_Dataspace_Remove](MUI_Dataspace.md/#MUIM_Dataspace_Remove), [MUIM_Dataspace_Merge](MUI_Dataspace.md/#MUIM_Dataspace_Merge)

## MUIM_Dataspace_Find
### NAME
[MUIM_Dataspace_Find](MUI_Dataspace.md/#MUIM_Dataspace_Find) -- V11, 0x8042832c

### SYNOPSIS
`DoMethod(obj, MUIM_Dataspace_Find, ULONG id);`

### FUNCTION
This method tries to look up an entry with the specified ID in the
dataspace.

### INPUTS
**`ULONG id`**
     reference ID.

### RESULT
Returns NULL on failure (entry not found) or some non NULL value on success.
A non NULL return value will point to the data area which has been added
before using [MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add).

### SEE ALSO
[MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add), [MUIM_Dataspace_Get](MUI_Dataspace.md/#MUIM_Dataspace_Get), [MUIM_Dataspace_Remove](MUI_Dataspace.md/#MUIM_Dataspace_Remove)

## MUIM_Dataspace_Get
### NAME
[MUIM_Dataspace_Get](MUI_Dataspace.md/#MUIM_Dataspace_Get) -- V21, 0x8042483f

### SYNOPSIS
`DoMethod(obj, MUIM_Dataspace_Get, ULONG id, ULONG *size);`

### FUNCTION
This method tries to look up an entry with the specified ID in the
dataspace.

### INPUTS
**`ULONG id`**
     reference ID.

**`ULONG *size`**
     pointer to a ULONG.

### RESULT
Returns NULL on failure (entry not found) or some non NULL value on success.
A non NULL return value will point to the data area which has been added
before using [MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add). Additionally the size of the entry will be
returned in the size parameter.

### SEE ALSO
[MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add), [MUIM_Dataspace_Find](MUI_Dataspace.md/#MUIM_Dataspace_Find), [MUIM_Dataspace_Remove](MUI_Dataspace.md/#MUIM_Dataspace_Remove)

## MUIM_Dataspace_Merge
### NAME
[MUIM_Dataspace_Merge](MUI_Dataspace.md/#MUIM_Dataspace_Merge) -- V11, 0x80423e2b

### SYNOPSIS
`DoMethod(obj, MUIM_Dataspace_Merge, Object *dataspace);`

### FUNCTION
This method adds all the contents of the merge dataspace specified as
parameter to the objects dataspace. As with [MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add), entries with
equal IDs will be replaced.

### INPUTS
**`Object *dataspace`**
     a Dataspace object which contents should be merged.

### RESULT
Returns the number of entries that have been added/replaced in the object's
dataspace. If this number doesn't match the number of entries in the merge
dataspace, something probably went wrong.

### SEE ALSO
[MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add), [MUIM_Dataspace_Remove](MUI_Dataspace.md/#MUIM_Dataspace_Remove)

## MUIM_Dataspace_ReadIFF
### NAME
[MUIM_Dataspace_ReadIFF](MUI_Dataspace.md/#MUIM_Dataspace_ReadIFF) -- V11, 0x80420dfb

### SYNOPSIS
`DoMethod(obj, MUIM_Dataspace_ReadIFF, struct IFFHandle *handle);`

### FUNCTION
Adds the contents of an IFF handle from iffparse.library to the dataspace.
As always, objects with the same ID that are already in the dataspace will
be replaced.

This method does not look for any chunk types and chunk IDs itself. Instead,
it expects that you have already located the chunk which contains your data
and does nothing but ReadChunkBytes() until all dataspace entries of the
current chunk are read.

### NOTES
Do not call [MUIM_Dataspace_ReadIFF](MUI_Dataspace.md/#MUIM_Dataspace_ReadIFF) if your handle is positioned on chunks
that were not written with [MUIM_Dataspace_WriteIFF](MUI_Dataspace.md/#MUIM_Dataspace_WriteIFF) or strange things may
happen!

### INPUTS
**`struct IFFHandle *handle`**
     pointer to a struct IFFHandle from iffparse.library/AllocIFF(). The
     handle must already be open, initialized for reading and positioned
     on a chunk that was created with [MUIM_Dataspace_WriteIFF](MUI_Dataspace.md/#MUIM_Dataspace_WriteIFF).

### RESULT
Returns 0 on success or some IFFERR_xxx on failure.

### SEE ALSO
[MUIM_Dataspace_WriteIFF](MUI_Dataspace.md/#MUIM_Dataspace_WriteIFF), iffparse.library/AllocIFF

## MUIM_Dataspace_Remove
### NAME
[MUIM_Dataspace_Remove](MUI_Dataspace.md/#MUIM_Dataspace_Remove) -- V11, 0x8042dce1

### SYNOPSIS
`DoMethod(obj, MUIM_Dataspace_Remove, ULONG id);`

### FUNCTION
This method removes an entry from the dataspace.

### INPUTS
**`ULONG id`**
     reference ID.

### RESULT
Returns NULL if no entry with the given ID was found in the dataspace or
some non NULL value on success.

### SEE ALSO
[MUIM_Dataspace_Add](MUI_Dataspace.md/#MUIM_Dataspace_Add), [MUIM_Dataspace_Find](MUI_Dataspace.md/#MUIM_Dataspace_Find)

## MUIM_Dataspace_WriteIFF
### NAME
[MUIM_Dataspace_WriteIFF](MUI_Dataspace.md/#MUIM_Dataspace_WriteIFF) -- V11, 0x80425e8e

### SYNOPSIS
`DoMethod(obj, MUIM_Dataspace_WriteIFF, struct IFFHandle *handle, ULONG type, ULONG id);`

### FUNCTION
Writes the contents of a dataspace to an IFF handle of iffparse.library.

In detail, a chunk with the specified type and ID is created with
PushChunk(), the contents of the dataspace are written with
WriteChunkBytes() and the chunk is terminated with PopChunk().

### INPUTS
**`struct IFFHandle *handle`**
     pointer to a struct IFFHandle from iffparse.library/AllocIFF().
     The handle must already be open and initialized for writing.

**`ULONG type`**
     type of chunk to create.

**`ULONG id`**
     ID of chunk to create.

### RESULT
Returns 0 on success or some IFFERR_xxx on failure.

### SEE ALSO
[MUIM_Dataspace_ReadIFF](MUI_Dataspace.md/#MUIM_Dataspace_ReadIFF), iffparse.library/AllocIFF

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
