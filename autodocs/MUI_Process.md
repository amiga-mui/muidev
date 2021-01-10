# Process.mui
## Super class
[Semaphore.mui](MUI_Semaphore)
## Inherited by
* [Slave.mui](MUI_Slave)
## Background
Process class simplifies the creation of subtasks to execute stuff in
parallel to the rest of the application. Typically a process object is
'embedded' into a class instead of being subclassed. See Class4 demo for
details.

Note: a subprocess must **NOT** invoke any method of any of the application's
objects. All methods must be pushed onto the application's method stack by
invoking [MUIM_Application_PushMethod](MUI_Application/#MUIM_Application_PushMethod). Already pushed methods can be unpushed
using [MUIM_Application_UnpushMethod](MUI_Application/#MUIM_Application_UnpushMethod) in case it might be possible that the
pushed method may be executed after the destination object has been
disposed.
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Process_AutoLaunch](MUI_Process.md/#MUIA_Process_AutoLaunch)|V20|I..|`ULONG`
[MUIA_Process_Name](MUI_Process.md/#MUIA_Process_Name)|V20|I..|`ULONG`
[MUIA_Process_Priority](MUI_Process.md/#MUIA_Process_Priority)|V20|I..|`ULONG`
[MUIA_Process_SourceClass](MUI_Process.md/#MUIA_Process_SourceClass)|V20|I..|`ULONG`
[MUIA_Process_SourceObject](MUI_Process.md/#MUIA_Process_SourceObject)|V20|I..|`ULONG`
[MUIA_Process_StackSize](MUI_Process.md/#MUIA_Process_StackSize)|V20|I..|`ULONG`
[MUIA_Process_Task](MUI_Process.md/#MUIA_Process_Task)|V20|..G|`ULONG`

## Methods
Method|Version
------|-------
[MUIM_Process_Kill](MUI_Process.md/#MUIM_Process_Kill)|V20
[MUIM_Process_Launch](MUI_Process.md/#MUIM_Process_Launch)|V20
[MUIM_Process_Process](MUI_Process.md/#MUIM_Process_Process)|V20
[MUIM_Process_Signal](MUI_Process.md/#MUIM_Process_Signal)|V20

## MUIA_Process_AutoLaunch
### NAME
[MUIA_Process_AutoLaunch](MUI_Process/#MUIA_Process_AutoLaunch) -- V20 [I..], `ULONG`, 0x80428855

### FUNCTION
If set to TRUE process loop is started right after the object instance is
created.

Defaults to TRUE.

### EXAMPLE
See supplied Process class example (Class4)

## MUIA_Process_Name
### NAME
[MUIA_Process_Name](MUI_Process/#MUIA_Process_Name) -- V20 [I..], `ULONG`, 0x8042732b

### FUNCTION
Specifies a name for the process. The name will be copied. If no name is
specified a suitable one will be generated automatically.

### EXAMPLE
See supplied Process class example (Class4)

## MUIA_Process_Priority
### NAME
[MUIA_Process_Priority](MUI_Process/#MUIA_Process_Priority) -- V20 [I..], `ULONG`, 0x80422a54

### FUNCTION
Specifies a priority for the process. Defaults to the same priority as the
calling process and shouldn't be changed if not needed.

### EXAMPLE
See supplied Process class example (Class4)

## MUIA_Process_SourceClass
### NAME
[MUIA_Process_SourceClass](MUI_Process/#MUIA_Process_SourceClass) -- V20 [I..], `ULONG`, 0x8042cf8b

### FUNCTION
To make it possible to 'embedd' process class instance into custom class
this attribute should point to the container class. [MUIM_Process_Process](MUI_Process/#MUIM_Process_Process)
method will be called using class given with this attribute and an object
specified with [MUIA_Process_SourceObject](MUI_Process/#MUIA_Process_SourceObject).

### EXAMPLE
See supplied Process class example (Class4)

### SEE ALSO
[MUIA_Process_SourceObject](MUI_Process/#MUIA_Process_SourceObject)

## MUIA_Process_SourceObject
### NAME
[MUIA_Process_SourceObject](MUI_Process/#MUIA_Process_SourceObject) -- V20 [I..], `ULONG`, 0x804212a2

### FUNCTION
To make it possible to embed process class instance into a custom class
this attribute should point to the container object. [MUIM_Process_Process](MUI_Process/#MUIM_Process_Process)
method will be called using class given with [MUIA_Process_SourceClass](MUI_Process/#MUIA_Process_SourceClass) and an
object specified with [MUIA_Process_SourceObject](MUI_Process/#MUIA_Process_SourceObject).

### EXAMPLE
See supplied Process class example (Class4)

### SEE ALSO
[MUIA_Process_SourceClass](MUI_Process/#MUIA_Process_SourceClass)

## MUIA_Process_StackSize
### NAME
[MUIA_Process_StackSize](MUI_Process/#MUIA_Process_StackSize) -- V20 [I..], `ULONG`, 0x804230d0

### FUNCTION
Specifies a stack size for the new process. Defaults to 32K.

### EXAMPLE
See supplied Process class example (Class4)

## MUIA_Process_Task
### NAME
[MUIA_Process_Task](MUI_Process/#MUIA_Process_Task) -- V20 [..G], `ULONG`, 0x8042b123

### FUNCTION
Returns a pointer to the created process.

## MUIM_Process_Kill
### NAME
[MUIM_Process_Kill](MUI_Process/#MUIM_Process_Kill) -- V20, 0x804264cf

### SYNOPSIS
`DoMethod(obj, MUIM_Process_Kill, LONG maxdelay);`

### FUNCTION
Stops process' loop ([MUIM_Process_Process](MUI_Process/#MUIM_Process_Process)). If the loop is not running does
nothing.

### INPUTS
**`LONG maxdelay`**
     the maximum time in seconds to wait until the child task eventually
     terminates

### RESULT
A boolean values which indicated whether killing the child task was
successful or not.

### EXAMPLE
See supplied Process class example (Class4)

## MUIM_Process_Launch
### NAME
[MUIM_Process_Launch](MUI_Process/#MUIM_Process_Launch) -- V20, 0x80425df7

### SYNOPSIS
`DoMethod(obj, MUIM_Process_Launch);`

### FUNCTION
Starts process' loop ([MUIM_Process_Process](MUI_Process/#MUIM_Process_Process)). If the loop is already running
does nothing.

### EXAMPLE
See supplied Process class example (Class4)

## MUIM_Process_Process
### NAME
[MUIM_Process_Process](MUI_Process/#MUIM_Process_Process) -- V20, 0x804230aa

### SYNOPSIS
`DoMethod(obj, MUIM_Process_Process, ULONG *kill, Object *proc);`

### FUNCTION
Main process method. Terminating condition is passed in message struct.
A proper implementation should wait for a signal to not use 100% cpu.

### INPUTS
**`ULONG *kill`**
     stay in the process' main loop as long as this variable is zero.

**`Object *proc`**
     a pointer to the Process object itself.

### EXAMPLE
See supplied Process class example (Class4)

## MUIM_Process_Signal
### NAME
[MUIM_Process_Signal](MUI_Process/#MUIM_Process_Signal) -- V20, 0x8042e791

### SYNOPSIS
`DoMethod(obj, MUIM_Process_Signal, ULONG sigs);`

### FUNCTION
Sends a signal mask to the created process.

### INPUTS
**`ULONG sigs`**
     a signal mask to send to the Process' child task.

### EXAMPLE
See supplied Process class example (Class4)

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
