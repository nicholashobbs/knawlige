# cs theory

## data structures
arrays, linked lists, stacks, queues, trees, graphs, heaps, hash tables, tries, etc.

## algorithmic complexity
study of space time and resources required by algorithms
**big o notation** is used to describe the upper bound of complexity of an algorithm in terms of the input size n and the number of operations performed by the algorithm as a function of n 
**omega notation** is used to describe the lower bound of the complexity
**theta notation** is always between omega and big o


quadratic complexity in terms of runtime is O(n^2)
logarithmic complexity in terms of runtime is O(logn)
linear complexity in terms of runtime is O(n)
constant complexity in terms of runtime is O(1)
linearithmic complexity in terms of runtime is O(nlogn)

a sort is **stable** if it preserves the order of equal elements
a sort is **in-place** if it uses constant space
a sort is **adaptive** if it takes advantage of the fact that the input is already partially sorted

**bubble sort** is stable, in-place, and adaptive. it works by repeatedly swapping adjacent elements that are out of order. It has a worst case time complexity of O(n^2) and a best case time complexity of O(n) and space complexity of O(1)

**selection sort** is not stable, in-place, and not adaptive. it works by repeatedly finding the minimum element from unsorted part and putting it at the beginning. it has a worst case time complexity of O(n^2) and a best case time complexity of O(n^2) and space complexity of O(1)

**insertion sort** is stable, in-place, and adaptive. it works by inserting each element into its proper place in the sorted part of the array. it has a worst case time complexity of O(n^2) and a best case time complexity of O(n) and space complexity of O(1)

**merge sort** is stable, not in-place, and not adaptive. it works by dividing the array into two halves, sorting each half, and then merging the two sorted halves. it has a worst case time complexity of O(nlogn) and a best case time complexity of O(nlogn) and space complexity of O(n)

**quick sort** is not stable, in-place, and not adaptive. it works by picking a pivot element and partitioning the array around the pivot such that all elements less than the pivot come before it and all elements greater than the pivot come after it. it has a worst case time complexity of O(n^2) and a best case time complexity of O(nlogn) and space complexity of O(logn)

**heap sort** is not stable, in-place, and not adaptive. it works by building a max heap from the input data. the largest item is stored at the root of the heap. it has a worst case time complexity of O(nlogn) and a best case time complexity of O(nlogn) and space complexity of O(1)
## graph algorithms

**depth first search** is a graph traversal algorithm that starts at the root node and explores as far as possible along each branch before backtracking. it uses a stack to keep track of next nodes to explore. At each node, it checks to see if it has reached the goal, if not, adjacent nodes are added to the stack. it has a time complexity of O(V+E) and space complexity of O(V). it is also called pre-order traversal.

```python
def dfs(graph, start, goal):
    stack = [start]
    while stack:
        node = stack.pop()
        if node == goal:
            return True
        for adjacent in graph[node]:
            stack.append(adjacent)
    return False
```

**breadth first search** is a graph traversal algorithm that starts at the root node and explores all of the neighbor nodes at the present depth prior to moving on to the nodes at the next depth level. it has a time complexity of O(V+E) and space complexity of O(V). it is also called level-order traversal.

```python
def bfs(graph, start, goal):
    queue = [start]
    while queue:
        node = queue.pop(0)
        if node == goal:
            return True
        for adjacent in graph[node]:
            queue.append(adjacent)
    return False
```

**dijkstra's algorithm** is a graph traversal algorithm that finds the shortest path between two nodes in a graph. it has a time complexity of O(V^2) and space complexity of O(V)

```python
def dijkstra(graph, start, goal):
    distances = {node: float('inf') for node in graph}
    distances[start] = 0
    while distances:
        current_node = min(distances, key=distances.get)
        if current_node == goal:
            return distances[current_node]
        for adjacent, weight in graph[current_node].items():
            new_distance = distances[current_node] + weight
            if new_distance < distances[adjacent]:
                distances[adjacent] = new_distance
        del distances[current_node]
    return float('inf')
```

**bellman-ford algorithm** is a graph traversal algorithm that finds the shortest path between two nodes in a graph. it has a time complexity of O(VE) and space complexity of O(V)

