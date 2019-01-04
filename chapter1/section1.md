# Functions

##1. Give a real-world example that requires sorting or a real-world example that requires
## computing a convex hull.

### sorting: 
To place students into seats in alphabetical order, their names must be sorted.
### convex hull: 
For a truck that has to deliver to n locations, find the order of locations that the truck should follow to travel the shortest distance to make the deliveries 

## 2. Other than speed, what other measures of efficiency might one use in a real-world
## setting?

Distance, work-completed/time


## 3. Select a data structure that you have seen previously, and discuss its strengths and
## limitations.

### Linked Lists:
Strengths: Adding and removing elements from this list is much faster than other lists. It also allows for an efficient implementation of hash tables that deals with collisions in an effective way.
Limitations: There are no indices, and thus look up time in the worst case is O(N). 

## 4. How are the shortest-path and traveling-salesman problems given above similar?
## How are they different?

Finding the shortest-path and traveling-salesman problems both look for a path that results in the smallest distance travelled. Finding the shortest path, however, has the easiest solutions, in comparison with traveling-salesman. The shortest path can be found, as it is done through GPS or internet routing nodes. However, the traveling-salesman is an NP-complete problem that can only have an approximate solution when put under certain assumptions. This is because it is much more complex, with multiple trucks, the unknown factor of locations for each day, the unknown factor of deliveries for each day, and such.

## 5. Come up with a real-world problem in which only the best solution will do. Then
## come up with one in which a solution that is “approximately” the best is good
## enough.

The best solution is necessary for seating passengers in an airline, based on preferences, keeping families together/nearby, based on the amount paid for the tickets, and such factors.

An approximate solution will do for airlines suggesting flights to passengers going to multiple destinations. Correct airlines must be suggested for a shorter distance and minimum stops to get to the location. However, multiple stops can also be suggested, as passengers can decide.