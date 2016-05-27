# Module: MMM-Nest
The `MMM-Nest` module is a <a href="https://github.com/MichMich/MagicMirror">MagicMirror</a> addon.
This module displays your <a href="https://www.nest.com">Nest's</a> data on your Mirror

## Using the module

To use this module, add it to the modules array in the `config/config.js` file:
````javascript
modules: [
	{
		module: 'MMM-Nest',
		position: 'lower_third',	// This can be any of the regions.
									// Best results in one of the middle regions like: lower_third
		config: {
			// See 'Configuration options' for more information.
			token: '1234567890zbcdefghijkl' //Nest Token - REQUIRED

		}
	}
]
````

## Configuration options

The following properties can be configured:


<table width="100%">
	<!-- why, markdown... -->
	<thead>
		<tr>
			<th>Option</th>
			<th width="100%">Description</th>
		</tr>
	<thead>
	<tbody>
		<tr>
			<td><code>token</code></td>
			<td>Used to get data from your Nest<br>
				<br><b>Example:</b> <code>c.alkjsfkljadsfj234....</code>
				<br> This value is <b>REQUIRED</b>
			</td>
		</tr>
	</tbody>
</table>