**topological sort** is a graph traversal algorithm that sorts the nodes in a directed acyclic graph (DAG) in such a way that if there is an edge from node A to node B, then A appears before B in the ordering. it has a time complexity of O(V+E) and space complexity of O(V)

**kruskal's algorithm** is a graph traversal algorithm that finds the minimum spanning tree of a graph. it has a time complexity of O(ElogE) or O(ElogV) and space complexity of O(E) or O(V)


**maximum flow** is a graph traversal algorithm that finds the maximum flow through a graph. it has a time complexity of O(VE^2) and space complexity of O(V)

**maximum clique** is a graph traversal algorithm that finds the maximum clique in a graph. it has a time complexity of O(3^V/2) and space complexity of O(V). A clique is a subset of nodes in a graph such that every pair of nodes in the subset is connected by an edge


## dynamic programming
dynamic programming is a method for solving a complex problem by breaking it down into a collection of simpler subproblems, solving each of those subproblems , and storing their solutions using a memory-based data structure such as an array or hash table. the next time the same subproblem occurs, instead of recomputing its solution, one simply looks up the previously computed solution, thereby saving computation time at the expense of storage space

## parallel computing
parallel computing is a method to run multiple calulations at once. there are two types of parallel computing: data parallel and task parallel. data parallel is when the same operation is performed on different pieces of data. task parallel is when different operations are performed on the same piece of data
## approximation algorithms
approximation algorithms are algorithms that find a solution that is close to the optimal solution in polynomial time. they are used when the optimal solution is too expensive to compute

## computational geometry
computational geometry is the study of algorithms that can be used to solve geometric problems. it is used in computer graphics, geographic information systems, robotics, and computer-aided design

## NP-completeness
a problem is NP-complete if it can be reduced to any other NP problem in polynomial time. NP-complete problems are the hardest problems in NP. they are hard to solve, but easy to verify. NP-complete problems include the traveling salesman problem, the knapsack problem, and the vertex cover problem. a P problem is a problem that can be solved in polynomial time. a NP problem is a problem that can be verified in polynomial time. a NP-complete problem is a problem that is both in NP and NP-complete

## recursion
recursive algorithms are algorithms that call themselves. they are used to solve problems that can be broken down into smaller versions of the same problem

## greedy algorithms
greedy algorithms are algorithms that make the locally optimal choice at each stage with the hope of finding a global optimum. they are used to solve optimization problems. they are not guaranteed to find the global optimum, but they are fast and easy to implement


# linux

• cd: Change the directory
• pwd: Print the working directory
• ls: List the contents of a directory
• mkdir: Create a new directory
• rmdir: Remove an empty directory
• cp: Copy files
• mv: Move or rename files
• rm: Remove files
• grep: Search for patterns in files
• find: Find files by name
• head: View the first few lines of a file
• tail: View the last few lines of a file
• sort: Sort lines in a file
• cat: Concatenate files and print to standard output
• echo: Print a line of text
• chmod: Change file permissions
• chown: Change file ownership
• sudo: Execute a command as the root user
• su: Switch user
• clear: Clear the terminal screen
• man: View the manual page for a command
• vim: Text editor
• nano: Text editor
• top: View running processes
• ps: List running processes
• kill: Stop a running process
• ssh: Connect to a remote server
• scp: Copy files to/from a remote server
• date: Print the current date
• cal: Print a calendar for the current month
• mount: Mount a filesystem
• umount: Unmount a filesystem
• tar: Create or extract an archive
• gzip: Compress or decompress files
• passwd: Change a user’s password
• wget: Download files from the web
• curl: Retrieve data from the web
• locate: Find files by name
• env: View environment variables
• which: View the location of binaries
• alias: Create a shortcut for a command
• uname: Print information about the system
• df: View disk usage information
• free: View memory usage information
• ifconfig: View network configuration information
• ping: Test network connectivity
• shutdown: Shut down the system
• reboot: Reboot the system
• chroot: Change the root directory
• nohup: Run a command in the background.

## linux filesystem

The Linux filesystem is a hierarchical structure that starts from the root directory and contains all of the other directories and files. The root directory is the topmost directory in the filesystem and it contains subdirectories which form the basis of the entire filesystem. Each subdirectory contains other subdirectories and files.

The purpose of each directory is to store specific types of data or to provide a specific function. 

