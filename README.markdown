# Navigate Us

Navigate Us is a navigation system implemented in C++ and Python, designed to find the shortest path between two locations (cities) and estimate travel time based on the chosen mode of transportation (walking, car, or bike). The system uses a graph-based approach with Depth-First Search (DFS) to compute all possible paths, sorts them by distance, and visualizes the shortest path using a Python script.

## Features
- **User Authentication**: Supports sign-in and sign-up with username and password.
- **Transport Modes**: Estimates travel time for walking, car, or bike.
- **Shortest Path Calculation**: Finds all paths between two locations and displays the shortest one.
- **Path Visualization**: Generates a graph of the shortest path using Python's `networkx` and `matplotlib`.
- **Ambiguity Handling**: Allows users to request an alternative path in case of issues like traffic or accidents.

## Prerequisites
- **C++ Compiler**: g++ or any compiler supporting C++11 or later.
- **Python**: Version 3.x with `networkx` and `matplotlib` libraries installed.
- **Input Files**:
  - `data.txt`: List of city IDs and names (format: `ID CityName`).
  - `dis2.txt`: Graph edges with weights (format: `node1 node2 weight`).
  - `userData.bin`: Stores user credentials (created automatically during sign-up).

## Installation
1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd navigate-us
   ```

2. **Install Python Dependencies**:
   ```bash
   pip install networkx matplotlib
   ```

3. **Compile the C++ Code**:
   ```bash
   g++ NAVIGATE_US.cpp -o navigate_us
   ```

## Usage
1. **Prepare Input Files**:
   - Create `data.txt` with city data, e.g.:
     ```
     1 NewYork
     2 Chicago
     3 Boston
     ```
   - Create `dis2.txt` with edge data, e.g.:
     ```
     1 2 100
     2 3 150
     1 3 200
     ```

2. **Run the Program**:
   ```bash
   ./navigate_us
   ```

3. **Follow the Prompts**:
   - Choose to sign in (1) or sign up (2).
   - Enter username and password.
   - Select a mode of transport (1: Walk, 2: Car, 3: Bike).
   - Input source and destination location IDs from `data.txt`.
   - View the shortest path, distance, and estimated travel time.
   - If prompted, indicate if there’s an ambiguity (e.g., traffic) to get an alternative path.
   - A graph of the path will be saved as `graph.png`.

## File Structure
- `path.h`: Contains the DFS-based pathfinding logic and global variables.
- `NAVIGATE_US.cpp`: Main program with user authentication, transport mode selection, and pathfinding.
- `ROUTEGRAPH.py`: Python script to visualize the shortest path as a graph.
- `data.txt`: Input file with city IDs and names.
- `dis2.txt`: Input file with graph edges and weights.
- `userData.bin`: Stores user credentials (created during sign-up).
- `out.txt`: Temporary file with the shortest path for visualization.
- `<username>.txt`: Created for each user during sign-up (currently unused).
- `graph.png`: Output file with the visualized path.

## Limitations
- Inefficient file handling due to repeated file opening/closing.
- Uses DFS to find all paths, which is computationally expensive for large graphs.
- Stores passwords in plaintext in `userData.bin`, which is insecure.
- Hardcoded velocity values may not reflect real-world scenarios.
- Limited error handling for invalid inputs or missing files.
- Program exits after one navigation query.

## Future Improvements
- Use Dijkstra’s or A* algorithm for faster shortest path calculation.
- Implement secure password storage (e.g., hashing).
- Add error handling for file operations and user inputs.
- Allow multiple navigation queries without exiting.
- Enhance the Python visualization to include edge weights or display interactively.
- Replace `goto` statements with structured control flow for better maintainability.

## Authors
- Taha Shah
- Mir Osama Ali
- Jalil Abbas

## License
This project is licensed under the MIT License.