# Resources
Resources are the name for items & blocks.

# Base Resource

``` csharp
using Modding.Models;

    class NewResource : BaseResource
    {
        public override string name { get { return "new_resource"; } }
    }

```

To add a resource xml file to the list of files loaded by the game, place it in the games [Resources\WorldGeneration](worldgenfiles) file, and add it to the `<Files>` tag in [Layer1Header.xml](worldgenfiles)

!> The order in [Layer1Header.xml](worldgenfiles) determines the order resources are spawned.

Each resource must have an enclosing `<Tile>` tag, and exist within a `<ResourceList>` tag.

<table>
	<tr>
		<td>Tag</td>
		<td>Variable Type</td>
		<td>Description</rd>
	</tr>
	<tr>
		<td>ID</td>
		<td>String</td>
		<td>Name and unique id of the tile, must be unique</td>
	</tr>
	<tr>
		<td>FileName</td>
		<td>String</td>
		<td>The name of the file containing the tile itself. 
		The file must be in the [Resources\WorldGeneration\Tiles](worldgenfiles) folder</td>
	</tr>
</table>

If you want the resource to spawn naturally in the world, include a `<SpawnInfo>` tag. All tags in the table below should be included within the `<SpawnInfo>` tag and are all optional.

<table>
	<tr>
		<td>Tag</td>
		<td>Variable Type</td>
		<td>Description</rd>
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
		<td>Bool</td>
		<td>Use perlin noise insetad of the normal cellular noise for generating this resource. Overriden by SingleInstance. <b>Note that PerlinNoise will often result in decreased spawn rate and size compared to cellular noise</b></td>
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
	<tr>
		<td>FillAllLayers</td>
		<td>bool</td>
		<td>If true on a layer 1 resource, layer 2 resources won't spawn on top of it</td>
	</tr>
</table>

## Resource Tile

``` prolog
<Tile>
  <id>2</id>
  <Name>Iron Ore</Name>
  <FileName>IronOre</FileName>
  <SpawnInfo>
    <Frequency>0.9</Frequency>
    <Size>1</Size>
    <SpawnRate>0.3</SpawnRate>
  </SpawnInfo>
</Tile>
```
