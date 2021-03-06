
# Application.CalendarBarStylesEdit Method (Project)

Changes the style of the specified type of bar in the Calendar view.


## Syntax

 _expression_. **CalendarBarStylesEdit**( **_Item_**,  **_Bar_**,  **_Pattern_**,  **_Color_**,  **_Align_**,  **_Wrap_**,  **_Shadow_**,  **_Field1_**,  **_Field2_**,  **_Field3_**,  **_Field4_**,  **_Field5_**,  **_SplitPattern_**)

 _expression_A variable that represents an  **Application** object.


### Parameters



|**Name**|**Required/Optional**|**Data Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Item|Required| **Long**|The type of calendar bar style to edit. Can be one of the following  **[PjBarItem](f00c9e4d-fed3-3de8-e672-fb64e871f0d2.md)** constants: **pjBarNonCritical**,  **pjBarCritical**,  **pjBarSummary**,  **pjBarMilestone**,  **pjBarMarked**,  **pjBarHighlighted**,  **pjBarProjectSummary**, or  **pjBarExternalTask**.|
|Bar|Optional| **Long**|The bar type. Can be one of the following  **[PjCalendarBarType](7e43f537-fd96-9f3d-1f3b-9c444bf7b672.md)** constants: **pjNormalBar**,  **pjLineBar**, or  **pjNoBar**.|
|Pattern|Optional| **Long**|The bar pattern. Can be one of the  **[PjFillPattern](4f6af32c-5efd-42b6-4017-20a1497c1b6d.md)** constants.|
|Color|Optional| **Long**|The bar color. Can be one of the  **[PjColor](46108cf5-1e35-9774-b424-6c84223d9aac.md)** constants.|
|Align|Optional| **Long**|The justification of text in the bar. Can be one of the following  **[PjAlignment](925376b3-c8aa-3326-5693-71dd3510f28c.md)** constants: **pjLeft**,  **pjCenter**, or  **pjRight**.|
|Wrap|Optional| **Boolean**| **True** if Project wraps text in the bar; otherwise, **False**.|
|Shadow|Optional| **Boolean**| **True** if the bar has a shadow; otherwise, **False**.|
|Field1|Optional| **String**|The first field to display in the bar.|
|Field2|Optional| **String**|The second field to display in the bar.|
|Field3|Optional| **String**|The third field to display in the bar.|
|Field4|Optional| **String**|The fourth field to display in the bar.|
|Field5|Optional| **String**|The fifth field to display in the bar.|
|SplitPattern|Optional| **Long**|The line pattern used to display split tasks. Can be one of the following  **[PjLineType](1bbd5c65-b6c5-a190-ce5e-dfdd326e1975.md)** constants: **pjNoLines**,  **pjDash**,  **pjCloseDot**,  **pjContinuous**, or  **pjDot**.|

### Return Value

 **Boolean**


## Remarks

Specifying a value for any of  _Field1_ through _Field5_ requires that all preceding _Field_ arguments also be specified. For example, specifying _Field3_ also requires _Field1_ and _Field2_ to be specified.


 **Note**  The  _Field1_ to _Field5_ parameters cannot use the **PjFields** constants. To see the field names that you can add to calendar bars, open the Calendar view, click the **Format** tab in the **Calendar Tools** group. Click **Bar Styles** on the Ribbon, and then click the ** Field(s)** drop-down list.

To edit calendar bar styles where  _Color_ can be an RGB value, use the **[CalendarBarStylesEditEx](3b7cb188-fff6-b9c1-a673-34774791c043.md)** method.


## Example

The following example sets critical tasks as normal bars, the color to purple with diagonal stripes, and the fields to include the task name and assigned resource names. The example also sets summary tasks as line bars and the color to green.


```vb
Sub CalendarBar_StyleEdit() 
 'Activate Caldender view 
 ViewApply Name:="Calendar" 
 
 CalendarBarStylesEdit Item:=pjBarCritical, Bar:=PjCalendarBarType.pjNormalBar, _ 
 Color:=PjColor.pjPurple, Pattern:=PjFillPattern.pjDiagonalRightPattern, _ 
 Field1:="Name", Field2:="Resource Names" 
 CalendarBarStylesEdit Item:=pjBarSummary, Bar:=PjCalendarBarType.pjLineBar, _ 
 Color:=PjColor.pjGreen 
End Sub
```

