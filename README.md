# Documentation of geojson files
This documentation is going to demonstrate what the geojson files need for CoAXs frontend

### What's the geojson files

Scenario map

![alt text](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/scenariomap.png "scenario map")

Route map

![alt text](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/routemap.png "route map")




As the picture above, Geojson files are used to show the points, lines, polygons on the maps. We have five optional features which can show on the CoAXs map area. 

**All these geojson files are optional!**

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

-- [Geojson for lines](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/lines.geojson). Each line has a unique id.

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

-- [Geojson for stations](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/stations.geojson). The stations on one line has a unique id.

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

- **(3) trunks**:

-- [Geojson for trunks](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/trunks.geojson). Each trunck has a unique id.

-- the json file which include the style AND the trunck name for each trunk id. For example, "B" is the trunk id.
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

-- [Geojson for route](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/routes.geojson). Since all the routes which pass one trunk should has same style. So each route should have the trunk id which it passes.

-- the json file which include the style for each trunk id. For example, "B" is the trunk id.
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

-- [Geojson for stops](https://github.com/mitTransportAnalyst/documentation-of-geojson-files/blob/master/stops.geojson). Since all the stops which are on one trunk should has same style. So each stop should have the trunk id which it belongs to.

-- the json file which include the style for each trunk id. For example, "B" is the trunk id.
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



