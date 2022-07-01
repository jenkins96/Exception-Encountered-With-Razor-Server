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
at Microsoft.AspNetCore.Components.RenderTree.RenderTreeDiffBuilder.ComputeDiff(Renderer renderer, RenderBatchBuilder batchBuilder, Int32 componentId, ArrayRange1 oldTree, ArrayRange1 newTree)
at Microsoft.AspNetCore.Components.Rendering.ComponentState.RenderIntoBatch(RenderBatchBuilder batchBuilder, RenderFragment renderFragment, Exception& renderFragmentException)
at Microsoft.AspNetCore.Components.RenderTree.Renderer.ProcessRenderQueue()
--- End of stack trace from previous location ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at Microsoft.AspNetCore.Components.Rendering.HtmlRenderer.HandleException(Exception exception)
at Microsoft.AspNetCore.Components.RenderTree.Renderer.ProcessRenderQueue()
at Microsoft.AspNetCore.Components.RenderTree.Renderer.ProcessPendingRender()
at Microsoft.AspNetCore.Components.RenderTree.Re
 ```

## Setup
* Window 10
* Visual Studio 2022
* Net 6.0
* Blazor Server App

## Steps To Reproduce
* Clone Repository
* Run Project



This reminds me of and older similat bug:
* https://github.com/dotnet/aspnetcore/issues/7665
