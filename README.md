# Maze Router - Lee's Algorithm

## Overview

This project implements a **grid-based maze router** using **Lee's algorithm** to find the shortest path between two pins on the **same routing layer**. The system avoids obstacles and accounts for direction-based costs.

Currently, the router supports:

- **Same-layer routing only** 
- **A single net with 2 pins**
- **Obstacle avoidance**
- **cost penalties**

The project is implemented in Python and structured for extension to support multi-layer and multi-net scenarios in the future.

---

## Input File Format

The router expects an input file named `input1.txt` with the following format:

```
<rows>, <cols>, <DirectionPenalty>, <ViaPenalty>
OBS (<layer>, <row>, <col>)
OBS (<layer>, <row>, <col>)
...
net1 (<layer>, <row>, <col>) (<layer>, <row>, <col>)
```

### Example:
```
5, 5, 1, 10
OBS (0, 1, 2)
OBS (0, 2, 2)
OBS (0, 3, 2)
net1 (0, 0, 2) (0, 4, 2)
```

> ⚠️ Axis format: **(layer, row, col)**  
> Internally: `grid[layer][row][col]`

---

## How to Run

1. Place your input in a file named `input1.txt` in the same directory as the script.
2. Run the script using Python:
   ```bash
   python maze_router.py
   ```
3. You’ll see:
   - Grid dimensions and routing penalties
   - Obstacle positions
   - Loaded net endpoints
   - Path coordinates (if found)
   - Total cost of the path

---

## Features

- **Lee’s algorithm** for shortest-path routing
- **Obstacle parsing** and detection
- **Penalty costs** for non-preferred routing directions
- **Back-propagation** to recover the final route
- **Console output** of the routed coordinates

---

## Limitations

- Only supports:
  - **Same-layer routing**
  - **One net with two pins**
- No support for:
  - **Multiple nets**
  - **Vias or multi-layer routing**
  - **Rip-up and re-route**
  - **Visualization or output file writing**

---

## Future Work

Planned improvements:

- Support for multi-pin and multi-net routing
- Multi-layer routing with via penalties
- Rip-up and re-route strategies
- Routing order heuristics (Bonus)
- Routing result export and visualization
- GUI or web-based visualization of routing results

---

## Project Details

- Course: **CSCE3304 – Spring 2025**
- Project: **Maze Routing with Lee’s Algorithm**
- Status: **Milestone 1**
- Repository initialized with basic routing functionality

---

## Authors

*Mohamed Ahmed, Youssef Elmahdy, Hussien Heggi *

---

## License

This project is licensed for academic use only. Redistribution or commercial use is not permitted without explicit permission.
