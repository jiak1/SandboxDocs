# Resources
Resources are the name for Tiles on layers 1 and 2 (those that aren't the base biome layer).

#xml

To add a reosurce xml file to the list of files loaded by the game, place it in the games Resources\WorldGeneration file, and add it to the <Files> tag in Layer1Header.xml
*Note that the order in Layer1Header.xml determines the order resources are spawned.*

Each resource must have an eclosing <Tile> tag, and exist within a <ResourceList> tag.

<table>
	<tr>
		<td>tag</td>
		<td>variable type</td>
		<td>description</rd>
	</tr>
	<tr>
		<td>id</td>
		<td>string</td>
		<td>Name and unique id of the tile, must be unique</td>
	</tr>
	<tr>
		<td>FileName</td>
		<td>string</td>
		<td>The name of the file containing the tile itself. 
		The file must be in the Resources\WorldGeneration\Tiles folder</td>
	</tr>
</table>

If you want the resource to spawn naturally in the world, inclide a <SpawnInfo> tag. All tags in the table below should be included within the <SpawnInfo> tag and are all optional.

<table>
	<tr>
		<td>tag</td>
		<td>variable type</td>
		<td>description</rd>
	</tr>
	<tr>
		<td>Frequency</td>
		<td>Float</td>
		<td>Changes the frequency variable in the random noise generator. Scale of 0-1.</td>
	</tr>
	<tr>
		<td>Size</td>
		<td>Float</td>
		<td>Multiplies the size of the generated vein by the given value.</td>
	</tr>
	<tr>
		<td>SpawnRate</td>
		<td>Float</td>
		<td>How common veins of this resource should be. Scale of 0-1</td>
	</tr>
	<tr>
		<td>UsePerlin</td>
		<td>bool</td>
		<td>Use perlin noise insetad of the normal cellular noise for generating this resource. Overriden by SingleInstance
		*Note that PerlinNoise will often result in decreased spawn rate and size compared to cellular noise*</td>
	</tr>
	<tr>
		<td>SingleInstance</td>
		<td>Bool</td>
		<td>Use white noise instead of the normal cellular noise, causing veins to spawn in a size of 1. Overrides UsePerlin</td>
	</tr>
	<tr>
		<td>Jitter</td>
		<td>Float</td>
		<td>Sets the jitter value of the noise generator. Only functions if SingleInstance and UsePerlin are false. Scale of 0-1</td>
	</tr>
	<tr>
		<td>Biomes</td>
		<td>List, String</td>
		<td>Names of all the biomes this resource should spawn in. Resource will spawn in all biomes if this tag is not present.</td>
	</tr>
</table>

``` prolog
<Resource>
<ID>2</ID>
<Name>Iron Ore</Name>
<SpawnChance>0.5</SpawnChance>
</Resource>
```