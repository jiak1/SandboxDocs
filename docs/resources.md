# Resources
Resources are the name for Tiles on layers 1 and 2 (those that aren't the base biome layer).

#xml

To add a reosurce xml file to the list of files loaded by the game, place it in the games Resources\WorldGeneration file, and add it to the <Files> tag in Layer1Header.xml
*Note that the order in Layer1Header.xml determines the order resources are spawned.*

Each resource must have an eclosing <Tile> tag, and exist within a <ResourceList> tag.

<table>
	<tr>
	<td>tag</td>
	<td>type</td>
	<td>description</rd>
	</tr>
</table>

``` prolog
<Resource>
<ID>2</ID>
<Name>Iron Ore</Name>
<SpawnChance>0.5</SpawnChance>
</Resource>
```