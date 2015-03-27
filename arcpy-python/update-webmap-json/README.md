Python Script to update a web map (proof of concept)
=========================

## Instructions

1. This script relies on the urllib, urllib2, and json modules
2. This script is designed to be run through an IDE

3. Access the data of your web map as JSON using: http://www.arcgis.com/sharing/rest/content/items/<web map ID>/data?f=pjson
4. replace the following in the JSON using a text editor(See sample JSON below):

true > True
false > False
null > None
5. On line 96, replace "Replace with JSON, remove the quotes" with your edited JSON
5. Run the script and input your username, password, and web map title



## Use Case

This script is useful for someone who is not familiar with python but needs to update their existing web map, not through the UI of ArcGIS Online. This is a workaround for BUG-000085088.

This is often required if a service that was previously accessible has been turned off or removed. If you do not care about maintaining your existing web map ID, simply save a copy of the web map.

NOTE: This script assumes that there is ONLY one web map in your content(all folders) with this title.

## Sample JSON

{
    "applicationProperties": {
        "viewing": {
            "basemapGallery": {
                "enabled": True
            },
            "routing": {
                "enabled": True
            },
            "measure": {
                "enabled": True
            }
        }
    },
    "operationalLayers": [],
    "baseMap": {
        "baseMapLayers": [
			{
                "opacity": 1,
                "url": "http://services.arcgisonline.com/ArcGIS/rest/services/Canvas/World_Light_Gray_Base/MapServer",
                "id": "World_Light_Gray_Base_4394",
                "visibility": True,
                "itemId": "ed712cb1db3e4bae9e85329040fb9a49"
            }
        ],
        "title": "Sample Web Map"
    },
    "version": "1.9"
}
