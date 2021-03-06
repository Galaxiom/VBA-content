
# Application.AddResourcesFromProjectServer Method (Project)

Opens the ** Build Team** dialog box if you are connected to Project Server and are currently in a resource view.


## Syntax

 _expression_. **AddResourcesFromProjectServer**

 _expression_A variable that represents an  **Application** object.


### Return Value

 **Boolean**


## Remarks

The  **AddResourcesFromProjectServer** method is only available in resource views and returns a trappable error (error code 1100) when applied in a non-resource view.


## Example

The following example displays the  **Build Team from Project Server** dialog box. First, Project adds the URL specified in **Collaboration Options** ( **Collaborate** menu) to Microsoft Internet Explorer's list of trusted sites. Upon confirmation, Project switches to a **Resource Sheet** view and displays the ** Build Team from Project Server** dialog box, if connected to My Computer in workgroup mode. Project displays the ** Build Team from <Project Name&gt;** dialog box when connected to Project Server.


```vb
Sub AddResources() 
   If Projects.Count = 0 Then 
      MsgBox "You must have at least one active project open." 
      Exit Sub 
   End If 
 
   If ActiveProject.ServerURL = "" Then 
      MsgBox "A Project Server URL has not been " _ 
         &amp; "specified." &amp; Chr(13) &amp; "Click OK to select " _ 
         &amp; "'Collaborate Using Project Server' and " _ 
         &amp; "specify a valid URL in the Options dialog box " _ 
         &amp; "(Tools menu)." 
      Application.OptionsWorkgroup 
   Else 
      ActiveProject.MakeServerURLTrusted 
      ViewApply Name:="Resource Sheet" 
      Application.AddResourcesFromProjectServer 
   End If 
End Sub
```

