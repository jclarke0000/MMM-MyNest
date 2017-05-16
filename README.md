# Module: MMM-MyNest
The `MMM-MyNest` module is a <a href="https://github.com/MichMich/MagicMirror">MagicMirror</a> addon.

It is a fork of MMM-Nest by Luke Moch
https://github.com/mochman/MMM-Nest

This module displays your <a href="https://www.nest.com">Nest Thermostat</a> data on your Mirror

![Screenshot 1](/../screenshots/mmm-mynest-scr1.png?raw=true "Screenshot 1")
![Screenshot 2](/../screenshots/mmm-mynest-scr2.png?raw=true "Screenshot 2")


**NOTE** I haven't tested this with multiple thermostats, or with list mode.  I only have one Nest in my home, and list mode kind of defeats the reason why I modified this module, which was to make the module look very close to what you see in the Nest app.


## Installing the module
run `git clone https://github.com/jclarke0000/MMM-MyNest` from inside your `MagicMirror/modules` folder

## Getting the Nest Token
Run getToken.sh.  This will walk you through getting a token to allow this module to get data from your Nest.  It requires you to set up a Nest Developer Account.

## Known Issues
If you have a family account, make sure you get the PIN with your master account's login (not a account you shared the thermostat with).

## Using the module
To use this module, add it to the modules array in the `config/config.js` file:
````javascript
modules: [
	{
		module: 'MMM-MyNest',
		position: 'bottom_right',	// This can be any of the regions.
									// Best results in one of the side regions like: top_left
		config: {
			// See 'Configuration options' for more information.
			token: '1234567890zbcdefghijkl', //Nest Token - REQUIRED
			thermNum: 3, //Choose which thermostat - REQUIRED if you have multiple thermostats on the same account
			displayName: true, //Display the thermostat name
			displayType: "nest" //Choose either the Nest display or a list
		}
	}
]
````

## Choosing your thermostat
Do not enter a `thermNum:` in your config.js.  The module will list your available thermostats.  You will then be presented with a list of your thermostats to pick from.

![Choose Thermostat](https://cloud.githubusercontent.com/assets/19363185/19137765/4768b484-8b44-11e6-8441-e9b43c3f32fd.png)

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
		<tr>
			<td><code>thermNum</code></td>
			<td>Used to choose which thermostat is shown<br>
				<br><b>Example:</b> <code>2</code>
				<br> This value is <b>REQUIRED only if you have multiple thermostats</b>
			</td>
		</tr>
		<tr>
			<td><code>displayName</code></td>
			<td>Display the thermostat name<br>
				<br><b>Example:</b> <code>true</code>
				<br><b>Default value:</b> <code>false</code>
			</td>
		</tr>
		<tr>
      <td><code>displayType</code></td>
      <td>Choose how the data is displayed<br>
        <br><b>Possible values:</b> <code>"list"</code>, <code>"nest"</code>
        <br><b>Default value:</b> <code>"nest"</code>
      </td>
    </tr>
		<tr>
			<td><code>units</code></td>
			<td>What units to use. Specified by config.js<br>
				<br><b>Possible values:</b> <code>config.units</code> = Specified by config.js, <code>metric</code> = Celsius, <code>imperial</code> =Fahrenheit
				<br><b>Default value:</b> <code>config.units</code>
			</td>
		</tr>
		<tr>
			<td><code>updateInterval</code></td>
			<td>How often this refreshes<br>
				<br><b>Example:</b> <code>60000</code>
				<br> Nest recommends a call every minute or greater.
				<br><b>Default value:</b> <code>60000</code>
			</td>
		</tr>
	</tbody>
</table>

## Using the Akkurat font

The Nest Thermostst's display and the Nest app both use a font called Akkurat.  The module will use this font if available, but as it is a licensed font, it is not included in this repo.  It is optional -- the module will fall back to Roboto if Akkurat isn;t available -- but if you would like to use it, accquire the font on your own in webfopnt format, either woff or woff2.

the font must be named `akkurat-webfont.woff` or `akkurat-webfont.woff2`, and it needs to be in a folder named `Akkurat` in MagicMirror's `fonts` folder.
