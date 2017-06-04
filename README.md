# Documentation of GeoJSON files
To help users contextualize the scenarios they make in CoAXs, routes, stops, and route/corridor segments can be shown on the map by configuring various GeoJSON files.  All of these files are optional.

### Overview of GeoJSON files

Scenario map

![alt text](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/scenariomap.png "scenario map")

Route map

![alt text](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/routemap.png "route map")

We have five optional features which can show on the CoAXs map area. 

In scenario map:
- (1) **lines**: (type: line) City basic transit network. It is to give the user a basic sense of location. You can use the main subway or bus line
- (2) **stations**: (type: point) The main stations on the (1) lines.  

In route map:
- (3) **trunks**: (type: line) The segment of the routes which we mainly focus on and are going to improve.  
- (4) **routes**: (type: line) The transit routes which pass the (3) trunks.
- (5) **stops**: (type: point) The stops which on the (4) routes.

**We can combine scenario map and route map into one map. **

### Requirement for each files
- **(1) lines**:

-- [GeoJSON for lines](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/lines.geojson). Each line has a unique id.

-- the json file which include the style for each line id. For example, "A" is the line id.
```javascript
{
"A":{
style: {weight: 1.5,
	opacity:0,
	fillOpacity:0,
	color: #696969,
	},
}
```

- **(2) stations**:

-- [GeoJSON for stations](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/stations.geojson). The stations on one line has a unique id.

-- the json file which include the style for each line id. For example, "A" is the line id.
```javascript
{
"A":{
style: {weight: 1.5,
        stroke: false,
	opacity:0,
	fillOpacity:0,
	color: #696969,
	},
}
```

- **(3) segment highlight**:

-- [GeoJSON for highlighted segments](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/trunks.geojson). Each segment highlight has a unique id.

-- the json file which include the style AND the corridor name for each corridor id. For example, "B" is the corridor id.
```javascript
{
  "B": {name: "Mass Ave", 
        style: {weight: 1.5,
                stroke: false,
		opacity:0,
		fillOpacity:0,
		color: #696969,
		},
	},
};
```

- **(4) routes**:

-- [GeoJSON for route](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/routes.geojson). All routes using a given corridor segment should share the same style, so each should have the id of the corridor to which it belongs.

-- the json file which include the style for each corridor id. For example, "B" is the corridor id.
```javascript
{
"B":{
style: {weight: 1.5,
	opacity:0,
	fillOpacity:0,
	color: #696969,
	},
}
```

- **(5) stops**:

-- [GeoJSON for stops](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/stops.geojson). All stops on a given corridor should share the same style, so each stop should have the id of the corridor to which it belongs.

-- the json file which include the style for each corridor id. For example, "B" is the corridor id.
```javascript
{
"B":{
style: {weight: 1.5,
        stroke: false,
        opacity:0,
        fillOpacity:0,
        color: #696969,
        },
}
```



