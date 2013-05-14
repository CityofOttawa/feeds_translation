Feeds Translation
=================

Allows Feeds to import nodes and apply Content Translation to them (i.e. tnid)

Installation
------------

1. Download Feeds 2.0-alpha8 or higher
2. Apply the following patch: http://drupal.org/files/1994654-add-plugin-alter.patch
3. Enable feeds_translation


Usage
-----

1. Create a English Feeds Mapping (or language or your choice) -> Following field needs to exsist: ```GUID``` (your unique record selector for the Feeds Mapping).

2. Create a French Feeds Mapping (or language of your choice) -> Following fields needs to exsist: ```GUID``` (your unique record selector for the Feeds Mapping) and ```Translation node id```.  Translation node is source name can be any value as it will be overwirten in step 3. Example: [Source: Blank Source 1] [Target: Translation node id].

3. Go to the Feeds Tamper page for the French Feeds Mapping and for the ```Translation node id``` field add the "Get TNID from GUID" plugin

4. Run the English Feed

5. Run the French Feed

When the French feed runs the Tamper plugin will take the GUID and look it up in the Feeds table to find the English/original node and apply the nid of the English node to the tnid of the French node.

The English and French GUID field should have the same values.  Best way to do this is have your multilingual data in a single row:
ID/GUID | Title (Eng) | Title (Fre) | Description (Eng) | Description (Fre)
--------|-------------|-------------|-------------------|-------------------
