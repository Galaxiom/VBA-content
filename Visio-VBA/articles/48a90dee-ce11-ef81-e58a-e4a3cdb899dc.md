
# Master.Index Property (Visio)

Gets the ordinal position of a  **Master** object in the **Masters** collection. Read-only.


## Syntax

 _expression_. **Index**

 _expression_A variable that represents a  **Master** object.


### Return Value

Integer


## Remarks

Most collections are indexed starting with 1 rather than zero (0), so the index of the first element is 1, the index of the second element is 2, and so forth. The index of the last element in a collection is the same as the value of that collection's  **Count** property. You can iterate through a collection by using these index values. Adding objects to or deleting objects from a collection can change the index values of other objects in the collection.