/bin directory stores all the executable programs that are available to users
/etc directory stores system configuration files
/home directory stores user data
/usr directory contains user commands and libraries
/dev directory contains device files, such as hard drives
/proc directory stores information about currently running processes.
/var: Stores variable data, such as log files
/sbin: Stores system administration commands and programs
/tmp: Stores temporary files
/boot: Stores bootloader files
/lib: Stores library files
/opt: Stores optional add-on packages
/mnt: Used to mount external storage devices



# windows commands
ctrl shift esc opens task manager


## command line
cmd is for basic commands, powershell is a scripting language for task automation. Powershell has more capabilities, such as the ability to create
## cmd cheat sheet
 CLS – Clears the screen • CMD – Displays another command prompt • COLOR – Sets the text and background color • PROMPT – Changes the command prompt • CD – Change directory • DIR – List files in the current directory • MD – Make a directory • RD – Remove a directory • MOVE – Move files from one directory to another • COPY – Copy files • DEL – Delete files • TYPE – Display the contents of a file • REN – Rename a file • SORT – Sort the contents of a file • FIND – Search for text within a file • OPENFILES – Display the current open files list or disconnect open files • SHUTDOWN – Shutdown the computer • TASKLIST – List the currently running processes • TASKKILL – End a running process • NETSTAT – Display active TCP connections • IPCONFIG – Display IP configuration information • PING – Send a test message to another computer • TRACERT – Trace the path between two computers • PATH – Display and change the path • SET – Display and set environment variables • ASSOC – Change file associations • ATTRIB – Change file attributes

## powershell cheat sheet

Get-Command: Lists all available commands
Get-Help: Displays help information for a specific command
Get-Alias: Lists all aliases for a specific command
Set-Alias: Creates a new alias for a command
Get-ChildItem: Lists all the items in a directory
Set-ExecutionPolicy: Sets the execution policy for PowerShell
Get-Process: Lists all running processes
Invoke-Command: Runs a command on one or more remote computers
Get-Service: Lists all Windows services
Set-Item: Creates or modifies an item in a specified location
New-Item: Creates a new item in a specified location
Remove-Item: Deletes an item from a specified location
Update-Help: Downloads and installs the newest help files
Get-Content: Gets the content of the specified item
Set-Content: Sets the content of the specified item
Invoke-Expression: Runs commands or expressions on the local computer
Start-Process: Starts one or more processes on the local computer
Start-Service: Starts one or more services on the local computer
Stop-Process: Stops one or more running processes
Stop-Service: Stops one or more services
Get-EventLog: Gets events and event logs from local and remote computers
New-EventLog: Creates a new event log and a new event source on a local or remote computer
Get-PfxCertificate: Gets a certificate from a Personal Information Exchange (PFX) file
Set-Variable: Sets a variable in the current session
New-Variable: Creates a new variable with the specified name and value
Get-WmiObject: Gets instances of Windows Management Instrumentation (WMI) classes or information about the available WMI classes
Invoke-WmiMethod: Calls a method of a WMI class
Set-WmiInstance: Creates or updates an instance of a WMI class
Remove-WmiObject: Deletes an instance of a WMI class
Set-ExecutionPolicy: Sets the execution policy for the shell
Set-Location: Sets the current working location. Out-File: Sends output to a file
Export-Csv: Converts objects into a series of comma-separated values (CSV) and sends the output to a file

### shortcuts
## `win + r` 
is run shortcut

- type in control for control panel
- type in msconfig for system configuration
- type in regedit for registry editor
- type in services.msc for services
- type in devmgmt.msc for device manager
- type in diskmgmt.msc for disk manager
- type in eventvwr.msc for event viewer
- type in ncpa.cpl for network connections
- type in perfmon.msc for performance monitor
- type in taskmgr for task manager

`win + x` is power user menu

`win + e` is file explorer

`win + l` is lock

`win + i` is settings
`win + tab` is task view

`alt + tab` is switch between apps

# vscode

- `ctrl + k + s` is keyboard shortcuts
- `ctrl + alt + up` or down arrow adds cursor above or below
- `ctrl + k v` opens preview to the side
# unorganized

## imperative
describing every step of how to do something

## declarative
describing what should be done


