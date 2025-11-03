# What is this?
This is an updated version (python2→python3) of the [Berkeley Pacman](https://inst.eecs.berkeley.edu/~cs188/fa24/projects/) project. It's nearly 1-to-1, so you can follow their documentation.

**Changes:**
- Formatted with Black (pypi)
- Standardized to snake_case

# How do I get started?

### Setup
Follow the instructions in [documentation/setup.md](documentation/setup.md)

### Quick Test
```bash
# From inside main
python pacman.py -l tiny_maze -p SearchAgent -a fn=tiny_maze_search
```
or
```bash
# From the Repository's Root
python pacman.py -l tiny_maze -p SearchAgent -a fn=tiny_maze_search
```

# What files should I edit?

### Files You'll Modify ✏️
- **`main/search.py`** - Implement search algorithms (DFS, BFS, UCS, A*)
- **`main/search_agents.py`** - Implement search problems and heuristics

### Files to Reference 📖
- **`main/util.py`** - Data structures: `Stack`, `Queue`, `PriorityQueue`
- **`main/game.py`** - Game state and mechanics

# How do I run this?

### Using Project Commands
After running the setup, use these commands:
```bash
run pacman           # Launch Pacman game
run autograder       # Test your code
project pacman_examples  # See example commands
```

### Direct Python Commands
You can also run Python directly:

**Test algorithms on different mazes:**
```bash
python pacman.py -l tiny_maze -p SearchAgent -a fn=dfs
python pacman.py -l medium_maze -p SearchAgent -a fn=bfs
python pacman.py -l big_maze -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic
```

**Test specific questions:**
```bash
python autograder.py search_agent -q q1    # Test DFS
python autograder.py search_agent -q q2    # Test BFS
python autograder.py search_agent          # Test everything
```

**Useful flags:**
- `-z 0.5` - Speed up animation
- `-q` - No graphics (faster)
- `--frameTime 0` - Run at max speed

# What do I need to know?

### The Search Problem Interface
```python
start = problem.get_start_state()        # Get starting position
is_goal = problem.is_goal_state(state)   # Check if at goal
successors = problem.get_successors(state)  # Get neighbors

# Each successor is a Transition with:
successor.state   # Next position
successor.action  # 'North', 'South', 'East', 'West'
successor.cost    # Usually 1
```

### Your Functions Return a Path
```python
def depth_first_search(problem):
    # ... your code ...
    return ['North', 'East', 'East', 'South']  # List of actions
```

### Data Structures (from util.py)
```python
from util import Stack, Queue, PriorityQueue

stack = Stack()
stack.push(item)
item = stack.pop()   

queue = Queue()
queue.push(item)
item = queue.pop()    

pq = PriorityQueue()
pq.push(item, priority)
item = pq.pop()      
```

# Common Issues

**Pacman doesn't move?**  
→ Return a list of actions: `['North', 'South', 'East']`

**Infinite loop?**  
→ Track visited states to avoid revisiting

**Tests fail but game works?**  
→ Your solution may not be optimal (BFS/A* should find shortest/cheapest path)

**Need help?**  
→ Check [Berkeley's documentation](https://inst.eecs.berkeley.edu/~cs188/fa24/projects/) for detailed explanations

# Quick Reference

**Algorithms to implement:**
1. Depth-First Search (DFS) 
2. Breadth-First Search (BFS) 
3. Uniform Cost Search (UCS) 
4. A* Search - uses PriorityQueue

**Available mazes:** check the directory `main/layout/` for maze layouts

**Good luck!** 🎮
