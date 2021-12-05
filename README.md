# donutgraph.js
Animated Donut Graph - jQuery plugin<br>
build upon D3.js<br>

![preview](https://github.com/jpweinerdev/donutgraph.js/blob/main/intro.png)

## jQuery initialization and customization
This plugin requires jQuery (&gt;= 1.8.x) and D3.js (&gt;= v5.4.0)<br>Font Awesome (4.4.x) is used for the handles inner icon symbols.

## Minimal html configuration
```html
<div id="graph"></div>
```

## Custom CSS settings
```html
text {
	font-family: "Helvetica Neue", Helvetica, Arial,sans-serif;
	font: 12px sans-serif;
}
```

## jQuery initialization and customization
This plugin requires jQuery (>= 1.8.x) and D3.js (&gt;= v5.4.0)

```javascript
$("#graph").donutgraph({
	data: [],
	height: 400,
	width: 400,
	colorSetting: ["#33876b","#559559","#77a347","#98b236","#bac024","#dcce12","#e0e0e0"],
	onChange: function (obj) {	
		$('#info').html('Item: '+ obj.label + ' – '+ obj.value);
	}
});
```

## Options and parameters
Parameter | Type | Default | Description
--- | --- | --- | ---
`container` | string | #graph | ID or class of HTML container element (div)
`measureElement` | string | #measure | ID or class of HTML container element (span) for measuring label text
`height` | int | 400 | total height of SVG container
`width` | int | 400 | total width of SVG container
`donutWidth` | int | > 0 < (width/2)-50 | width of donut ring element
`padAngle` | float | 0.02 | space angle between ring segments
`animationDuration` | int | 750 | duration in milliseconds<br>tweening animation
`labelColor` | string | #9e9e9e | label text color (hex)
`accentColor` | array | ["#d81b60","#80c441"] | array with color values (hex)<br>2 settings
`colorSetting` | array | ["#33876b","#559559", ...] | array with color values (hex)<br>> 2 for ring segments 
`useColorRange` | boolean | true | true: use color range as setted in colorSetting<br>false: use 1 color from colorSetting for all segments
`data` | array | [] | data array: [{id: 1, label: "Apples", value: 13.5, color: "#80c441"}]<br>object properties:<br>"id" (string): id<br>"label" (string): item label<br>"value" (int,float): item value<br>"color" (string): hex color value (optional) 

## Events
Parameter | Description
--- | ---
`onChange` | call back function when data changes<br>returns Array of Donut section data<br>[<br>&nbsp;&nbsp;&nbsp;	id: id of current segment data,<br>&nbsp;&nbsp;&nbsp;	label: item label,<br>&nbsp;&nbsp;&nbsp;	value: item value,<br>&nbsp;&nbsp;&nbsp;	valueFormated: item value (string),<br>&nbsp;&nbsp;&nbsp;	percent: item percentage value,<br>]<br>[{id: 0, label: 'Apples', value: 20, valueFormated: '20', percent: '32%'}, ...]

## Methods
Parameter | Description
--- | ---
`update` | update graph<br>method name "update"<br>expects second parameter "data"<br>var data = []; $("#graph").donutgraph("update", data);

## Demo

See working demo on [developer.jpweiner.net](http://developer.jpweiner.net/donutgraph.html).


## Credits

Built on top of [jQuery Boilerplate](http://jqueryboilerplate.com).

## License

[MIT License](http://zenorocha.mit-license.org/) © Zeno Rocha
