# Datamap.mui
## Super class
[Semaphore.mui](MUI_Semaphore.md)
## Background
The Datamap class serves as a simple data container, similar to Dataspace. They
both are subclasses of Semaphore clas. The data is sorted by the string key
using btree.library. This makes lookups very fast.

Datamap is designed to store arbitrary data.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Datamap_AutoLock](MUI_Datamap.md/#MUIA_Datamap_AutoLock)|V20|I..|`BOOL`
[MUIA_Datamap_CopyKeys](MUI_Datamap.md/#MUIA_Datamap_CopyKeys)|V20|I..|`BOOL`
[MUIA_Datamap_Count](MUI_Datamap.md/#MUIA_Datamap_Count)|V21|..G|`ULONG`
[MUIA_Datamap_Pool](MUI_Datamap.md/#MUIA_Datamap_Pool)|V20|I..|`APTR`

## Methods
Method|Version
------|-------
[MUIM_Datamap_Clear](MUI_Datamap.md/#MUIM_Datamap_Clear)|V20
[MUIM_Datamap_Find](MUI_Datamap.md/#MUIM_Datamap_Find)|V20
[MUIM_Datamap_Get](MUI_Datamap.md/#MUIM_Datamap_Get)|V21
[MUIM_Datamap_Iterate](MUI_Datamap.md/#MUIM_Datamap_Iterate)|V20
[MUIM_Datamap_IterationKey](MUI_Datamap.md/#MUIM_Datamap_IterationKey)|V20
[MUIM_Datamap_Remove](MUI_Datamap.md/#MUIM_Datamap_Remove)|V20
[MUIM_Datamap_Set](MUI_Datamap.md/#MUIM_Datamap_Set)|V20

## MUIA_Datamap_AutoLock
### NAME
[MUIA_Datamap_AutoLock](MUI_Datamap.md/#MUIA_Datamap_AutoLock) -- V20 [I..], `BOOL`, 0x8042fbe4

### FUNCTION
Setting this attribute to TRUE ensures that Datamap methods are called under
appropriate locks. Please note that this does not guarantee that the
returned data will stay valid on return. It also does not protect the
iteration methods. In case the Datamap is used by multiple threads, you must
put the whole iteration into an exclusive lock.

## MUIA_Datamap_CopyKeys
### NAME
[MUIA_Datamap_CopyKeys](MUI_Datamap.md/#MUIA_Datamap_CopyKeys) -- V20 [I..], `BOOL`, 0x8042a179

### FUNCTION
Setting this attribute to FALSE will skip the copying of the passed key to
[MUIM_Datamap_Set](MUI_Datamap.md/#MUIM_Datamap_Set). Instead the key will be used directly for all tree
related actions. It is up the the application to ensure the validity of the
key as long as the corresponding entry is contained in the tree.

This attribute is very useful if your application uses static strings as
keys for example.

## MUIA_Datamap_Count
### NAME
[MUIA_Datamap_Count](MUI_Datamap.md/#MUIA_Datamap_Count) -- V21 [..G], `ULONG`, 0x80427580

### FUNCTION
Returns the number of stored items in the Datamap object.

## MUIA_Datamap_Pool
### NAME
[MUIA_Datamap_Pool](MUI_Datamap.md/#MUIA_Datamap_Pool) -- V20 [I..], `APTR`, 0x80424724

### FUNCTION
If set to a valid memory pool pointer created by exec/CreatePool() the
datamap object will use this pool for all memory allocations instead of
creating a private pool.

### SEE ALSO
[MUIM_Datamap_Set](MUI_Datamap.md/#MUIM_Datamap_Set), exec.library/CreatePool

## MUIM_Datamap_Clear
### NAME
[MUIM_Datamap_Clear](MUI_Datamap.md/#MUIM_Datamap_Clear) -- V20, 0x8042eebc

### SYNOPSIS
`DoMethod(obj, MUIM_Datamap_Clear);`

### FUNCTION
Remove and free all entries in the Datamap object.

## MUIM_Datamap_Find
### NAME
[MUIM_Datamap_Find](MUI_Datamap.md/#MUIM_Datamap_Find) -- V20, 0x8042d650

### SYNOPSIS
`DoMethod(obj, MUIM_Datamap_Find, CONST_STRPTR key);`

### FUNCTION
Look up an entry by a key.

### INPUTS
**`CONST_STRPTR key`**
     key to look up the entry by.

### RESULT
Pointer to the stored data or NULL in case the key was not found.

### SEE ALSO
[MUIM_Datamap_Get](MUI_Datamap.md/#MUIM_Datamap_Get), [MUIM_Datamap_Iterate](MUI_Datamap.md/#MUIM_Datamap_Iterate)

## MUIM_Datamap_Get
### NAME
[MUIM_Datamap_Get](MUI_Datamap.md/#MUIM_Datamap_Get) -- V21, 0x8042c2ba

### SYNOPSIS
`DoMethod(obj, MUIM_Datamap_Get, CONST_STRPTR key, ULONG *size);`

### FUNCTION
Look up an entry by a key.

### INPUTS
**`CONST_STRPTR key`**
     key to look up the entry by.

**`ULONG *size`**
     pointer to ULONG.

### RESULT
Pointer to the stored data or NULL in case the key was not found.
Additionally the size of the entry will be returned in the size parameter.

### SEE ALSO
[MUIM_Datamap_Set](MUI_Datamap.md/#MUIM_Datamap_Set), [MUIM_Datamap_Find](MUI_Datamap.md/#MUIM_Datamap_Find), [MUIM_Datamap_Get](MUI_Datamap.md/#MUIM_Datamap_Get), [MUIM_Datamap_Iterate](MUI_Datamap.md/#MUIM_Datamap_Iterate)

## MUIM_Datamap_Iterate
### NAME
[MUIM_Datamap_Iterate](MUI_Datamap.md/#MUIM_Datamap_Iterate) -- V20, 0x8042fda1

### SYNOPSIS
`DoMethod(obj, MUIM_Datamap_Iterate, ULONG *counter);`

### FUNCTION
This method iterates over all stored keys. It is perfectly legal to continue
the iteration after removing the current item by calling [MUIM_Datamap_Remove](MUI_Datamap.md/#MUIM_Datamap_Remove)
but calling [MUIM_Datamap_Clear](MUI_Datamap.md/#MUIM_Datamap_Clear) will make the iterator invalid.

### INPUTS
**`ULONG *counter`**
     pointer to a 32bit-sized storage for internal usage. This storage
     **MUST** be zeroed before starting the iteration.

### RESULT
Pointer to the stored data or NULL after returning the last item

### SEE ALSO
[MUIM_Datamap_IterationKey](MUI_Datamap.md/#MUIM_Datamap_IterationKey)

## MUIM_Datamap_IterationKey
### NAME
[MUIM_Datamap_IterationKey](MUI_Datamap.md/#MUIM_Datamap_IterationKey) -- V20, 0x8042bc15

### SYNOPSIS
`DoMethod(obj, MUIM_Datamap_IterationKey, ULONG *counter);`

### FUNCTION
Returns the key associated with the current iteration stage.

### INPUTS
**`ULONG *counter`**
     pointer to the 32bit-sized storage used for [MUIM_Datamap_Iterate](MUI_Datamap.md/#MUIM_Datamap_Iterate).

### RESULT
Pointer to a key or NULL if the counter doesn't contain a valid entry

### EXAMPLE
```c++
Object o = DatamapObject, End;
APTR item;
ULONG counter;

/* assume data has been inserted into the map before */
counter = 0;
while((item = (APTR)DoMethod(o, MUIM_Datamap_Iterate, &counter)) != NULL)
{
  CONST_STRPTR key = (CONST_STRPTR)DoMethod(o, MUIM_Datamap_IterationKey, &counter);

  printf("key '%s', data %p\n", key, item);
}
```

### SEE ALSO
[MUIM_Datamap_Iterate](MUI_Datamap.md/#MUIM_Datamap_Iterate)

## MUIM_Datamap_Remove
### NAME
[MUIM_Datamap_Remove](MUI_Datamap.md/#MUIM_Datamap_Remove) -- V20, 0x804203d8

### SYNOPSIS
`DoMethod(obj, MUIM_Datamap_Remove, CONST_STRPTR key);`

### FUNCTION
Removes the entry corresponding to the specified key.

### INPUTS
**`CONST_STRPTR key`**
     key to look up the entry by.

### RESULT
NULL if no corresponding entry was not found.

### SEE ALSO
[MUIM_Datamap_Set](MUI_Datamap.md/#MUIM_Datamap_Set)

## MUIM_Datamap_Set
### NAME
[MUIM_Datamap_Set](MUI_Datamap.md/#MUIM_Datamap_Set) -- V20, 0x8042b84f

### SYNOPSIS
`DoMethod(obj, MUIM_Datamap_Set, CONST_APTR data, LONG len, CONST_STRPTR key);`

### FUNCTION
This method adds or changes an entry corresponding to the specified key.
Keys are considered to be unique within a tree. Hence calling
[MUIM_Datamap_Set](MUI_Datamap.md/#MUIM_Datamap_Set) multiple times with the same key will overwrite the data
set before.

### INPUTS
**`CONST_APTR data`**
     pointer to data to store.

**`LONG len`**
     size of the data.

**`CONST_STRPTR key`**
     the key to index the data by.

### RESULT
NULL on failure or a non-NULL value on success.

### SEE ALSO
[MUIM_Datamap_Remove](MUI_Datamap.md/#MUIM_Datamap_Remove), [MUIM_Datamap_Find](MUI_Datamap.md/#MUIM_Datamap_Find), [MUIM_Datamap_Iterate](MUI_Datamap.md/#MUIM_Datamap_Iterate)

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
