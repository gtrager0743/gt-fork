# Developer Log - PA3: Maze Escape

### Entry 1
**Date:** 2026-04-18
**Entry Type:** Setup & Environment Check
**Task worked on:** Repository initialization and environment test.
**Issue encountered:** Setting up the local development environment and verifying the instructor's starter code compiles and runs correctly.
**Error message / symptom:** N/A — Initial project setup and verification phase.
**What I tried:** I forked the repository, cloned it locally, and executed the initial code to observe the functions in action
**Fix / resolution:** Successfully generated and printed a random maze with 'S' and 'E' markers. Everything works and I have a clear plan for implementing recursive DFS logic over the next two weeks.

### Entry 2
**Date:** 2026-04-21
**Entry Type:** Engineering Decision
**Task worked on:** DFS function signature
**Issue or decision:** deciding how to pass the maze and tracking arrays to the recursive function.
**Decision:** pass all vectors by reference using & (e.g., vector<vector<int>>& maze).
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