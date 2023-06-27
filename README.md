# C++ Mapping Software for ECE297

This is a geographical mapping software that visualizes cities across the globe. Designed for commuters in densly populated cities, who travel by car, bus and train. Written using C++, and visualizes data from the OpenStreetMap database API through graphics libraries like GTK and EZGL.

<img src="images/medzoomtoronto.png" alt="View of Toronto, Canada" height="41.5%" width="41.5%" style="border: 2px solid black;"> <img src="images/fullzoomlondon.png" alt="View of London, England" style="border: 2px solid black;">

## Main Features
* Use mouse/buttons to zoom, scroll and pan around the city
* Utilizes Dropdown menu to select between cities
* Visualizes different features such as roads, parks and lakes
* Displays street names, subway stations, points of interest and more
* Finds the optimal route between intersections for commuters
* Displays easy to undertand driving directions to travel the optimal path found
* Search for specific streets or intersections using search bar with autocomplete
* Toggle between dark mode and light mode

## Pathfinding Algorithm

### Describing the Graph Data Strcucture

Information is retrieved through the OpenStreetMaps API and the OSM database to build a graph which represents a map of a city. Each intersection of the city is represented as a node, and each intersection is connected by 1 or more street segments which represent the edges of the graph. Together these two attributes form the basis of our graph for which we were able to visualize and create a pathfinding algorithm.

### Pathfinding using A* Search Algorithm
Our mapping software utilizes the A* pathfinding algorithm approach. Our Pathfinding algorithm makes use of a variety of data structures - specifically, a heap, which is used to store high-priority intersections at the top. Those that contain the minimum travel time are dequeued, and its neigbouring intersections are enqueued until the destination intersection has been found. Since the algorithm is A*, it utilizes a heuristic which takes into account an intersections geometric (Euclidean) distance from destination. Those that are closer to the destination sit near the top of the heap, making our algorithm much more efficient.

### Traveling Salesman/Courier Problem - NP Hard Problem
Given a set of dropoff/pickup points, and a set of start/end intersections, our algorithm attempts to find the optimal path that reaches all the intersections. Since this type of problem is an example of a NP Hard problem, our algorithm finds a few "mediocre" solutions, then continues to make improvements until we end up with a relatively optimal path in a reasonable amount of time.

For our initial "baseline" solution, we try starting at every possible depot(start point), and use a greedy algorithm to always travel to the next closest pickup or dropoff point from the current location. Then, using the best "baseline" solution, we try swapping the order of two random intersections continuously to look for a more optimal path until we run out of time which we set as a hard limit of 50 seconds.

## Contact

Provide contact information (such as an email address or GitHub username) for users to reach out to you if they have any questions, feedback, or issues related to your mapping software.

## Acknowledgments

If you used any external resources, libraries, or code snippets in your mapping software, acknowledge and credit them here. You can also express gratitude to anyone who provided assistance or support during the development process.
