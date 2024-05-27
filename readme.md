## Tunnel Lining - Automated Numerical Simulation

### Overview

This code is designed to create numerical models for tunnel linings with varying cavity sizes. It generates .in files for the GPRMax software, which simulates ground-penetrating radar (GPR) data. The cavity sizes range from 0 to 300 mm, and the models cover different sections of the tunnel lining. The tunnel lining model is shown by figure down below

![tunnel lining](assets/pict1.png)

### Purpose

The primary purpose of this code is to automate the creation of input files for GPRMax, allowing for efficient simulation of various scenarios involving different concrete thicknesses, cavity sizes, and cavity positions. These simulations help in analyzing the effects of these variables on GPR signals, which is crucial for detecting and characterizing subsurface features such as cavities. Furthermore, this simulation results can be a training datasets for further analysis such as Deep Learning model.

### Key Parameters

- Concrete Thickness (x): Varies between 100 mm and 300 mm.
- Cavity Size (y): Includes 0, 1, 5, 10, 50, 100, 150, 200, 250, and 300 mm.
- Cavity Position (z): Positioned at 0.2, 0.4, and 0.6 meters along the x-coordinate.
- Cavity Sections (r): Section 1 until 5 become the focus
- Frequencies and Grid Spacing:
    - 400 MHz with dx = 0.017
    - 900 MHz and 1600 MHz with dx = 0.005

### Functionality

1. Importing Libraries:

    - The code utilizes the NumPy library for numerical operations.

2. Defining Parameters:

    - Arrays and lists are defined to specify the variations in cavity sizes and section labels.

3. Loop Structure:

    - Nested loops iterate over concrete thicknesses, sections, cavity sizes, and cavity positions to cover all possible combinations.

4. File Generation:

    - For each combination, the code constructs a file path and opens a new .in file.
    - Common header information, including domain size, grid spacing, materials, and waveform details, is written to each file.
    - Section-specific box definitions are included to represent the tunnel lining and cavities accurately.
