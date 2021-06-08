# Subflow for a Web of Things Weatherstation

This module provides a node which contains a subflow for realizing a weatherstation with support for the Web of Things Thing Description (WoT TD).
It uses CoAP (IPv6) multicast discovery in the local network to first retrieve TDs from `/.well-known/wot-thing-description` and then query the respective devices if they provide one of a number of supported types of sensor readings.
These kinds of sensor readings are identified by their semantic `@type` and can either be `saref:Temperature`,  `saref:Humidity` or `saref:Water`.
The retrieved sensor values are displayed in a Node-RED dashboard tab and (optionally) on a display.
To support the latter, however, a specific python script is needed which is why this functionality is disabled by default.

Both the modules `node-red-contrib-wot-discovery` and `node-red-node-ui-table` are needed as dependencies which will be installed alongside this subflow.
