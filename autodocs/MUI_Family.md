# Family.mui
## Super class
[Notify.mui](MUI_Notify.md)
## Inherited by
* [Menu.mui](MUI_Menu.md)
* [Menuitem.mui](MUI_Menuitem.md)
* [Menustrip.mui](MUI_Menustrip.md)
## Background
Family class is the base class for objects that are able to handle a list of
children. This is e.g. the case for MUIs Menustrip, Menu and Menuitem
objects.

Family class defines methods and attributes to add and remove children, sort
children, and transfer children to other Family objects.

Group class and application class should also be a subclass of Family class,
but due to BOOPSI system limitations, this is currently impossible. If the
future will allow more logical class trees, things might change, but
everything will be done in a compatible manner.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)|V8|I..|`Object *`
[MUIA_Family_ChildCount](MUI_Family.md/#MUIA_Family_ChildCount)|V20|..G|`LONG`
[MUIA_Family_List](MUI_Family.md/#MUIA_Family_List)|V8|..G|`struct MinList *`

## Methods
Method|Version
------|-------
[MUIM_Family_AddHead](MUI_Family.md/#MUIM_Family_AddHead)|V8
[MUIM_Family_AddTail](MUI_Family.md/#MUIM_Family_AddTail)|V8
[MUIM_Family_DoChildMethods](MUI_Family.md/#MUIM_Family_DoChildMethods)|V20
[MUIM_Family_GetChild](MUI_Family.md/#MUIM_Family_GetChild)|V20
[MUIM_Family_Insert](MUI_Family.md/#MUIM_Family_Insert)|V8
[MUIM_Family_Remove](MUI_Family.md/#MUIM_Family_Remove)|V8
[MUIM_Family_Reorder](MUI_Family.md/#MUIM_Family_Reorder)|V21
[MUIM_Family_Sort](MUI_Family.md/#MUIM_Family_Sort)|V8
[MUIM_Family_Transfer](MUI_Family.md/#MUIM_Family_Transfer)|V8

## MUIA_Family_Child
### NAME
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child) -- V8 [I..], `Object *`, 0x8042c696

### FUNCTION
You supply a pointer to a previously created MUI object here. This object
will be added to family at family creation time.

Of course you can specify any number of child objects, limited only by
available memory.

Normally, the value for a [MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child) tag is a direct call to another
MUI_NewObject(), children are generated "on the fly".

When a family is disposed, all of its children will also get deleted. If you
supply a NULL pointer as child, the family object will fail and previously
dispose all valid children found in the taglist.

This behaviour makes it possible to generate a complete family within one
single (but long) MUI_NewObject() call. Error checking is not necessary
since every error, even if it occurs in a very deep nesting level, will
cause the complete call to fail without leaving back any previously created
object.

### NOTES
As a special case, [MUIA_Group_Child](MUI_Group.md/#MUIA_Group_Child) is also recognized and treated as
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child).

### SEE ALSO
[MUIM_Family_AddTail](MUI_Family.md/#MUIM_Family_AddTail), [MUIM_Family_Insert](MUI_Family.md/#MUIM_Family_Insert), [MUIM_Family_AddHead](MUI_Family.md/#MUIM_Family_AddHead),
[MUIA_Family_Remove](MUI_Family.md/#MUIA_Family_Remove)

## MUIA_Family_ChildCount
### NAME
[MUIA_Family_ChildCount](MUI_Family.md/#MUIA_Family_ChildCount) -- V20 [..G], `LONG`, 0x8042b25a

### FUNCTION
Returns the number of family members of a family object.

### SEE ALSO
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)

## MUIA_Family_List
### NAME
[MUIA_Family_List](MUI_Family.md/#MUIA_Family_List) -- V8 [..G], `struct MinList *`, 0x80424b9e

### FUNCTION
Returns a pointer to a struct MinList which contains the children of a
family object. You must parse this list with intuition.library/NextObject().

### SEE ALSO
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)

## MUIM_Family_AddHead
### NAME
[MUIM_Family_AddHead](MUI_Family.md/#MUIM_Family_AddHead) -- V8, 0x8042e200

### SYNOPSIS
`DoMethod(obj, MUIM_Family_AddHead, Object *obj);`

### FUNCTION
Add an object as first object to the family. Subclasses of Family class
usually define which types of objects are possible within their family.

### INPUTS
**`Object *obj`**
     the object to be added.

### SEE ALSO
[MUIM_Family_AddTail](MUI_Family.md/#MUIM_Family_AddTail), [MUIM_Family_Insert](MUI_Family.md/#MUIM_Family_Insert), [MUIM_Family_Remove](MUI_Family.md/#MUIM_Family_Remove),
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)

## MUIM_Family_AddTail
### NAME
[MUIM_Family_AddTail](MUI_Family.md/#MUIM_Family_AddTail) -- V8, 0x8042d752

### SYNOPSIS
`DoMethod(obj, MUIM_Family_AddTail, Object *obj);`

### FUNCTION
Add an object as last object to the family. Subclasses of Family class
usually define which types of objects are possible within their family.

This method does the same as OM_ADDMEMBER.

### INPUTS
**`Object *obj`**
     the object to be added.

### SEE ALSO
[MUIM_Family_AddHead](MUI_Family.md/#MUIM_Family_AddHead), [MUIM_Family_Insert](MUI_Family.md/#MUIM_Family_Insert), [MUIM_Family_Remove](MUI_Family.md/#MUIM_Family_Remove),
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)

## MUIM_Family_DoChildMethods
### NAME
[MUIM_Family_DoChildMethods](MUI_Family.md/#MUIM_Family_DoChildMethods) -- V20, 0x80429a3c

### SYNOPSIS
`DoMethod(obj, MUIM_Family_DoChildMethods, /* ... */);`

### FUNCTION
Invoke a method on all children of a family.

### INPUTS
**`...`**
     the destination method.

### SEE ALSO
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)

## MUIM_Family_GetChild
### NAME
[MUIM_Family_GetChild](MUI_Family.md/#MUIM_Family_GetChild) -- V20, 0x8042c556

### SYNOPSIS
`DoMethod(obj, MUIM_Family_GetChild, LONG nr, Object *ref);`

### FUNCTION
Obtain a child a family.

### INPUTS
**`LONG nr`**
     number of the child to be returned.

**`Object *ref`**
     reference pointer from previous call.

Either use a valid index number or one of these special values:

**`MUIV_Family_GetChild_First`**
     Return the first child of the family.

**`MUIV_Family_GetChild_Last`**
     Return the last child of the family.

**`MUIV_Family_GetChild_Next`**
     Return the next child of the family in respect to the given reference
     child. Will fall back to the first child if the reference pointer is
     NULL.

**`MUIV_Family_GetChild_Previous`**
     Return the previous child of the family in respect to the given reference
     child. Will fall back to the last child if the reference pointer is NULL.

**`MUIV_Family_GetChild_Iterate`**
     Iterate over the list of children. The reference object must point to an
     array of 32bit entries of which the first entry carries the byte size of
     the whole array. Successive calls of [MUIM_Family_GetChild](MUI_Family.md/#MUIM_Family_GetChild) will then
     return the single family childs.

### EXAMPLE
```c++
Object *child;
/* obtain the first child a family */
child = (Object *)DoMethod(family, MUIM_Family_GetChild, MUIV_Family_GetChild_First);
/* obtain the forth child a family */
child = (Object *)DoMethod(family, MUIM_Family_GetChild, 3);
/* iterate over all children of a family */
LONG ref[20] = { sizeof(ref) };
for(child = NULL; (child = (Object *)DoMethod(family, MUIM_Family_GetChild, MUIV_Family_GetChild_Iterate, ref)) != NULL; )
{
  /* take care of the child */
}
```

### SEE ALSO
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)

## MUIM_Family_Insert
### NAME
[MUIM_Family_Insert](MUI_Family.md/#MUIM_Family_Insert) -- V8, 0x80424d34

### SYNOPSIS
`DoMethod(obj, MUIM_Family_Insert, Object *obj, Object *pred);`

### FUNCTION
Add an object after another object to the family. Subclasses of Family class
usually define which types of objects are possible within their family.

### INPUTS
**`Object *obj`**
     the object to be added.

**`Object *pred`**
     the new object is inserted **after** this object. pred must of course
     be a member of the family.

### SEE ALSO
[MUIM_Family_AddTail](MUI_Family.md/#MUIM_Family_AddTail), [MUIM_Family_AddHead](MUI_Family.md/#MUIM_Family_AddHead), [MUIM_Family_Remove](MUI_Family.md/#MUIM_Family_Remove),
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)

## MUIM_Family_Remove
### NAME
[MUIM_Family_Remove](MUI_Family.md/#MUIM_Family_Remove) -- V8, 0x8042f8a9

### SYNOPSIS
`DoMethod(obj, MUIM_Family_Remove, Object *obj);`

### FUNCTION
Remove an object from a family.

This method does the same as OM_REMMEMBER.

### INPUTS
**`Object *obj`**
     the object to be removed.

### SEE ALSO
[MUIM_Family_AddTail](MUI_Family.md/#MUIM_Family_AddTail), [MUIM_Family_Insert](MUI_Family.md/#MUIM_Family_Insert), [MUIM_Family_AddHead](MUI_Family.md/#MUIM_Family_AddHead),
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)

## MUIM_Family_Reorder
### NAME
[MUIM_Family_Reorder](MUI_Family.md/#MUIM_Family_Reorder) -- V21, 0x80426008

### SYNOPSIS
`DoMethod(obj, MUIM_Family_Reorder, Object *after, Object *array[1]);`

### FUNCTION
Reorder the children of a family.

### INPUTS
 Object *after
 the object to reorder the children after. Special values are
   * 0:  reorder the objects at the front of the Family object's child list
   * -1: reorder the objects at the end of the Family object's child list

**`Object *array[1]`**
     a NULL terminated array of objects to be reordered.

### EXAMPLE
```c++
// move child1, child2 and child3 to the front
DoMethod(family, MUIM_Family_Reorder, NULL, child1, child2, child3, NULL);
```

### SEE ALSO
[MUIM_Family_Sort](MUI_Family.md/#MUIM_Family_Sort)

## MUIM_Family_Sort
### NAME
[MUIM_Family_Sort](MUI_Family.md/#MUIM_Family_Sort) -- V8, 0x80421c49

### SYNOPSIS
`DoMethod(obj, MUIM_Family_Sort, Object *obj[1]);`

### FUNCTION
Sort the children of a family.

### INPUTS
**`Object *obj[1]`**
     array that contains **all** the children of the family in the desired
     order. The array must be terminated with a NULL entry.

### SEE ALSO
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)

## MUIM_Family_Transfer
### NAME
[MUIM_Family_Transfer](MUI_Family.md/#MUIM_Family_Transfer) -- V8, 0x8042c14a

### SYNOPSIS
`DoMethod(obj, MUIM_Family_Transfer, Object *family);`

### FUNCTION
All the children of the family are removed and added to another family in
the same order.

### INPUTS
**`Object *family`**
     the destination family.

### SEE ALSO
[MUIA_Family_Child](MUI_Family.md/#MUIA_Family_Child)

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
