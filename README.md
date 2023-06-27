# C++ Mapping Software for ECE297

This is a geographical mapping software that visualizes cities across the globe. Designed for commuters in densly populated cities, who travel by car, bus and train. Written using C++, and visualizes data from the OpenStreetMap database API through graphics libraries like GTK and EZGL.
| Toronto, Canada | London, England |
|:-----------------:|:-----------------:|
|<img src="images/medzoomtoronto.png" alt="View of Toronto, Canada" height="80%" width="80%"> | <img src="images/fullzoomlondon.png" alt="View of London, England"> |
 

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

### The Travelling Salesman (NP - Hard Problem)
The Travelling Salesman Problem (TSP) expands upon our A* pathfinding algorithm to find the optimal route for a courier delivering packages. Given a handful of starting locations, and many pickup/dropoff locations, our algorithm was designed to calculate the most optimal path that visits all the required intersections. Since this problem is very complex, our algorithm took an iterative approach, coming up with hundreds of solutions and annealing them until the most optimal route is found within its given time-limit. This approach uses a "hill-climbing" technique to ensure that solutions are not found within local minima, and the entire solution space is explored to come up with the best solution possible within the given timefram

## Screenshots
| Toronto, Canada | London, England |
|:-----------------:|:-----------------:|

## Contact

Provide contact information (such as an email address or GitHub username) for users to reach out to you if they have any questions, feedback, or issues related to your mapping software.

## Acknowledgments

If you used any external resources, libraries, or code snippets in your mapping software, acknowledge and credit them here. You can also express gratitude to anyone who provided assistance or support during the development process.
