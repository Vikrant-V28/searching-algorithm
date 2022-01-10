# searching algorithms
# Binary Search
* Binary Search is searching the sorted list by repeatedly dividing the search interval in half.
* We will use recursion to implement the algorithm.
* During each iteration we take the middle element, compare it with the searched value, then continue the process for the corresponding half.

```python3
def binary_search(list, l, r, x):
    if r >= l: 
        mid = l + (r - l)//2
        if list[mid] == x:
            return mid
        elif list[mid] > x:
            return binary_search(list, l, mid-1, x)
        else:
            return binary_search(list, mid+1, r, x)
    else:
        return -1
    # -1 returned if no match found.
        
nums = [2, 5, 8, 10, 40, 25]
x = 10
print(binary_search(nums, 0, len(nums)-1, x))
```
# DFS
* DFS is a search algorithm for graphs and trees.
* Let's consider a graph that is represented using an adjacency list, which shows which vertices are connected.
* The path variable keeps a list of vertices already visited so that the function does not visit a vertex twice.
* It also shows the path that the depth-first search algorithm took to find all the vertices.

```python3
def dfs(graph, vertex, path=[]):
    path += [vertex]

    for neighbor in graph[vertex]:
        if neighbor not in path:
            path = dfs(graph, neighbor, path)

    return path

# a sample graph
G = {1: [2, 3], 2: [4, 5], 3: [5], 4: [6], 5: [6], 6: [7], 7: []}
print(dfs(G, 1))
```
