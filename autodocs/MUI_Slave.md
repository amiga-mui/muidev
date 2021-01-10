# Slave.mui
## Super class
[Process.mui](MUI_Process.md)
## Background
The Slave class provides a convenient way of safely dispatching methods that
are to be run asynchronously on a thread as well as a safe way to call a
method from a thread on the main thread. In the most simple case one just
needs to call DoMethod() on the Slave instance rather than the object.

A Slave object is always bound to a single object it will invoke methods on.
You MUST NOT call methods of Process class directly on the instance of Slave
class. Furthermore it is your responsibility to ensure that the related
application object stays alive as long as the slave object which is bound with
your object.

Some attributes of Process class are allowed to be passed to the OM_NEW method
of Slave class:
  - [MUIA_Process_Name](MUI_Process.md/#MUIA_Process_Name)
  - [MUIA_Process_StackSize](MUI_Process.md/#MUIA_Process_StackSize)
  - [MUIA_Process_Priority](MUI_Process.md/#MUIA_Process_Priority)
All other attributes of Process class will be ignored.

### NOTES
Dispatching of methods works up to 16 arguments. In case your method needs
more parameters then [MUIM_Slave_Dispatch](MUI_Slave.md/#MUIM_Slave_Dispatch) must be used directly.

Keep in mind that it is your responsibility to ensure that both the main and
the slave thread access instance data and other global stuff in a thread
safe manner. Since Slave class is a subclass of Semaphore class methods like
[MUIM_Semaphore_Obtain](MUI_Semaphore.md/#MUIM_Semaphore_Obtain)/Release can be used to arbitrate the access to the
data instance data. Parallel access to global stuff must be secured
similarly.

### EXAMPLE
This is an incomplete example of a class using Slave class. It is by no means
meant to be a working implementation.

```c++
ULONG myClass_NEW(struct IClass *cl, Object *obj, Msg msg)
{
  if((obj = DoSuperMethodA(cl, obj, msg)) != NULL)
  {
    struct Data = INST_DATA(cl, obj);

    /* Create the slave object
     */
    data->slave = SlaveObject,
      MUIA_Slave_Object, obj,
      MUIA_Slave_Class, cl,
    End;
  }

  return (ULONG)obj;
}

ULONG myClass_DISPOSE(struct IClass *cl, Object *obj, Msg msg)
{
  struct Data = INST_DATA(cl, obj);

  /* Dispose the slave object
   */
  MUI_DisposeObject(data->slave);

  return DoSuperMethodA(cl, obj, msg);
}

ULONG myClass_Setup(struct IClass *cl, Object *obj, Msg msg)
{
  struct Data = INST_DATA(cl, obj);
  ULONG rc;

  if((rc = DoSuperMethodA(cl, obj, msg)) != 0)
  {
    STRPTR arg1;

    /* Please note that unless your object is after MUIM_Setup, you won't be
     * able to invoke methods on the main thread from the slave thread!
     * SEE ALSO MUIA_Slave_Application
     */
    DoMethod(data->slave, MUIM_MyClass_DispatchedOnAThread, arg1,
      arg2, arg3..., arg16);

    /*
     * Assume you need to pass some temporary data
     */
    if((arg1 = AllocVec(strlen(x) + 1)) != NULL)
    {
      strlcpy(arg1, x, strlen(x)+1);
      if(DoMethod(data->slave, MUIM_MyClass_DispatchedOnAThread,
        arg1, ...) == 0)
      {
        /* the slave object will return a 0 if the dispatch setup has
         * failed. In this case the data must be freed here.
         */
        FreeVec(arg1);
      }
    }
  }

  return rc;
}

ULONG myClass_DispatchedOnAThread(struct IClass *cl, Object *obj,
  struct MUIP_MyClass_DispatchedOnAThread *msg)
{
  struct Data = INST_DATA(cl, obj);

  /* This method will be executed on a subthread
   */

  /* Give some feedback to our main application thread - this is the only
   * way to obtain a result from this method on the main thread
   */
  DoMethod(data->slave, MUIM_MyClass_Feedback, feedback);

  /* CAUTION: remember that the method is dispatched asynchronously hence no
   * temporary data (i.e. located on the stack) must be passed as
   * parameters. Any dynamically allocated parameter should be freed here
   * after its use.
   */

  /* Free the dynamically allocated string.
   */
  FreeVec(msg->arg1);

  return result;
}

ULONG myClass_Error(struct IClass *cl, Object *obj, Msg msg)
{
  /* In case your method was for some reason not dispatched while the
   * invocation returned a success (see Setup method above) this method will
   * be called for each failed dispatch when the Slave object is disposed
   */
  switch(((Msg)msg->FailedDispatch)->MethodID)
  {
    case MUIM_MyClass_DispatchedOnAThread:
    {
      /* free all dynamically allocated parameters
       */
      struct MUIP_MyClass_DispatchedOnAThread *dmsg = msg->FailedDispatch;

      FreeVec(dmsg->arg1);
    }
    break;
  }

  return 0;
}

ULONG myClass_Feedback(struct IClass *cl, Object *obj,
  struct MUIP_MyClass_Feedback *msg)
{
  /* This method will be executed on the main thread when dispatched from
   * the slave thread.
   */

  return result;
}
```
## Attributes
Attribute|Version|ISG|Type
---------|-------|---|----
[MUIA_Slave_Application](MUI_Slave.md/#MUIA_Slave_Application)|V20|I..|`Object *`
[MUIA_Slave_Class](MUI_Slave.md/#MUIA_Slave_Class)|V20|I..|`Object *`
[MUIA_Slave_Object](MUI_Slave.md/#MUIA_Slave_Object)|V20|I..|`Object *`

## Methods
Method|Version
------|-------
[MUIM_Slave_Cleanup](MUI_Slave.md/#MUIM_Slave_Cleanup)|V20
[MUIM_Slave_Dispatch](MUI_Slave.md/#MUIM_Slave_Dispatch)|V20
[MUIM_Slave_Error](MUI_Slave.md/#MUIM_Slave_Error)|V20
[MUIM_Slave_Setup](MUI_Slave.md/#MUIM_Slave_Setup)|V20
[MUIM_Slave_SignalsReceived](MUI_Slave.md/#MUIM_Slave_SignalsReceived)|V20

## MUIA_Slave_Application
### NAME
[MUIA_Slave_Application](MUI_Slave.md/#MUIA_Slave_Application) -- V20 [I..], `Object *`, 0x80427767

### FUNCTION
By default Slave class will try to obtain the application object the first
time a method is dispatched. However, if the main object is not subclassed
from Area class or has not received the [MUIM_Setup](MUI_Area.md/#MUIM_Setup) method call yet this
automatism is not possible.

In these cases [MUIA_Slave_Application](MUI_Slave.md/#MUIA_Slave_Application) can be set explicitly during OM_NEW.

## MUIA_Slave_Class
### NAME
[MUIA_Slave_Class](MUI_Slave.md/#MUIA_Slave_Class) -- V20 [I..], `Object *`, 0x80420f8c

### FUNCTION
If set to a valid class all methods will be dispatched using CoerceMethod()
rather than DoMethod().

### SEE ALSO
[MUIA_Process_SourceClass](MUI_Process.md/#MUIA_Process_SourceClass)

## MUIA_Slave_Object
### NAME
[MUIA_Slave_Object](MUI_Slave.md/#MUIA_Slave_Object) -- V20 [I..], `Object *`, 0x804202ab

### FUNCTION
Destination object to dispatch methods on. This attribute is mandatory and
MUST be set during OM_NEW.

### SEE ALSO
[MUIA_Process_SourceObject](MUI_Process.md/#MUIA_Process_SourceObject)

## MUIM_Slave_Cleanup
### NAME
[MUIM_Slave_Cleanup](MUI_Slave.md/#MUIM_Slave_Cleanup) -- V20, 0x80425e72

### SYNOPSIS
`DoMethod(obj, MUIM_Slave_Cleanup);`

### FUNCTION
This method should be implemented if your slave needs some special cleanup
procecedure before the the slave thread eventually ceases to exist. Keep in
mind that this method might be called during the parent object's OM_DISPOSE
method.

### SEE ALSO
[MUIM_Slave_Setup](MUI_Slave.md/#MUIM_Slave_Setup)

## MUIM_Slave_Dispatch
### NAME
[MUIM_Slave_Dispatch](MUI_Slave.md/#MUIM_Slave_Dispatch) -- V20, 0x8042361f

### SYNOPSIS
`DoMethod(obj, MUIM_Slave_Dispatch, ULONG flags, LONG count, /* ... */);`

### FUNCTION
Dispatch a method on the slave's thread. If called from the thread the
method will be dispatched on the main thread instead. The execution of all
methods is asynchronous and will happen in parallel. Make sure not to pass
volatile or temporary data to the method, because these might have become
invalid by the time the method is eventually executed. If more than 16
parameters must be used then [MUIM_Slave_Dispatch](MUI_Slave.md/#MUIM_Slave_Dispatch) must be called directly.

### INPUTS
**`ULONG flags`**
     set to MUIF_Slave_Delegate_ForceSlave if the method is to be
     dispatched on the slave's thread in any case. For example this is
     required if the DoMethod() call happens from a thread that is
     neither the slave nor the main thread. This is also useful if a
     method call from the slave is to be executed on the slave's thread
     as well.

**`LONG count`**
     number of following parameters. This includes the MethodID as well.

**`parameters`**
     the actual parameters

### RESULT
Non-zero if setting up the dispatch message succeeded, zero otherwise. In
case of a failure all dynamically allocated parameters must be freed
by the calling thread.

### SEE ALSO
[MUIM_Application_PushMethod](MUI_Application.md/#MUIM_Application_PushMethod), [MUIM_Slave_Error](MUI_Slave.md/#MUIM_Slave_Error)

## MUIM_Slave_Error
### NAME
[MUIM_Slave_Error](MUI_Slave.md/#MUIM_Slave_Error) -- V20, 0x8042e544

### SYNOPSIS
`DoMethod(obj, MUIM_Slave_Error, Msg FailedDispatch, /* ... */);`

### FUNCTION
This method will be called on the slave's main object to dispose dynamically
allocated parameters of a dispatched method. For example this happens if the
method could not be dispatched after it has been queued for execution.

A possible situation is when the application is disposed before all queued
methods were executed.

### INPUTS
**`Msg FailedDispatch`**
     a full Msg containing the failed MethodID and all parameters

### SEE ALSO
MUIC_Slave

## MUIM_Slave_Setup
### NAME
[MUIM_Slave_Setup](MUI_Slave.md/#MUIM_Slave_Setup) -- V20, 0x80429faa

### SYNOPSIS
`DoMethod(obj, MUIM_Slave_Setup);`

### FUNCTION
This method should be implemented if your slave needs some special setup
procecedure before the first method is dispatched in the slave thread.

Usually this is quite useful for setting up network stuff, i.e. in a VNC client.

### RESULT
**`ULONG sigmask`**
     a signal mask containing the signals for which the method
     [MUIM_Slave_SignalsReceived](MUI_Slave.md/#MUIM_Slave_SignalsReceived) is to be triggered. This method will be dispatched
     on the slave process. Return 0 if no custom signals are needed.

### NOTES
All SIGBREAKF_CTRL_XXX signals are reserved for Slave class' internal usage and
MUST NOT be used by user classes.

### SEE ALSO
[MUIM_Slave_Cleanup](MUI_Slave.md/#MUIM_Slave_Cleanup), [MUIM_Slave_SignalsReceived](MUI_Slave.md/#MUIM_Slave_SignalsReceived)

## MUIM_Slave_SignalsReceived
### NAME
[MUIM_Slave_SignalsReceived](MUI_Slave.md/#MUIM_Slave_SignalsReceived) -- V20, 0x8042d21a

### SYNOPSIS
`DoMethod(obj, MUIM_Slave_SignalsReceived, ULONG sigmask);`

### FUNCTION
This method is invoked on the slave process whenever the slave process
receives a signal matching those returned by the [MUIM_Slave_Setup](MUI_Slave.md/#MUIM_Slave_Setup) method.

### INPUTS
**`ULONG sigmask`**
     received signal mask

### SEE ALSO
[MUIM_Slave_Setup](MUI_Slave.md/#MUIM_Slave_Setup)

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
