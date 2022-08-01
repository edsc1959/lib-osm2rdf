# lib-osm2rdf
osm2rdf means: OSM to Relational Data Format.
It is an OSM parser and relational database content generator.
Target Database currently is Postgresql.
# Why this project
There are existing several tools to transform OSM (Open Street Map) data - which are usually existing in XML format - to a more usable relational format, e.g. osm2pgsql (https://wiki.openstreetmap.org/wiki/Osm2pgsql). But in my opinion the relational format is not really optimal.
- usage of positional data. As an example: ways are stored as relation to points. this is causing huge lookup efforts when iterating over ways to get their shape. Better was to either store the coordinates of the waypoints directly (is the same storage amount as a 64-bit key to an existing pont location) or create a materialized view.
