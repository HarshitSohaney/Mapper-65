# Mapper-65
Large scale GIS Mapping system project created using C++ and OpenStreetMap at the University of Toronto

This Repository contains a demo of the Mapper Project that I created along with teammates Srinidhi Shankar and Prarthona Paul. 

# Contents



# Software Development Information

## Languages and Tools 

1. C++ 
2. GTK (GUI development)

## Programming paradigm - OOP

1. Extensively used Structs to create various objects for elements like features, points of interests and path tracing data.
2. Created seperate header files to split milestone global variables.
3. Abstraction was implmented with functions that were used for streets, features and path finding.

## Milestones

The project was split into four milestones:
1. Data loading
2. GUI implementation
3. Path Finding Algorithms - *A star and Dijkstras*
4. The Travelling Salesman Problem

The team kept track of various tasks during these milestones through a wiki page and a trello workflow.

## OpenStreetMap

The project used the OpenStreetMap database to parse geographic data. The course team converted xml files to binary files for efficient data accessing. Data was processed using various keywords and structures based on OSM standards.

Reference: https://wiki.openstreetmap.org/wiki/Main_Page

# Mapper-65 Demonstration

## The Go Green Initiative

## Constant complexity data access

## GUI Features

### Transit

Users can choose to see transit options in a city by clicking on the transit button. The paths were laid out using the OSM database keys for subways and buses, giving accurate paths. 

<img width="958" alt="NewYork_transit" src="https://user-images.githubusercontent.com/73911621/163701642-eda9d4e2-3826-4962-9635-b180f002d78d.PNG">

### Multiple Maps
### POI Selection
### Search bar integration

The search bar was created using the GTK search bar widget. It supports partial street name inputs, and gives suggestions and autocompletes. Users can query partial street names and press enter, the search will consider all possible streets and find common intersections. 
<img width="853" alt="Toronto_searchBar" src="https://user-images.githubusercontent.com/73911621/163701688-359bb986-0a16-4f3b-81de-f3be795a13fc.PNG">

### Dark Mode
### Navigation Mode

The map turns green when in navigation mode. A navigation bar provides important information about the selected from and to, and has an additional feature to swap the two immediately. Detailed directions are presented in a text box on the right, and the path is highlighted as the user goes through the directions.

https://user-images.githubusercontent.com/73911621/163701733-c4f86cd1-4c6e-461b-b7c6-54a4707a7218.mp4

### Help Page

## Path Finding

## The Travelling Salesman Problem





