
# Crafting Prototype

## Dungeon Generation
Locations are generated from a combination of localized themed cells and 
general cells, ie. localized being the type of construction or resource the
floor is made of, and general being wood or other universal resource.

The input data used provides cell types for which the location converts into
local thematic data.

This data is linked via a description in the tile legend (source generation
data) and dungeon legend, a set of data generated by surrounding influences
such as location, zone theme, scenario theme.

Due to how the generation system works, often multiple colors must be used to 
produce a desired single output, i.e. two floor colors to describe a single 
floor type. This is handled by the tile legend so the dungeon need not be aware.

The list of types presents the game with potential theme and experience and the 
more descriptive it can be, the wider range of outputs. 

The code will need some level of fall back as during development it is likely 
that the pairing of cell generation and matched dungeon legends will go out of 
sync. This should be flagged as a warning to help keep track and update as 
needed.

valid name list:

### Name Word Legend:
Tag           | Description
------------- | -------------
int          |internal space
ext          |external space
floor        |solid walkable space
wall         |solid non-walkable space
hole         |hollow drop to whatever unseen lies below
bridge       |constructed or natural crossing of a hole
river        |directionally flowing liquid
pond         |non-flowing liquid
natural      |wild and natural with no manipulation
worked       |natural but manipulated
crafted      |constructed for purpose
plant        |vegetation
corridor     |passageway
room         |umm, a room
door         |door way with or without door in place
bed          |place to sleep
chair        |place to sit
table        |place to place stuff
statue       |construct depicting something of importance
hidden       |unseen element 
dense        |heavy element that complicates vision and/or movement

### Codes:
Type    | ID Range
------------- | -------------
Special |     -2 ->  -99
Floor   |   -100 ->  -999
Wall    |    100 ->   999
Light   |  -1001 -> -1200
Item    |   1000 ->  4999
Fixture |  -1000 -> -5000
Creature|   5001 ->  8000

### Fixture List:
Fixture         |   ID
------------- | -------------
Exit:           |   -1000
Door Standard   |   -1201
Door Heavy      |   -1202
Door Secret     |   -1203

