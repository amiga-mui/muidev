# Notify.mui
## Super class
rootclass
## Inherited by
* [Application.mui](MUI_Application)
* [Area.mui](MUI_Area)
* [Family.mui](MUI_Family)
* [Textdata.mui](MUI_Textdata)
* [Window.mui](MUI_Window)
## Background
Notify class is superclass of all other MUI classes. It's main purpose is to
handle MUI's notification mechanism, but it also contains some other methods
and attributes useful for every object.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_ApplicationObject](MUI_Notify.md/#MUIA_ApplicationObject)|V4|..G|`Object *`
[MUIA_AppMessage](MUI_Notify.md/#MUIA_AppMessage)|V5|..G|`struct AppMessage *`
[MUIA_HelpLine](MUI_Notify.md/#MUIA_HelpLine)|V4|ISG|`LONG`
[MUIA_HelpNode](MUI_Notify.md/#MUIA_HelpNode)|V4|ISG|`STRPTR`
[MUIA_NoNotify](MUI_Notify.md/#MUIA_NoNotify)|V7|.S.|`BOOL`
[MUIA_NoNotifyMethod](MUI_Notify.md/#MUIA_NoNotifyMethod)|V20|.S.|`ULONG`
[MUIA_ObjectID](MUI_Notify.md/#MUIA_ObjectID)|V11|ISG|`ULONG`
[MUIA_Parent](MUI_Notify.md/#MUIA_Parent)|V11|..G|`Object *`
[MUIA_Revision](MUI_Notify.md/#MUIA_Revision)|V4|..G|`LONG`
[MUIA_UserData](MUI_Notify.md/#MUIA_UserData)|V4|ISG|`ULONG`
[MUIA_Version](MUI_Notify.md/#MUIA_Version)|V4|..G|`LONG`

## Methods
Method|Version
------|-------
[MUIM_CallHook](MUI_Notify.md/#MUIM_CallHook)|V4
[MUIM_Export](MUI_Notify.md/#MUIM_Export)|V12
[MUIM_FindObject](MUI_Notify.md/#MUIM_FindObject)|V13
[MUIM_FindUData](MUI_Notify.md/#MUIM_FindUData)|V8
[MUIM_GetConfigItem](MUI_Notify.md/#MUIM_GetConfigItem)|V11
[MUIM_GetUData](MUI_Notify.md/#MUIM_GetUData)|V8
[MUIM_Import](MUI_Notify.md/#MUIM_Import)|V12
[MUIM_KillNotify](MUI_Notify.md/#MUIM_KillNotify)|V4
[MUIM_KillNotifyObj](MUI_Notify.md/#MUIM_KillNotifyObj)|V16
[MUIM_MultiSet](MUI_Notify.md/#MUIM_MultiSet)|V7
[MUIM_NoNotifySet](MUI_Notify.md/#MUIM_NoNotifySet)|V9
[MUIM_Notify](MUI_Notify.md/#MUIM_Notify)|V4
[MUIM_Set](MUI_Notify.md/#MUIM_Set)|V4
[MUIM_SetAsString](MUI_Notify.md/#MUIM_SetAsString)|V4
[MUIM_SetUData](MUI_Notify.md/#MUIM_SetUData)|V8
[MUIM_SetUDataOnce](MUI_Notify.md/#MUIM_SetUDataOnce)|V11
[MUIM_WriteLong](MUI_Notify.md/#MUIM_WriteLong)|V6
[MUIM_WriteString](MUI_Notify.md/#MUIM_WriteString)|V6

## MUIA_ApplicationObject
### NAME
[MUIA_ApplicationObject](MUI_Notify/#MUIA_ApplicationObject) -- V4 [..G], `Object *`, 0x8042d3ee

### FUNCTION
You can obtain a pointer to the application object that some gadget belongs
to by using this attribute. Useful mainly within callback hooks if you do
not want to deal with global variables.

If your object is not currently attached to an application, you will receive
NULL.

### SEE ALSO
[MUIA_WindowObject](MUI_Area/#MUIA_WindowObject)

## MUIA_AppMessage
### NAME
[MUIA_AppMessage](MUI_Notify/#MUIA_AppMessage) -- V5 [..G], `struct AppMessage *`, 0x80421955

### FUNCTION
When your window is an AppWindow, i.e. you have set the
[MUIA_Window_AppWindow](MUI_Window/#MUIA_Window_AppWindow) attribute to TRUE, you will be able to get AppMessages
by listening to [MUIA_AppMessage](MUI_Notify/#MUIA_AppMessage). Whenever an AppMessage arrives, this
attribute will be set to a pointer to that message.

[MUIA_AppMessage](MUI_Notify/#MUIA_AppMessage) is object specific. You can e.g. set up different
notifications for different objects in your window, they will only get
executed when icons are dropped over the specific object.

If you wait on [MUIA_AppMessage](MUI_Notify/#MUIA_AppMessage) with a window object, your notify will always
get executed when icons are dropped on the window.

### NOTES
- You should use the [MUIM_CallHook](MUI_Notify/#MUIM_CallHook) method to call a hook function when an
  AppMessage arrives (see below). The pointer to the AppMessage is valid
  only as long as the notification method is executed.

- AppWindows are only possible on the workench screen.

### EXAMPLE
```c++
/* Call the AppMsgHook when an icon is dropped on a listview */
DoMethod(lvobj, MUIM_Notify, MUIA_AppMessage, MUIV_EveryTime,
  lvobj, 3,
  MUIM_CallHook, &AppMsgHook, MUIV_TriggerValue);

/* Call the AppMsgHook when an icon is dropped on the window */
DoMethod(winobj, MUIM_Notify, MUIA_AppMessage, MUIV_EveryTime,
  winobj, 3,
  MUIM_CallHook, &AppMsgHook, MUIV_TriggerValue);
```

### SEE ALSO
[MUIA_Window_AppWindow](MUI_Window/#MUIA_Window_AppWindow), [MUIA_Application_DropObject](MUI_Application/#MUIA_Application_DropObject), [MUIM_CallHook](MUI_Notify/#MUIM_CallHook)

## MUIA_HelpLine
### NAME
[MUIA_HelpLine](MUI_Notify/#MUIA_HelpLine) -- V4 [ISG], `LONG`, 0x8042a825

### FUNCTION
Define a line in a help file specified with [MUIA_Application_HelpFile](MUI_Application/#MUIA_Application_HelpFile).

### SEE ALSO
[MUIA_Application_HelpFile](MUI_Application/#MUIA_Application_HelpFile), [MUIA_HelpNode](MUI_Notify/#MUIA_HelpNode)

## MUIA_HelpNode
### NAME
[MUIA_HelpNode](MUI_Notify/#MUIA_HelpNode) -- V4 [ISG], `STRPTR`, 0x80420b85

### FUNCTION
Define a node in a help file specified with [MUIA_Application_HelpFile](MUI_Application/#MUIA_Application_HelpFile).

### SEE ALSO
[MUIA_Application_HelpFile](MUI_Application/#MUIA_Application_HelpFile), [MUIA_HelpLine](MUI_Notify/#MUIA_HelpLine)

## MUIA_NoNotify
### NAME
[MUIA_NoNotify](MUI_Notify/#MUIA_NoNotify) -- V7 [.S.], `BOOL`, 0x804237f9

### FUNCTION
If you set up a notify on an attibute to react on user input, you will also
recognize events when you change this attribute under program control with
SetAttrs(). Setting [MUIA_NoNotify](MUI_Notify/#MUIA_NoNotify) together with your attribute will prevent
this notification from being triggered.

### NOTES
[MUIA_NoNotify](MUI_Notify/#MUIA_NoNotify) is a "one time" attribute. It is only valid during the current
SetAttrs() call!

### EXAMPLE
```c++
SetAttrs(slider,
  MUIA_NoNotify, TRUE,
  MUIA_Numeric_Value, 26,
  TAG_DONE);
```

## MUIA_NoNotifyMethod
### NAME
[MUIA_NoNotifyMethod](MUI_Notify/#MUIA_NoNotifyMethod) -- V20 [.S.], `ULONG`, 0x80420a74

### FUNCTION
Similar to settings [MUIA_NoNotify](MUI_Notify/#MUIA_NoNotify) to TRUE to avoid triggering notifications
for specific attributes setting this attribute to a specific method ID will
not trigger the corresponding method upon setting an attribute while all
other notifications will still be triggered.

### NOTES
[MUIA_NoNotifyMethod](MUI_Notify/#MUIA_NoNotifyMethod) is a "one time" attribute. It is only valid during the
current SetAttrs() call!

### EXAMPLE
```c++
/* set a slider's current level without triggering further MUIM_Set
   methods */
SetAttrs(slider,
  MUIA_NoNotifyMethod, MUIM_Set,
  MUIA_Numeric_Value, 26,
  TAG_DONE);
```

## MUIA_ObjectID
### NAME
[MUIA_ObjectID](MUI_Notify/#MUIA_ObjectID) -- V11 [ISG], `ULONG`, 0x8042d76e

### FUNCTION
Objects with a non NULL [MUIA_ObjectID](MUI_Notify/#MUIA_ObjectID) export their contents during
[MUIM_Application_Save](MUI_Application/#MUIM_Application_Save) and import them during [MUIM_Application_Load](MUI_Application/#MUIM_Application_Load).

You have to use different ObjectIDs for your objects!

### NOTES
This was previously called [MUIA_ExportID](MUI_Area/#MUIA_ExportID) and was placed in Area class
(muimaster.library V11 and below).

### SEE ALSO
[MUIM_Application_Save](MUI_Application/#MUIM_Application_Save), [MUIM_Application_Load](MUI_Application/#MUIM_Application_Load)

## MUIA_Parent
### NAME
[MUIA_Parent](MUI_Notify/#MUIA_Parent) -- V11 [..G], `Object *`, 0x8042e35f

### FUNCTION
Get a pointer to the parent object of the current object. The parent object
is always the group/family object which contains the current object. If an
object has no parent group, this attribute will be NULL.

### SEE ALSO
[MUIA_Group_Child](MUI_Group/#MUIA_Group_Child)

## MUIA_Revision
### NAME
[MUIA_Revision](MUI_Notify/#MUIA_Revision) -- V4 [..G], `LONG`, 0x80427eaa

### FUNCTION
Get the revision number of an objects class. Although [MUIA_Revision](MUI_Notify/#MUIA_Revision) is
documented at notify class, you will of course receive the revision number
of the object's true class.

### NOTES
Please note that if you are a MUI custom class developer you need to catch
the [MUIA_Version](MUI_Notify/#MUIA_Version)/Revision tag within a OM_GET method or otherwise your
object will probably return the wrong version/revision number.
It is also important that your class only return the version number if the
[MUIA_Version](MUI_Notify/#MUIA_Version)/Revision request had been directly performed on it. Therefore
you are recommended to use the following statements within your OM_GET
custom class method:

```c++
case MUIA_Version:
  if(OCLASS(obj) != cl) break;
  *store = VERSION;
  return(TRUE);

case MUIA_Revision:
  if(OCLASS(obj) != cl) break;
  *store = REVISION;
  return(TRUE);
```

### EXAMPLE
```c++
strobj = MUI_NewObject(MUIC_String, ... , TAG_DONE);
    ...
ULONG ver, rev;
get(strobj, MUIA_Version, &ver);
get(strobj, MUIA_Revision, &rev);
printf("String class version %ld.%ld\n", ver , rev);
```

### SEE ALSO
[MUIA_Version](MUI_Notify/#MUIA_Version)

## MUIA_UserData
### NAME
[MUIA_UserData](MUI_Notify/#MUIA_UserData) -- V4 [ISG], `ULONG`, 0x80420313

### FUNCTION
A general purpose value to fill in any kind of information.

## MUIA_Version
### NAME
[MUIA_Version](MUI_Notify/#MUIA_Version) -- V4 [..G], `LONG`, 0x80422301

### FUNCTION
Get the version number of an objects class. Although [MUIA_Version](MUI_Notify/#MUIA_Version) is
documented at notify class, you will of course receive the version number of
the object's true class.

### NOTES
Please note that if you are a MUI custom class developer you need to catch
the [MUIA_Version](MUI_Notify/#MUIA_Version)/Revision tag within a OM_GET method or otherwise your
object will probably return the wrong version/revision number.
It is also important that your class only return the version number if the
[MUIA_Version](MUI_Notify/#MUIA_Version)/Revision request had been directly performed on it. Therefore
you are recommended to use the following statements within your OM_GET
custom class method:

```c++
case MUIA_Version:
  if(OCLASS(obj) != cl) break;
  *store = VERSION;
  return(TRUE);

case MUIA_Revision:
  if(OCLASS(obj) != cl) break;
  *store = REVISION;
  return(TRUE);
```

### EXAMPLE
```c++
strobj = MUI_NewObject(MUIC_String, ... , TAG_DONE);
    ...
ULONG ver, rev;
get(strobj, MUIA_Version, &ver);
get(strobj, MUIA_Revision, &rev);
printf("String class version %ld.%ld\n", ver , rev);
```

### SEE ALSO
[MUIA_Revision](MUI_Notify/#MUIA_Revision)

## MUIM_CallHook
### NAME
[MUIM_CallHook](MUI_Notify/#MUIM_CallHook) -- V4, 0x8042b96b

### SYNOPSIS
`DoMethod(obj, MUIM_CallHook, struct Hook *Hook, ULONG param1, /* ... */);`

### FUNCTION
Call a standard amiga callback hook, defined by a Hook structure. Together
with [MUIM_Notify](MUI_Notify/#MUIM_Notify), you can easily bind hooks to buttons, your hook will be
called when the button is pressed.

The hook will be called with a pointer to the hook structure in A0, a
pointer to the calling object in A2 and a pointer to the first parameter in
A1.

### INPUTS
**`struct Hook *Hook`**
     pointer to a struct Hook.

**`ULONG param1`**
     zero or more parameters. The hook function will receive a pointer
     to the first parameter in register A1.

### RESULT
return - the value returned by the hook function (V20.2291+)

### EXAMPLE
standalone:

```c++
DoMethod(obj, MUIM_CallHook, &hookstruct, 13, 42, "foobar", "barfoo");
```

within a notification statement:

```c++
DoMethod(propobj, MUIM_Notify, MUIA_Prop_First, MUIV_EveryTime,
  propobj, 3,
  MUIM_CallHook, prophook, MUIV_TriggerValue);
```

prophook will be called every time the knob is moving and gets a pointer to
the knob's current level in A1.

## MUIM_Export
### NAME
[MUIM_Export](MUI_Notify/#MUIM_Export) -- V12, 0x80420f1c

### SYNOPSIS
`DoMethod(obj, MUIM_Export, Object *dataspace);`

### FUNCTION
This method is called for each object in the application tree (including
menus) during execution of [MUIM_Application_Save](MUI_Application/#MUIM_Application_Save). Its purpose is to export
an object's "contents" to a dataspace object for later saving to an IFF file.

If you override this method to export your custom data, you are supposed to
use your [MUIA_ObjectID](MUI_Notify/#MUIA_ObjectID) as ID for the dataspace entry. Don't export if your
[MUIA_ObjectID](MUI_Notify/#MUIA_ObjectID) is 0.

### INPUTS
**`Object *dataspace`**
     Dataspace object to export the data to.

### RESULT
Return 0 if you don't want your superclasses to be able to import/export any
values themselves. Otherwise return DoSuperMethodA(cl, obj, msg);

### EXAMPLE
```c++
ULONG mExport(struct IClass *cl, Object *obj, struct MUIP_Export *msg)
{
  struct Data *mydata = INST_DATA(cl,obj);
  ULONG id;
  ULONG exp=0;

  if((id = (muiNotifyData(obj)->mnd_ObjectID)) != 0)
  {
    DoMethod(msg->dataspace, MUIM_Dataspace_Add, &mydata->myvalue, sizeof(LONG), id);
  }

  return(0);
}
```

### SEE ALSO
[MUIM_Import](MUI_Notify/#MUIM_Import), [MUIM_Application_Load](MUI_Application/#MUIM_Application_Load), [MUIM_Application_Save](MUI_Application/#MUIM_Application_Save)

## MUIM_FindObject
### NAME
[MUIM_FindObject](MUI_Notify/#MUIM_FindObject) -- V13, 0x8042038f

### SYNOPSIS
`DoMethod(obj, MUIM_FindObject, Object *findme);`

### FUNCTION
This method checks if the given object is still contained in the object tree
of the calling object. In case the object is not found FALSE will be
returned, TRUE otherwise.

### INPUTS
**`Object *findme`**
     pointer to an object to be searched.

### SEE ALSO
[MUIA_Parent](MUI_Notify/#MUIA_Parent)

## MUIM_FindUData
### NAME
[MUIM_FindUData](MUI_Notify/#MUIM_FindUData) -- V8, 0x8042c196

### SYNOPSIS
`DoMethod(obj, MUIM_FindUData, ULONG udata);`

### FUNCTION
This method tests if the [MUIA_UserData](MUI_Notify/#MUIA_UserData) of the object contains the given
<udata> and returns the object pointer in this case.

Although this is not very useful for single objects, performing this method
on objects that handle children can become very handy. In this case, all the
children (any maybe their children) are tested against <udata> and the first
matching object is returned.

This method is especially useful if you created your menu tree with a
NewMenu structure and you want to find the object pointer for a single menu
item.

### INPUTS
**`ULONG udata`**
     userdata to look for.

### RESULT
A pointer to the first object with the specified user data or NULL if no
object is found.

### NOTES
If you have many objects in your application, [MUIM_FindUData](MUI_Notify/#MUIM_FindUData) may take quite
long. You can limit the amount of time by performing the method not on the
application but on the window or even on the group/family your object is
placed in.

### SEE ALSO
[MUIM_GetUData](MUI_Notify/#MUIM_GetUData), [MUIM_SetUData](MUI_Notify/#MUIM_SetUData)

## MUIM_GetConfigItem
### NAME
[MUIM_GetConfigItem](MUI_Notify/#MUIM_GetConfigItem) -- V11, 0x80423edb

### SYNOPSIS
`DoMethod(obj, MUIM_GetConfigItem, ULONG id, ULONG *storage);`

### FUNCTION
This method obtains the given configuration item from the object's local
configuration.

Currently MUICFG_PublicScreen (ID 0x24) is the only publically available
item.

### INPUTS
**`ULONG id`**
     configuration item ID.

**`ULONG *storage`**
     place to store the configuration item.

## MUIM_GetUData
### NAME
[MUIM_GetUData](MUI_Notify/#MUIM_GetUData) -- V8, 0x8042ed0c

### SYNOPSIS
`DoMethod(obj, MUIM_GetUData, ULONG udata, ULONG attr, ULONG *storage);`

### FUNCTION
This method tests if the [MUIA_UserData](MUI_Notify/#MUIA_UserData) of the object contains the given
<udata> and gets <attr> to <storage> for itself in this case.

Although this is not very useful for single objects, performing this method
on objects that handle children can become very handy. In this case, all the
children (any maybe their children) are searched against <udata> and the
first matching object will be asked for the specified attribute.

### INPUTS
**`ULONG udata`**
     userdata to look for.

**`ULONG attr`**
     attribute to get.

**`ULONG *storage`**
     place to store the attribute.

### NOTES
If you have many objects in your application, [MUIM_GetUData](MUI_Notify/#MUIM_GetUData) may take quite
long. You can limit the amount of time by performing the method not on the
application but on the window or even on the group/family your objects are
placed in.

### SEE ALSO
[MUIM_SetUData](MUI_Notify/#MUIM_SetUData), [MUIM_FindUData](MUI_Notify/#MUIM_FindUData)

## MUIM_Import
### NAME
[MUIM_Import](MUI_Notify/#MUIM_Import) -- V12, 0x8042d012

### SYNOPSIS
`DoMethod(obj, MUIM_Import, Object *dataspace);`

### FUNCTION
This method is called for each object in the application tree (including
menus) during execution of [MUIM_Application_Load](MUI_Application/#MUIM_Application_Load). Its purpose is to import
an object's "contents" from a dataspace object after loading from an IFF
file.

If you override this method to import your custom data, you are supposed to
use your [MUIA_ObjectID](MUI_Notify/#MUIA_ObjectID) as ID for the dataspace entry. Don't import if your
[MUIA_ObjectID](MUI_Notify/#MUIA_ObjectID) is 0.

### INPUTS
**`Object *dataspace`**
     Dataspace object to import the data from.

### RESULT
Return 0 if you don't want your superclasses to be able to import/export any
values themselves. Otherwise return(DoSuperMethodA(cl,obj,msg));

### EXAMPLE
```c++
ULONG mImport(struct IClass *cl, Object *obj, struct MUIP_Import *msg)
{
  struct Data *mydata = INST_DATA(cl, obj);
  ULONG id;
  ULONG *data;

  if((id = (muiNotifyData(obj)->mnd_ObjectID)) != 0)
  {
     if((data = (ULONG *)DoMethod(msg->dataspace, MUIM_Dataspace_Find, id)) != NULL)
       mydata->myvalue = *data;
  }

  return(0);
}
```

### SEE ALSO
[MUIM_Import](MUI_Notify/#MUIM_Import), [MUIM_Application_Load](MUI_Application/#MUIM_Application_Load), [MUIM_Application_Save](MUI_Application/#MUIM_Application_Save)

## MUIM_KillNotify
### NAME
[MUIM_KillNotify](MUI_Notify/#MUIM_KillNotify) -- V4, 0x8042d240

### SYNOPSIS
`DoMethod(obj, MUIM_KillNotify, ULONG TrigAttr);`

### FUNCTION
[MUIM_KillNotify](MUI_Notify/#MUIM_KillNotify) kills previously given notifications on specific attributes.

### INPUTS
**`ULONG TrigAttr`**
     attribute for which the notify was specified. If you set up more
     than one notify for an attribute, only the first one will be
     killed.

### EXAMPLE
```c++
DoMethod(button, MUIM_KillNotify, MUIA_Pressed);
```

### SEE ALSO
[MUIM_Notify](MUI_Notify/#MUIM_Notify)

## MUIM_KillNotifyObj
### NAME
[MUIM_KillNotifyObj](MUI_Notify/#MUIM_KillNotifyObj) -- V16, 0x8042b145

### SYNOPSIS
`DoMethod(obj, MUIM_KillNotifyObj, ULONG TrigAttr, Object *dest);`

### FUNCTION
Similar to [MUIM_KillNotify](MUI_Notify/#MUIM_KillNotify) this method kills previously given notifications
on specific attributes, but only for a specific destination object.

### INPUTS
**`ULONG TrigAttr`**
     attribute for which the notify was specified. If you set up more
     than one notify for an attribute, only the first one will be
     killed.

**`Object *dest`**
     kill the notifications for this single destination object only.

### EXAMPLE
```c++
DoMethod(button, MUIM_KillNotifyObj, MUIA_Pressed, otherbutton);
```

### SEE ALSO
[MUIM_KillNotify](MUI_Notify/#MUIM_KillNotify)

## MUIM_MultiSet
### NAME
[MUIM_MultiSet](MUI_Notify/#MUIM_MultiSet) -- V7, 0x8042d356

### SYNOPSIS
`DoMethod(obj, MUIM_MultiSet, ULONG attr, ULONG val, Object *obj, /* ... */);`

### FUNCTION
Set an attribute for multiple objects. Receiving an attribute/value pair and
a list of objects, this method sets the new value for all the objects in the
list. This is especially useful for disabling/enabling lots of objects with
one singe function call.

The object that executes this method isn't affected!

Note: This method was implemented in version 7 of notify class.

### INPUTS
**`ULONG attr`**
     attribute to set.

**`ULONG val`**
     new value for the attribute.

**`APTR obj, ...`**
     list of MUI objects, terminated with a NULL pointer.

### EXAMPLE
```c++
/* disable all the address related gadgets... */
DoMethod(xxx, MUIM_MultiSet, MUIA_Disabled, TRUE,
  ST_Name, ST_Street, ST_City, ST_Country, ST_Phone, NULL);
/* note that the xxx object doesn't get disabled! */
```

### SEE ALSO
[MUIM_Set](MUI_Notify/#MUIM_Set), [MUIM_Notify](MUI_Notify/#MUIM_Notify)

## MUIM_NoNotifySet
### NAME
[MUIM_NoNotifySet](MUI_Notify/#MUIM_NoNotifySet) -- V9, 0x8042216f

### SYNOPSIS
`DoMethod(obj, MUIM_NoNotifySet, ULONG attr, ULONG val, /* ... */);`

### FUNCTION
Acts like [MUIM_Set](MUI_Notify/#MUIM_Set) but doesn't trigger any notification. This can become
useful to avoid deadlocks with bi-directional connections.

### INPUTS
**`ULONG attr`**
     attribute you want to set.

**`ULONG val, ...`**
     value to set the attribute to.

EXMAPLE
```c++
DoMethod(editor, MUIM_Notify, EDIT_Top, MUIV_EveryTime,
  sbar, 3,
  MUIM_NoNotifySet, MUIA_Prop_First, MUIV_TriggerValue);

DoMethod(sbar, MUIM_Notify, MUIA_Prop_First, MUIV_EveryTime,
  editor, 3,
  MUIM_NoNotifySet, EDIT_Top, MUIV_TriggerValue);
```

### SEE ALSO
[MUIM_Set](MUI_Notify/#MUIM_Set)

## MUIM_Notify
### NAME
[MUIM_Notify](MUI_Notify/#MUIM_Notify) -- V4, 0x8042c9cb

### SYNOPSIS
`DoMethod(obj, MUIM_Notify, ULONG TrigAttr, ULONG TrigVal, Object *DestObj, ULONG FollowParams, /* ... */);`

### FUNCTION
Add a notification event handler to an object. Notification is essential for
every MUI application.

A notification statement consists of a source object, an attribute/value
pair, a destination object and a notification method. The attribute/value
pair belongs to the source object and determines when the notification
method will be executed on the destination object.

Whenever the source object gets the given attribute set to the given value
(this can happen because of the user pressing some gadgets or because of
your program explicitly setting the attribute with SetAttrs()), the
destination object will execute the notification method.

With some special values, you can trigger the notification every time the
attribute is changing. In this case, you can include the triggering
attribute's value within the notification method. See below.

One big problem with notifications are endless loops. Imagine you have a prop
gadget and want to show its state with a gauge object. You connect
[MUIA_Prop_First](MUI_Prop/#MUIA_Prop_First) with [MUIA_Gauge_Max](MUI_Gauge/#MUIA_Gauge_Max) and everything is fine, the gauge gets
updated when the user drags around the gadget. On the other hand, if your
program sets the gauge to a new value, you might want your prop gadget to
immediately show this change and connect [MUIA_Gauge_Max](MUI_Gauge/#MUIA_Gauge_Max) width
[MUIA_Prop_First](MUI_Prop/#MUIA_Prop_First). Voila, a perfect endless loop.

To avoid these conditions, MUI always checks new attribute values against
the current state and cancels notification when both values are equal. Thus,
setting [MUIA_Prop_First](MUI_Prop/#MUIA_Prop_First) to 42 if the prop gadgets first position is already
42 won't trigger any notification event.

### INPUTS
**`ULONG TrigAttr`**
     attribute that triggers the notification.

**`ULONG TrigVal`**
     value that triggers the notification. The special value
     MUIV_EveryTime makes MUI execute the notification method every
     time when TrigAttr changes. In this case, the special value
     MUIV_TriggerValue in the notification method will be replaced
     with the value that TrigAttr has been set to. You can use
     MUIV_TriggerValue up to four times in one notification method.
     Since version 8 of muimaster.library, you can also use
     MUIV_NotTriggerValue here. In this case, MUI will replace TRUE
     values with FALSE and FALSE values with TRUE. This can become
     quite useful when you try to set "negative" attributes like
     [MUIA_Disabled](MUI_Area/#MUIA_Disabled).

**`Object *DestObj`**
     object on which to perform the notification method. Either
     supply a valid object pointer or one of the following special
     values (V10) which will be resolved at the time the event
     occurs:
       * MUIV_Notify_Self: notifies the object itself.
       * MUIV_Notify_Window : notifies the object's parent window.
       * MUIV_Notify_Application: notifies the object's application.
       * MUIV_Notify_Parent (V20): notifies the object's direct parent object.
       * MUIV_Notify_ParentParent (V20): notifies the object's grandparent object.
       * MUIV_Notify_ParentParentParent (V20): notifies the object's
         great-grandparent object.

 ULONG FollowParams
 of following parameters. If you e.g. have a notification method
 with three parts (maybe [MUIM_Set](MUI_Notify/#MUIM_Set), attr, val), you have to set
 FollowParams to 3. This allows MUI to copy the complete
 notification method into a private buffer for later use.

**`...`**
     following is the notification method.

### EXAMPLE
```c++
/*
** Every time when the user releases a button
** (and the mouse is still over it), the button object
** gets its MUIA_Pressed attribute set to FALSE.
** Thats what a program can react on with notification,
** e.g. by openening another window.
*/

DoMethod(buttonobj, MUIM_Notify,
  MUIA_Pressed, FALSE,                /* attribute/value pair */
  windowobj,                          /* destination object   */
  3,                                  /* 3 following words    */
  MUIM_Set, MUIA_Window_Open, TRUE);  /* notification method  */

/*
** Lets say we want to show the current value of a
** prop gadget somewhere in a text field:
*/

DoMethod(propobj,MUIM_Notify,      /* notification is triggered   */
  MUIA_Prop_First, MUIV_EveryTime, /* every time the attr changes */
  textobj,                         /* destination object */
  4,                               /* 4 following words  */
  MUIM_SetAsString, MUIA_Text_Contents,
  "value is %ld !", MUIV_TriggerValue);
  /* MUIV_TriggerValue will be replaced with the
     current value of MUIA_Prop_First */

/*
** Inform our application when the user hits return
** in a string gadget:
*/

DoMethod(stringobj, MUIM_Notify, MUIA_String_Acknowledge, MUIV_EveryTime,
   MUIV_Notify_Application, 2,
   MUIM_Application_ReturnID, ID_FOOBAR);
```

## MUIM_Set
### NAME
[MUIM_Set](MUI_Notify/#MUIM_Set) -- V4, 0x8042549a

### SYNOPSIS
`DoMethod(obj, MUIM_Set, ULONG attr, ULONG val);`

### FUNCTION
Set an attribute to a value. Normally, you would set attributes with
intuition.library SetAttrs() or with the OM_SET method as with any other
BOOPSI objects. But since these calls need a complete tag list, not just a
single attribute/value pair, they are not useful within a [MUIM_Notify](MUI_Notify/#MUIM_Notify)
method.

### INPUTS
**`ULONG attr`**
     attribute you want to set.

**`ULONG val, ...`**
     value to set the attribute to.

EXMAPLE
```c++
DoMethod(strobj, MUIM_Set, MUIA_String_Contents, "foobar");
```
and
```c++
SetAttrs(strobj, MUIA_String_Contents, "foobar", TAG_DONE);
```
are equal.

### SEE ALSO
[MUIM_SetAsString](MUI_Notify/#MUIM_SetAsString), [MUIM_Notify](MUI_Notify/#MUIM_Notify), [MUIM_NoNotifySet](MUI_Notify/#MUIM_NoNotifySet)

## MUIM_SetAsString
### NAME
[MUIM_SetAsString](MUI_Notify/#MUIM_SetAsString) -- V4, 0x80422590

### SYNOPSIS
`DoMethod(obj, MUIM_SetAsString, ULONG attr, CONST_STRPTR format, ULONG val, /* ... */);`

### FUNCTION
Set a (text kind) attribute to a string. This can be useful if you want to
connect a numeric attribute of an object with a text attribute of another
object.

### INPUTS
**`ULONG attr`**
     attribute to set.

**`CONST_STRPTR format`**
     C like formatting string, remember to use "%ld"!

**`ULONG val, ...`**
     one or more parameters for the format string.

### NOTES
The resulting string must not exceed 1024 characters. You can pass a maximum
of 8 arguments. More are ignored.

### EXAMPLE
stand alone:

```c++
DoMethod(txobj, MUIM_SetAsString, MUIA_Text_Contents,
  "My name is %s and I am %ld years old.", name, age);
```

within a notification statement:

```c++
DoMethod(propobj, MUIM_Notify, MUIA_Prop_First, MUIV_EveryTime,
  txobj, 4,
  MUIM_SetAsString, MUIA_Text_Contents, "prop gadget shows %ld.", MUIV_TriggerValue);
```

### SEE ALSO
[MUIM_Set](MUI_Notify/#MUIM_Set), [MUIM_Notify](MUI_Notify/#MUIM_Notify)

## MUIM_SetUData
### NAME
[MUIM_SetUData](MUI_Notify/#MUIM_SetUData) -- V8, 0x8042c920

### SYNOPSIS
`DoMethod(obj, MUIM_SetUData, ULONG udata, ULONG attr, ULONG val);`

### FUNCTION
This method tests if the [MUIA_UserData](MUI_Notify/#MUIA_UserData) of the object contains the given
<udata> and sets <attr> to <val> for itself in this case.

Altough this is not very useful for single objects, performing this method
on objects that handle children can become very handy. In this case, all the
children (any maybe their children) are tested against <udata> and all
matching objects will get the attribute set.

If you e.g. want to clear several string gadgets in your applciation at
once, you simply give them the same [MUIA_UserData](MUI_Notify/#MUIA_UserData) and use

```c++
DoMethod(app, MUIM_SetUData, MyUDATA, MUIA_String_Contents, NULL);
```

### INPUTS
**`ULONG udata`**
     userdata to look for.

**`ULONG attr`**
     attribute to set.

**`ULONG val`**
     value to set attribute to.

### NOTES
If you have many objects in your application, [MUIM_SetUData](MUI_Notify/#MUIM_SetUData) may take quite
long. You can limit the amount of time by performing the method not on the
application but on the window or even on the group your gadgets are place
in.

### SEE ALSO
[MUIM_GetUData](MUI_Notify/#MUIM_GetUData), [MUIM_FindUData](MUI_Notify/#MUIM_FindUData), [MUIM_SetUDataOnce](MUI_Notify/#MUIM_SetUDataOnce)

## MUIM_SetUDataOnce
### NAME
[MUIM_SetUDataOnce](MUI_Notify/#MUIM_SetUDataOnce) -- V11, 0x8042ca19

### SYNOPSIS
`DoMethod(obj, MUIM_SetUDataOnce, ULONG udata, ULONG attr, ULONG val);`

### FUNCTION
This method performs like [MUIM_SetUData](MUI_Notify/#MUIM_SetUData), but stops when it has found an
object with the given user data. If you don't have objects with equal user
datas and don't rely on setting all of them, [MUIM_SetUDataOnce](MUI_Notify/#MUIM_SetUDataOnce) is
preferrable because it's more efficient.

### INPUTS
**`ULONG udata`**
     userdata to look for.

**`ULONG attr`**
     attribute to set.

**`ULONG val`**
     value to set attribute to.

### SEE ALSO
[MUIM_SetUData](MUI_Notify/#MUIM_SetUData), [MUIM_GetUData](MUI_Notify/#MUIM_GetUData)


## MUIM_WriteLong
### NAME
[MUIM_WriteLong](MUI_Notify/#MUIM_WriteLong) -- V6, 0x80428d86

### SYNOPSIS
`DoMethod(obj, MUIM_WriteLong, ULONG val, ULONG *memory);`

### FUNCTION
This method simply writes a longword somewhere to memory. Although this
seems quite useless, it might become handy if used within a notify
statement. For instance, you could easily connect the current level of a
slider with some member of your program's data structures.

### INPUTS
**`ULONG val`**
     value to write.

**`ULONG *memory`**
     location to write the value to.

### EXAMPLE
```c++
/* Let the slider automagically write its level to a variable */
static LONG level;

DoMethod(slider, MUIM_Notify, MUIA_Numeric_Value, MUIV_EveryTime,
  slider, 3,
  MUIM_WriteLong, MUIV_TriggerValue, &level);
```

### SEE ALSO
[MUIM_WriteString](MUI_Notify/#MUIM_WriteString), [MUIM_Notify](MUI_Notify/#MUIM_Notify)

## MUIM_WriteString
### NAME
[MUIM_WriteString](MUI_Notify/#MUIM_WriteString) -- V6, 0x80424bf4

### SYNOPSIS
`DoMethod(obj, MUIM_WriteString, CONST_STRPTR str, STRPTR memory);`

### FUNCTION
This method simply copies a string somewhere to memory. Although this seems
quite useless, it might become handy if used within a notify statement. For
instance, you could easily connect the current contents of a string gadget
with some member of your programs data structures.

Note: The string is copied with strcpy(), you must assure that the
destination points to enough memory.

### INPUTS
**`CONST_STRPTR str`**
     string to copy.

 STRPTR memorystr:
 location to write the value to.

### EXAMPLE
```c++
static char buffer[256];

DoMethod(string, MUIM_Notify, MUIA_String_Contents, MUIV_EveryTime,
  string, 3,
  MUIM_WriteString, MUIV_TriggerValue, buffer);
```

### SEE ALSO
[MUIM_WriteLong](MUI_Notify/#MUIM_WriteLong), [MUIM_Notify](MUI_Notify/#MUIM_Notify)

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
