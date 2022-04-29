# Mapper-65
Large scale GIS Mapping system project created using C++ and OpenStreetMap at the University of Toronto.

The source code for the project cannot be made public due to Academic Offense policies at the University of Toronto. This Repository only contains a demo of the Mapper Project that I created along with teammates Srinidhi Shankar and Prarthona Paul. 

# Contents
- [Software Development Information](#software-development-information)
  * [Languages and Tools](#languages-and-tools)
  * [Programming Paradigm - OOP](#programming-paradigm---oop)
  * [Milestones](#milestones)
  * [OpenStreetMap](#openstreetmap)
- [Mapper-65 Demonstration](#mapper-65-demonstration)
  * [The Go Green Initiative](#the-go-green-initiative)
  * [Constant Complexity Data Access](#constant-complexity-data-access)
  * [GUI Features](#gui-features)
    + [Transit](#transit)
    + [Multiple Maps](#multiple-maps)
    + [Points Of Interest Selection](#points-of-interest-selection)
    + [Search Bar Integration](#search-bar-integration)
    + [Dark Mode](#dark-mode)
    + [Navigation Mode](#navigation-mode)
    + [Help Page](#help-page)
  * [Path Finding](#path-finding)
  * [The Travelling Salesman Problem](#the-travelling-salesman-problem)


# Software Development Information

## Languages and Tools 

1. C++ 
2. GTK (GUI development)

## Programming Paradigm - OOP

1. Extensively used Structs to create various objects for elements like features, points of interest and path tracing data.
2. Created separate header files to split milestone global variables.
3. Abstraction was implemented with functions that were used for streets, features, and pathfinding.

## Milestones

The project was split into four milestones:
1. Data loading
2. GUI implementation
3. Path Finding Algorithms - *A star and Dijkstra's*
4. The Travelling Salesman Problem

The team kept track of various tasks during these milestones through a wiki page and a Trello workflow.

My contribution to the project over the semester (14 weeks):

![image](https://user-images.githubusercontent.com/73911621/165882772-a706311b-1caa-4f39-9aab-7ec70ba78278.png)


## OpenStreetMap

The project used the OpenStreetMap database to parse geographic data. The course team converted XML files to binary files for efficient data accessing. Data were processed using various keywords and structures based on OSM standards.

Reference: https://wiki.openstreetmap.org/wiki/Main_Page

# Mapper-65 Demonstration

## The Go Green Initiative

The map was created with climate impact in mind. The team hopes to expand route finding to subways and buses in order to promote greener traveling. Transit paths will be given precedence and greener roadways will be highlighted when presenting paths to users. A carbon footprint approximate will be calculated and displayed to the user. 
Additionally, the map includes various Points Of Interest that promote greener methods of travel:
1. Bicycle Rentals
2. Electric Vehicle Charging
3. Recycling Bins

## Constant Complexity Data Access

Various data loading functions were created to load important OSM information into data structures. Functions were evaluated based on O complexity analysis

## GUI Features

### Transit

Users can choose to see transit options in a city by clicking on the transit button. The paths were laid out using the OSM database keys for subways and buses, giving accurate paths. 

<img width="958" alt="NewYork_transit" src="https://user-images.githubusercontent.com/73911621/163701642-eda9d4e2-3826-4962-9635-b180f002d78d.PNG">

### Multiple Maps

Maps are loaded in a function through OSM XML map files converted into binary files. Users can change maps and explore different cities around the world. Some maps included are:
1. Toronto
2. New York
3. Sydney
4. Singapore
5. New Delhi
6. Hong Kong
7. Tokyo
  
### Points Of Interest Selection

When searching for POIs, users can select what POIs they want to see from a drop-down menu. All categorized POIs in the users' search area will appear and as the user zooms out, those are the ones that remain. This was a design decision made to keep POI querying fast and intuitive.  If POIs are not present on the user's screen, the nearest POIs are displayed as the user looks around.

https://user-images.githubusercontent.com/73911621/163702592-af32cfc7-ea72-4b22-93cb-fb4bdf550c64.mp4

### Search Bar Integration

The search bar was created using the GTK search bar widget. It supports partial street name inputs and gives suggestions and autocompletes. Users can query partial street names and press enter, the search will consider all possible streets and find common intersections. 

<p align = middle>
<img width="853" alt="Toronto_searchBar" src="https://user-images.githubusercontent.com/73911621/163701688-359bb986-0a16-4f3b-81de-f3be795a13fc.PNG">
  </p>
  
### Dark Mode

A dark mode feature allows eye comfort based on brightness.

<img width="499" alt="Singapore_Light" src="https://user-images.githubusercontent.com/73911621/163702029-c307f46a-fb47-4753-80c6-464f2464bdfa.PNG"><img width="500" alt="Singapore_darkMode" src="https://user-images.githubusercontent.com/73911621/163702033-2e9958e7-5b77-48fb-a56a-98b1a3cfec48.PNG">


### Navigation Mode

The map turns green when in navigation mode. A navigation bar provides important information about the selected from and to, and has an additional feature to swap the two immediately. Detailed directions are presented in a text box on the right, and the path is highlighted as the user goes through the directions.

https://user-images.githubusercontent.com/73911621/163701733-c4f86cd1-4c6e-461b-b7c6-54a4707a7218.mp4

### Help Page

A help page was created using HTML/CSS to give users instructions on how to use the map.

[Git Repo] (https://github.com/PrarthonaPaul/Mapper_Instructions)

## Path Finding

Three algorithms were used to achieve navigation on the map. Breadth-First Search was implemented as an initial solution and then iterated upon.

1. Dijkstra's Algorithm

Dijkstra's algorithm was implemented using a min-heap (priority queue). The following video demonstrates Dijkstra's algorithm working on our map. The highlights are just a visualization tool to see the algorithm working (the actual finding is much quicker than that demonstrated through the highlights). Dijkstra's algorithm uses wavefronts to explore all paths until it finds the best one to the destination. These wavefronts are circular and expand outwards from the source. 

https://user-images.githubusercontent.com/73911621/163704211-7b30bdf2-ca4f-47fe-8df1-9ed3444c7a7b.mp4

2. A Star Algorithm

A Star algorithm was implemented by making slight adjustments to Dijkstra's by including a new dimension of estimation - time remaining. The algorithm was significantly faster for single-source single destination searches. The visualization shows how the algorithm moves in a more focused direction rather than a circular wavefront. 

https://user-images.githubusercontent.com/73911621/163703965-d7ab6e1a-76c8-476a-876a-072dba7df698.mp4

## The Travelling Salesman Problem

The final milestone of the project was related to coding an acceptable solution to the Travelling Salesman Problem using various heuristics. For background, the Travelling Salesman Problem is an NP-complete problem relating to finding the shortest path for given pick-ups and deliveries. Dijkstra's algorithm was expanded to find paths to multiple destinations from a source, all at once. Multi-Destination Dijkstra's, coupled with a greedy algorithm gave an initial solution. 

In order to improve our result path, we iterated through multiple pickup points and implemented a simple multi-start. Additionally, we implemented local perturbations through 2-opt, which improved our results by testing various different swaps between path links. 

Demonstration of a greedy algorithm that takes the nearest neighbor:

![Nearestneighbor (1)](https://user-images.githubusercontent.com/73911621/163704680-fdb10e2e-03ad-4dec-a226-38312f9d1fc2.gif)



For more information on the Travelling Salesman Problem (src): https://en.wikipedia.org/wiki/Travelling_salesman_problem
