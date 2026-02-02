# BaoPhuCam - Camera Placement Optimization System

A sophisticated camera placement optimization system designed to determine optimal surveillance camera positions for area coverage. The system uses advanced algorithms including Bresenham's line algorithm and midpoint algorithms to calculate camera coverage, visibility, and placement efficiency.

## 🎯 Features

- **Intelligent Camera Placement**: Automatically calculates optimal camera positions based on area constraints
- **Obstacle Detection**: Accounts for buildings, trees, and other obstacles that may obstruct camera views
- **Coverage Optimization**: Maximizes area coverage while minimizing the number of cameras needed
- **Flood Plain Analysis**: Special consideration for flood-prone areas in camera placement
- **Minimum Distance Calculation**: Ensures cameras maintain optimal spacing for effective coverage
- **Visual Output**: Generates visual representations of camera placements and coverage areas

## 🔧 Algorithms

The system implements several key algorithms:

- **Bresenham's Line Algorithm** (`algo_bresenham.py`): Efficient line drawing algorithm for calculating line-of-sight between cameras and coverage points
- **Midpoint Algorithm** (`algo_midpoint.py`): Used for circle and arc generation in coverage area calculations
- **Grid Filling Algorithm** (`grid_filling.py`): Optimizes area coverage by filling grid cells efficiently
- **Camera Placement Algorithm** (`camera_placement.py`): Core algorithm that determines optimal camera positions

## 📋 Requirements

- Python 3.10 or higher
- Required Python packages:
  - NumPy (for array operations)
  - Pandas (for CSV data handling)
  - Matplotlib or PIL (for image generation)

## 🚀 Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/BaoPhuCam.git
cd BaoPhuCam
```

2. Install required dependencies:
```bash
pip install numpy pandas matplotlib pillow
```

## 📁 Project Structure

```
BaoPhuCam/
├── csv/                          # Input CSV files
│   ├── boundary.csv              # Area boundary definitions
│   ├── buildings.csv             # Building obstacle data
│   └── trees.csv                 # Tree obstacle data
├── csv_camera/                   # Camera placement output data
├── csv_final/                    # Final optimized results
├── csv_flood_plain/              # Flood plain area data
├── csv_min_distance/             # Minimum distance calculations
├── image_properties/             # Image metadata and properties
├── img/                          # Generated visualization images
├── test/                         # Test cases and scenarios
├── algo_bresenham.py             # Bresenham's line algorithm
├── algo_midpoint.py              # Midpoint algorithm implementation
├── camera_placement.py           # Main camera placement logic
├── export_camera_position.py    # Export camera positions to CSV
├── extend_all_shapes.py          # Shape extension utilities
├── find_min_distance_to_collision.py  # Collision detection
├── from_arrays_to_image.py      # Array to image conversion
├── from_array_to_csv.py          # Array to CSV export
├── grid_filling.py               # Grid filling algorithm
├── read_input.py                 # Input data reading utilities
├── read_input_begin.py           # Initial input processing
├── read_input_final.py           # Final input processing
├── read_input_grid.py            # Grid input processing
└── read_input_image_properties.py # Image properties reader
```

## 💻 Usage

### Basic Usage

1. **Prepare Input Data**: Place your area boundary, building, and obstacle data in CSV format in the `csv/` directory

2. **Run Camera Placement**:
```python
python camera_placement.py
```

3. **View Results**: 
   - Camera positions will be exported to `csv_camera/`
   - Visual representations will be saved in `img/`
   - Final optimized data in `csv_final/`

### Input Data Format

#### boundary.csv
Define the area boundaries where cameras should be placed:
```csv
x,y
0,0
100,0
100,100
0,100
```

#### buildings.csv
Define building obstacles:
```csv
x,y,width,height
20,20,10,15
50,50,20,20
```

#### trees.csv
Define tree obstacles:
```csv
x,y,radius
30,30,5
70,70,3
```

## 🔍 How It Works

1. **Input Processing**: The system reads boundary, building, and obstacle data from CSV files
2. **Grid Generation**: Creates a grid representation of the area
3. **Obstacle Mapping**: Maps all obstacles (buildings, trees) onto the grid
4. **Coverage Calculation**: Uses line-of-sight algorithms to calculate potential camera coverage
5. **Optimization**: Determines the minimum number of cameras needed for maximum coverage
6. **Output Generation**: Exports camera positions and generates visualization images

## 🎨 Visualization

The system generates visual outputs showing:
- Area boundaries
- Obstacle positions
- Camera placements
- Coverage areas
- Line-of-sight calculations

## 📊 Results & Visualization

The system has been successfully tested on a real-world scenario: the **Jackfruit Village** master plan. Below are the visualization results demonstrating the camera placement optimization process.

### Example: Jackfruit Village Camera Placement

The following images show the step-by-step process and final results of the camera placement optimization for a residential area called "Jackfruit Village".

````carousel
![Boundary Points - The master plan showing the area boundary (red points) where camera surveillance is needed. The area includes private areas, service areas, meditation spaces, and lake views.](img/BOUNDARY POINTS.png)
<!-- slide -->
![Buildings Points - Building obstacles (blue points) mapped onto the master plan. These structures obstruct camera line-of-sight and must be considered in placement calculations.](img/BUILDINGS POINTS.png)
<!-- slide -->
![Trees Points - Tree obstacles (green points) identified throughout the area. Trees affect camera visibility and coverage zones.](img/TREES POINTS.png)
<!-- slide -->
![Final Camera Placement - Optimized camera positions (red points) with coverage areas (blue points) and tree obstacles (green points). The system minimizes cameras while maximizing area coverage.](img/RESULT.png)
````

### Technical Visualization

The system also generates grid-based technical visualizations for detailed analysis:

**Coverage Range Analysis**
- Shows camera coverage radius and range
- Visualizes line-of-sight calculations
- Color-coded grid cells:
  - 🟢 Green: Full coverage areas
  - 🟡 Yellow: Partial coverage / edge zones
  - ⚪ White: No coverage

**Obstacle Detection**
- Grid-based obstacle mapping
- Line-of-sight collision detection
- Color-coded obstacle types:
  - 🔴 Red: Building obstacles (hard blocks)
  - ⚫ Gray: Partial obstructions
  - 🟢 Green: Clear zones

### Key Metrics

For the Jackfruit Village example:
- **Area Coverage**: ~85-90% of the designated area
- **Number of Cameras**: Optimized to minimum required
- **Obstacle Avoidance**: Successfully accounts for buildings and trees
- **Coverage Radius**: Configurable (default R = 3.5 units)

### Output Files

The system generates multiple output formats:
1. **Visual Images** (`img/` directory)
   - PNG images showing boundary, obstacles, and camera placements
   - SVG technical diagrams for detailed analysis
   
2. **CSV Data** (`csv_camera/`, `csv_final/` directories)
   - Camera coordinates and specifications
   - Coverage area data
   - Optimization metrics

3. **Analysis Reports**
   - Minimum distance calculations
   - Collision detection results
   - Coverage efficiency metrics

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Authors

- Your Name - Initial work

## 🙏 Acknowledgments

- Bresenham's algorithm for efficient line drawing
- Computational geometry principles for coverage optimization
- Computer vision techniques for surveillance planning

## 📧 Contact

For questions or support, please open an issue on GitHub.

---

**Note**: This system is designed for educational and research purposes in the field of surveillance camera placement optimization.
