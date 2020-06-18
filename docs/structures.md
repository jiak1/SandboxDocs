# Structures

Structures are stored internally as resources. 

To spawn a resource as a structure, add the <StructureInfo> tag which must contain the following tags

<table>
	<tr>
		<td>tag</td>
		<td>variable type</td>
		<td>description</rd>
	</tr>
	<tr>
		<td>StructureSize</td>
		<td>Vector2Int (2 ints)</td>
		<td>Two integers seperated by a comma for the width and height of the structure.</td>
	</tr>
	<tr>
		<td>StructureTiles</td>
		<td>string array</td>
		<td>The id's of the tiles in the structure in order. Use commas to seperate columns, and NewLines to seperate rows.</td>
	</tr>
</table>


## Example StructureInfo:

``` prolog
<StructureInfo>
   <StructureSize>6, 6</StructureSize>
   <StructureTiles>
     1, 1, 1, 1, 1, 1
     1, 23, 2, 2, 23, 1
     1, 2, 5, 5, 2, 1
     1, 2, 5, 5, 2, 1
     1, 23, 2, 2, 23, 1
     1, 1, 1, 1, 1, 1
   </StructureTiles>
 </StructureInfo>
 ```
