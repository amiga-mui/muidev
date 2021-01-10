# Objectmap.mui
## Super class
[Semaphore.mui](MUI_Semaphore.md)
## Background
The Objectmap class serves as a simple data container, similar to Dataspace
and Datamap. They both are subclasses of Semaphore class. The data is sorted
by the string key using btree.library. This makes lookups very fast.

In contrast to Datamap class Objectmap class is designed to store MUI objects
only. By adding an object to the map using [MUIM_Objectmap_Set](MUI_Objectmap.md/#MUIM_Objectmap_Set) the application
loses the ownership of the object as long as it is a member of the Objectmap.
Such objects will be disposed when the Objectmap is disposed. This matches
the behavior and rules of Family class subclasses. Removing an object from the
Objectmap will return the ownership back to the application.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Objectmap_AutoLock](MUI_Objectmap.md/#MUIA_Objectmap_AutoLock)|V20|I..|`BOOL`
[MUIA_Objectmap_CopyKeys](MUI_Objectmap.md/#MUIA_Objectmap_CopyKeys)|V20|I..|`BOOL`
[MUIA_Objectmap_Count](MUI_Objectmap.md/#MUIA_Objectmap_Count)|V21|..G|`ULONG`
[MUIA_Objectmap_Pool](MUI_Objectmap.md/#MUIA_Objectmap_Pool)|V20|I..|`APTR`

## Methods
Method|Version
------|-------
[MUIM_Objectmap_Clear](MUI_Objectmap.md/#MUIM_Objectmap_Clear)|V20
[MUIM_Objectmap_Find](MUI_Objectmap.md/#MUIM_Objectmap_Find)|V20
[MUIM_Objectmap_Iterate](MUI_Objectmap.md/#MUIM_Objectmap_Iterate)|V20
[MUIM_Objectmap_IterationKey](MUI_Objectmap.md/#MUIM_Objectmap_IterationKey)|V20
[MUIM_Objectmap_Remove](MUI_Objectmap.md/#MUIM_Objectmap_Remove)|V20
[MUIM_Objectmap_Set](MUI_Objectmap.md/#MUIM_Objectmap_Set)|V20

## MUIA_Objectmap_AutoLock
### NAME
[MUIA_Objectmap_AutoLock](MUI_Objectmap.md/#MUIA_Objectmap_AutoLock) -- V20 [I..], `BOOL`, 0x8042e65f

### FUNCTION
Setting this attribute to TRUE ensures that Objectmap methods are called
under appropriate locks. Please note that this does not guarantee that the
returned object will stay valid on return. It also does not protect the
iteration methods. In case the Objectmap is used by multiple threads, you
must put the whole iteration into an exclusive lock.

## MUIA_Objectmap_CopyKeys
### NAME
[MUIA_Objectmap_CopyKeys](MUI_Objectmap.md/#MUIA_Objectmap_CopyKeys) -- V20 [I..], `BOOL`, 0x8042b964

### FUNCTION
Setting this attribute to FALSE will skip the copying of the passed key to
[MUIM_Objectmap_Set](MUI_Objectmap.md/#MUIM_Objectmap_Set). Instead the key will be used directly for all tree
related actions. It is up the the application to ensure the validity of the
key as long as the corresponding object is contained in the tree.

This attribute is very useful if your application uses static strings as
keys for example.

## MUIA_Objectmap_Count
### NAME
[MUIA_Objectmap_Count](MUI_Objectmap.md/#MUIA_Objectmap_Count) -- V21 [..G], `ULONG`, 0x80426006

### FUNCTION
Returns the number of stored objects in the Objectmap object.

## MUIA_Objectmap_Pool
### NAME
[MUIA_Objectmap_Pool](MUI_Objectmap.md/#MUIA_Objectmap_Pool) -- V20 [I..], `APTR`, 0x80422ed3

### FUNCTION
If set to a valid memory pool pointer created by exec/CreatePool() the
objectmap object will use this pool for all memory allocations instead of
creating a private pool.

### SEE ALSO
[MUIM_Objectmap_Set](MUI_Objectmap.md/#MUIM_Objectmap_Set), exec.library/CreatePool

## MUIM_Objectmap_Clear
### NAME
[MUIM_Objectmap_Clear](MUI_Objectmap.md/#MUIM_Objectmap_Clear) -- V20, 0x80422ee5

### SYNOPSIS
`DoMethod(obj, MUIM_Objectmap_Clear);`

### FUNCTION
Remove and dispose all objects in the Objectmap object.

## MUIM_Objectmap_Find
### NAME
[MUIM_Objectmap_Find](MUI_Objectmap.md/#MUIM_Objectmap_Find) -- V20, 0x80426506

### SYNOPSIS
`DoMethod(obj, MUIM_Objectmap_Find, CONST_STRPTR key);`

### FUNCTION
Look up an object by a key.

### INPUTS
**`CONST_STRPTR key`**
     key to look up the object by.

### RESULT
Pointer to the stored object or NULL in case the key was not found.

### SEE ALSO
[MUIM_Objectmap_Iterate](MUI_Objectmap.md/#MUIM_Objectmap_Iterate)

## MUIM_Objectmap_Iterate
### NAME
[MUIM_Objectmap_Iterate](MUI_Objectmap.md/#MUIM_Objectmap_Iterate) -- V20, 0x804262bc

### SYNOPSIS
`DoMethod(obj, MUIM_Objectmap_Iterate, ULONG *counter);`

### FUNCTION
This method iterates over all stored keys. It is perfectly legal to continue
the iteration after removing the current object by calling
[MUIM_Objectmap_Remove](MUI_Objectmap.md/#MUIM_Objectmap_Remove) but calling [MUIM_Objectmap_Clear](MUI_Objectmap.md/#MUIM_Objectmap_Clear) will make the
iterator invalid.

### INPUTS
**`ULONG *counter`**
     pointer to a 32bit-sized storage for internal usage. This storage
     **MUST** be zeroed before starting the iteration.

### RESULT
Pointer to the stored object or NULL after returning the last object

### SEE ALSO
[MUIM_Objectmap_IterationKey](MUI_Objectmap.md/#MUIM_Objectmap_IterationKey)

## MUIM_Objectmap_IterationKey
### NAME
[MUIM_Objectmap_IterationKey](MUI_Objectmap.md/#MUIM_Objectmap_IterationKey) -- V20, 0x8042d7ff

### SYNOPSIS
`DoMethod(obj, MUIM_Objectmap_IterationKey, ULONG *counter);`

### FUNCTION
Returns the key associated with the current iteration stage.

### INPUTS
**`ULONG *counter`**
     pointer to the 32bit-sized storage used for [MUIM_Objectmap_Iterate](MUI_Objectmap.md/#MUIM_Objectmap_Iterate).

### RESULT
Pointer to a key or NULL if the counter doesn't contain a valid entry

### EXAMPLE
```c++
Object o = ObjectmapObject, End;
Object *obj;
ULONG counter;

/* assume data has been inserted into the map before */
counter = 0;
while((obj = (Object *)DoMethod(o, MUIM_Objectmap_Iterate, &counter)) != NULL)
{
  CONST_STRPTR key = (CONST_STRPTR)DoMethod(o, MUIM_Objectmap_IterationKey, &counter);

  printf("key '%s', object %p\n", key, item);
}
```

### SEE ALSO
[MUIM_Objectmap_Iterate](MUI_Objectmap.md/#MUIM_Objectmap_Iterate)

## MUIM_Objectmap_Remove
### NAME
[MUIM_Objectmap_Remove](MUI_Objectmap.md/#MUIM_Objectmap_Remove) -- V20, 0x8042f649

### SYNOPSIS
`DoMethod(obj, MUIM_Objectmap_Remove, CONST_STRPTR key);`

### FUNCTION
Removes the object corresponding to the specified key. After removing the
object from the Objectmap the ownership by Objectmap end and the object
must be disposed separately again.

### INPUTS
**`CONST_STRPTR key`**
     key to look up the object by.

### RESULT
NULL if no corresponding object was not found.

### SEE ALSO
[MUIM_Objectmap_Set](MUI_Objectmap.md/#MUIM_Objectmap_Set)

## MUIM_Objectmap_Set
### NAME
[MUIM_Objectmap_Set](MUI_Objectmap.md/#MUIM_Objectmap_Set) -- V20, 0x80421ec5

### SYNOPSIS
`DoMethod(obj, MUIM_Objectmap_Set, Object *o, CONST_STRPTR key);`

### FUNCTION
This method adds or changes an object corresponding to the specified key.
Keys are considered to be unique within a tree. Hence calling
[MUIM_Objectmap_Set](MUI_Objectmap.md/#MUIM_Objectmap_Set) multiple times with the same key will overwrite the
object set before.

### INPUTS
**`Object *o`**
     pointer to an object to store in the map.

**`CONST_STRPTR key`**
     the key to index the data by.

### RESULT
NULL on failure or a non-NULL value on success.

### SEE ALSO
[MUIM_Objectmap_Remove](MUI_Objectmap.md/#MUIM_Objectmap_Remove), [MUIM_Objectmap_Find](MUI_Objectmap.md/#MUIM_Objectmap_Find), [MUIM_Objectmap_Iterate](MUI_Objectmap.md/#MUIM_Objectmap_Iterate)

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
