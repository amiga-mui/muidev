# Semaphore.mui
## Super class
rootclass
## Inherited by
* [Datamap.mui](MUI_Datamap.md)
* [Dataspace.mui](MUI_Dataspace.md)
* [Objectmap.mui](MUI_Objectmap.md)
* [Process.mui](MUI_Process.md)
## Background
The semaphore class helps to access dataspace objects from different tasks.
Its methods are identical to the exec.library semaphore functions and work
on the semaphore that is contained in the Semaphore classes instance data.
## Methods
Method|Version
------|-------
[MUIM_Semaphore_Attempt](MUI_Semaphore.md/#MUIM_Semaphore_Attempt)|V11
[MUIM_Semaphore_AttemptShared](MUI_Semaphore.md/#MUIM_Semaphore_AttemptShared)|V11
[MUIM_Semaphore_Obtain](MUI_Semaphore.md/#MUIM_Semaphore_Obtain)|V11
[MUIM_Semaphore_ObtainShared](MUI_Semaphore.md/#MUIM_Semaphore_ObtainShared)|V11
[MUIM_Semaphore_Release](MUI_Semaphore.md/#MUIM_Semaphore_Release)|V11

## MUIM_Semaphore_Attempt
### NAME
[MUIM_Semaphore_Attempt](MUI_Semaphore.md/#MUIM_Semaphore_Attempt) -- V11, 0x80426ce2

### SYNOPSIS
`DoMethod(obj, MUIM_Semaphore_Attempt);`

### FUNCTION
Emulates exec.library/AttemptSemaphore.

### SEE ALSO
exec.library/AttemptSemaphore,
[MUIM_Semaphore_Obtain](MUI_Semaphore.md/#MUIM_Semaphore_Obtain), [MUIM_Semaphore_ObtainShared](MUI_Semaphore.md/#MUIM_Semaphore_ObtainShared), [MUIM_Semaphore_Release](MUI_Semaphore.md/#MUIM_Semaphore_Release),
[MUIM_Semaphore_AttemptShared](MUI_Semaphore.md/#MUIM_Semaphore_AttemptShared)

## MUIM_Semaphore_AttemptShared
### NAME
[MUIM_Semaphore_AttemptShared](MUI_Semaphore.md/#MUIM_Semaphore_AttemptShared) -- V11, 0x80422551

### SYNOPSIS
`DoMethod(obj, MUIM_Semaphore_AttemptShared);`

### FUNCTION
Emulates exec.library/AttemptSemaphoreShared.
The autodocs suggested pre-V39 fixes are already implemented.

### SEE ALSO
exec.library/AttemptSemaphoreShared,
[MUIM_Semaphore_Obtain](MUI_Semaphore.md/#MUIM_Semaphore_Obtain), [MUIM_Semaphore_ObtainShared](MUI_Semaphore.md/#MUIM_Semaphore_ObtainShared), [MUIM_Semaphore_Release](MUI_Semaphore.md/#MUIM_Semaphore_Release),
[MUIM_Semaphore_Attempt](MUI_Semaphore.md/#MUIM_Semaphore_Attempt)

## MUIM_Semaphore_Obtain
### NAME
[MUIM_Semaphore_Obtain](MUI_Semaphore.md/#MUIM_Semaphore_Obtain) -- V11, 0x804276f0

### SYNOPSIS
`DoMethod(obj, MUIM_Semaphore_Obtain);`

### FUNCTION
Emulates exec.library/ObtainSemaphore.

### SEE ALSO
exec.library/ObtainSemaphore,
[MUIM_Semaphore_AttemptShared](MUI_Semaphore.md/#MUIM_Semaphore_AttemptShared), [MUIM_Semaphore_ObtainShared](MUI_Semaphore.md/#MUIM_Semaphore_ObtainShared),
[MUIM_Semaphore_Release](MUI_Semaphore.md/#MUIM_Semaphore_Release), [MUIM_Semaphore_Attempt](MUI_Semaphore.md/#MUIM_Semaphore_Attempt)

## MUIM_Semaphore_ObtainShared
### NAME
[MUIM_Semaphore_ObtainShared](MUI_Semaphore.md/#MUIM_Semaphore_ObtainShared) -- V11, 0x8042ea02

### SYNOPSIS
`DoMethod(obj, MUIM_Semaphore_ObtainShared);`

### FUNCTION
Emulates exec.library/ObtainSemaphoreShared.
The autodocs suggested pre-V39 fixes are already implemented.

### SEE ALSO
exec.library/ObtainSemaphoreShared,
[MUIM_Semaphore_AttemptShared](MUI_Semaphore.md/#MUIM_Semaphore_AttemptShared), [MUIM_Semaphore_Obtain](MUI_Semaphore.md/#MUIM_Semaphore_Obtain), [MUIM_Semaphore_Release](MUI_Semaphore.md/#MUIM_Semaphore_Release),
[MUIM_Semaphore_Attempt](MUI_Semaphore.md/#MUIM_Semaphore_Attempt)

## MUIM_Semaphore_Release
### NAME
[MUIM_Semaphore_Release](MUI_Semaphore.md/#MUIM_Semaphore_Release) -- V11, 0x80421f2d

### SYNOPSIS
`DoMethod(obj, MUIM_Semaphore_Release);`

### FUNCTION
Emulates exec.library/ReleaseSemaphore.

### SEE ALSO
exec.library/ReleaseSemaphore,
[MUIM_Semaphore_AttemptShared](MUI_Semaphore.md/#MUIM_Semaphore_AttemptShared), [MUIM_Semaphore_Obtain](MUI_Semaphore.md/#MUIM_Semaphore_Obtain), [MUIM_Semaphore_Release](MUI_Semaphore.md/#MUIM_Semaphore_Release),
[MUIM_Semaphore_Attempt](MUI_Semaphore.md/#MUIM_Semaphore_Attempt)

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
