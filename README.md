# CPD Zones Tiles

Map tiles showing the different zones that the Chattanooga Police Department serves.

# Usage

Example usage with Leaflet is as follows:
```javascript
var southWest = L.latLng(34.9816, -85.4719);
var northEast = L.latLng(35.217, -85.0462);
var center = L.latLng(35.0657, -85.241);
var bounds = L.latLngBounds(southWest, northEast);

var map = L.map('map', {
  maxZoom: 18,
  minZoom: 11,
  maxBounds: bounds,
  center: center,
  zoom: 12
});


L.tileLayer('./tiles/{z}/{x}/{y}.png', {
    attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Zone data &copy; City of Chattanooga, Imagery © <a href="http://mapbox.com">Mapbox</a>'}).addTo(map);

map.fitBounds(bounds);
```

The tiles only include the area needed to show the boundaries for the zones. You will need to set a max bounds for whatever you use to display the map tiles. Boundaries are included in the example above.

## Building

These tiles are based off of the [osm-bright](https://github.com/mapbox/osm-bright) project built with OpenStreetMap data.

Follow the instructions for building osm-bright. Add `CPDZones.geojson` from this repository as a data source within your TileMill project for osm-bright and add then styles from `CPDZones.mss` to complete styling.

## License

Map data © OpenStreetMap contributors, CC-BY-SA
Zone data © City of Chattanooga
Imagery © Mapbox
Code for this repository is under MIT License. See LICENSE for more details.

## Disclaimer

The data available on this website, including GIS data, maps, tables, numbers, graphics, and text (hereinafter collectively referred to as the "Information"), is provided AS IS and for you to view, access, copy, distribute and otherwise use the Information at your own risk. City of Chattanooga and its affiliated entities, elected and appointed officers, officials, employees and agents make no representation or warranty of any kind regarding this website or Information, explicit or implied.

