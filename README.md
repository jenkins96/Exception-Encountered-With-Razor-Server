# Exception Encountered With Razor Server

I want to redirect user to the login page when user is not authenticated.  

I am using OKTA authentication.  

However, when I run the project I am receving an error.  
 
I want to narrow down the problem, and simplify the project; comment out Okta portion in program file & in the project, and change to
  
UriHelper.NavigateTo(https://yahoo.com, true); the project is nothing to do OKTA.
  
Receiving following error:
 ```
System.NullReferenceException
  HResult=0x80004003
  Message=Object reference not set to an instance of an object.
  Source=Microsoft.AspNetCore.Components
  StackTrace:
   at Microsoft.AspNetCore.Components.RenderTree.RenderTreeDiffBuilder.UpdateRetainedChildComponent(DiffContext& diffContext, Int32 oldComponentIndex, Int32 newComponentIndex)
   at Microsoft.AspNetCore.Components.RenderTree.RenderTreeDiffBuilder.AppendDiffEntriesForFramesWithSameSequence(DiffContext& diffContext, Int32 oldFrameIndex, Int32 newFrameIndex)
   at Microsoft.AspNetCore.Components.RenderTree.RenderTreeDiffBuilder.AppendDiffEntriesForRange(DiffContext& diffContext, Int32 oldStartIndex, Int32 oldEndIndexExcl, Int32 newStartIndex, Int32 newEndIndexExcl)
   at Microsoft.AspNetCore.Components.RenderTree.RenderTreeDiffBuilder.ComputeDiff(Renderer renderer, RenderBatchBuilder batchBuilder, Int32 componentId, ArrayRange`1 oldTree, ArrayRange`1 newTree)
   at Microsoft.AspNetCore.Components.Rendering.ComponentState.RenderIntoBatch(RenderBatchBuilder batchBuilder, RenderFragment renderFragment, Exception& renderFragmentException)
   at Microsoft.AspNetCore.Components.RenderTree.Renderer.ProcessRenderQueue()
--- End of stack trace from previous location ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at Microsoft.AspNetCore.Components.Rendering.HtmlRenderer.HandleException(Exception exception)
   at Microsoft.AspNetCore.Components.RenderTree.Renderer.ProcessRenderQueue()
   at Microsoft.AspNetCore.Components.RenderTree.Renderer.ProcessPendingRender()
   at Microsoft.AspNetCore.Components.RenderTree.Renderer.AddToRenderQueue(Int32 componentId, RenderFragment renderFragment)
   at Microsoft.AspNetCore.Components.ComponentBase.StateHasChanged()
   at Microsoft.AspNetCore.Components.ComponentBase.CallOnParametersSetAsync()
   at Microsoft.AspNetCore.Components.ComponentBase.<RunInitAndSetParametersAsync>d__20.MoveNext()
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at Microsoft.AspNetCore.Components.Rendering.HtmlRenderer.HandleException(Exception exception)
   at Microsoft.AspNetCore.Components.RenderTree.Renderer.HandleExceptionViaErrorBoundary(Exception error, ComponentState errorSourceOrNull)
   at Microsoft.AspNetCore.Components.RenderTree.Renderer.AddToPendingTasks(Task task, ComponentState owningComponentState)
   at Microsoft.AspNetCore.Components.Rendering.ComponentState.SupplyCombinedParameters(ParameterView directAndCascadingParameters)
   at Microsoft.AspNetCore.Components.Rendering.ComponentState.SetDirectParameters(ParameterView parameters)
   at Microsoft.AspNetCore.Components.RenderTree.Renderer.<RenderRootComponentAsync>d__39.MoveNext()
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.GetResult()
   at Microsoft.AspNetCore.Components.Rendering.HtmlRenderer.<CreateInitialRenderAsync>d__17.MoveNext()
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter`1.GetResult()
   at Microsoft.AspNetCore.Components.Rendering.HtmlRenderer.<RenderComponentAsync>d__8.MoveNext()
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Microsoft.AspNetCore.Components.Rendering.RendererSynchronizationContext.<>c__11`1.<<InvokeAsync>b__11_0>d.MoveNext()
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter`1.GetResult()
   at Microsoft.AspNetCore.Mvc.ViewFeatures.StaticComponentRenderer.<PrerenderComponentAsync>d__4.MoveNext()
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter`1.GetResult()
   at Microsoft.AspNetCore.Mvc.ViewFeatures.ComponentRenderer.<PrerenderedServerComponentAsync>d__11.MoveNext()
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter`1.GetResult()
   at Microsoft.AspNetCore.Mvc.ViewFeatures.ComponentRenderer.<RenderComponentAsync>d__6.MoveNext()
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter`1.GetResult()
   at Microsoft.AspNetCore.Mvc.TagHelpers.ComponentTagHelper.<ProcessAsync>d__21.MoveNext()
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.GetResult()
   at Microsoft.AspNetCore.Razor.Runtime.TagHelpers.TagHelperRunner.<<RunAsync>g__Awaited|0_0>d.MoveNext()
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.GetResult()
   at BlazorApp1.Pages.Pages__Layout.<<ExecuteAsync>b__14_0>d.MoveNext() in C:\Users\adria\Downloads\Exception-Encountered-With-Razor-Server-main\Exception-Encountered-With-Razor-Server-main\BlazorApp1\Pages\_Layout.cshtml:line 15

  This exception was originally thrown at this call stack:
    [External Code]
    BlazorApp1.Pages.Pages__Layout.ExecuteAsync.AnonymousMethod__14_0() in _Layout.cshtml
 ```

Yes, if you take out that line on line 15 in "_Layout.cshtml" error is gone, but why should I?
Why is this issue happening?

## Setup
* Visual Studio 2022
* Net 6.0
* Blazor Server App

## Steps To Reproduce
* Clone Repository
* Run Project



This reminds me of and older similat bug:
* [Exceptions encountered when running Razor Components application](https://github.com/dotnet/aspnetcore/issues/7665).
