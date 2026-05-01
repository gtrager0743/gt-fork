# Developer Log - PA3: Maze Escape

### Entry 1
**Date:** 2026-04-18
**Entry Type:** Bug Fix
**Task worked on:** Repository initialization and environment test.
**Issue encountered:** Setting up the local development environment.
**Error message / symptom:** couldn't get the fork to work
**What I tried:** I googled how to fork a repository, cloned it locally, and reviewed the initial code
**Fix / resolution:** Successfully generated and printed a random maze with 'S' and 'E' markers. Everything works and I have a good idea how im going to implement recursive DFS logic over the next two weeks.

### Entry 2
**Date:** 2026-04-21
**Entry Type:** Engineering Decision
**Task worked on:** DFS function signature
**Issue or decision:** deciding how to pass the maze and tracking arrays to the recursive function.
**Decision:** pass all vectors by reference using & (example: vector<vector<int>>& maze).
**Reasoning:** copying the whole 2D maze for all steps requires a lot of memory use and could cause a crash or slow performance with large grids.

### Entry 3
**Date:** 2026-04-23
**Entry Type:** Edge Case
**Task worked on:** visited tracking and exit detection
**Issue or decision:** how will i stop recursion if it gets stuck in a loop between two open cells.
**What I tried:** originally i was checking for the exit only, but realized the recursion could still loop forever after testing it.
**Fix / resolution:** added a check for the visited array at the top. If already true, returns false to break loop. I also added the goal check to return true when the current (r, c) matches the exit coordinates.

### Entry 4
**Date:** 2026-04-24
**Entry Type:** Bug Fix
**Task worked on:** recursive direction loop.
**Issue or decision:** the DFS was only moving in one direction and stopping.
**Error message / symptom:** just generally breaks the whole program.
**What I tried:** I tried manually calling the function for NSEW, but it made the code really long.
**Fix / resolution:** for loop from 0 to 3. Calculate the neighbor coordinates nr = r + dr[i] and nc = c + dc[i]. This loop checks all directions for every step instead of manually doing it.

### Entry 5
**Date:** 2026-04-26
**Entry Type:** Engineering Decision
**Task worked on:** tracking for path reconstruction.
**Issue or decision:** How to store the path so the program can print it later.
**Decision:** I'm assigning the current coordinates (r, c) as the parent of the neighbor (nr, nc) right before the recursive call.

### Entry 6
**Date:** 2026-04-27
**Entry Type:** Edge Case
**Task worked on:** main function integration.
**Issue or decision:** DFS start point = 'S' coordinates provided by the generator.
**What I tried:** I was gonna hardcode a start at (0,0), then I reread the instructions and realized S and E have to be randomly placed on boundaries.
**Fix / resolution:** used the ent_r and ent_c variables extracted from the entrance pair to achieve this. it makes sure that the recursion starts on the correct boundary cell marked 'S' regardless of where it is randomly generated.