# 3D Energy Optimization

This C# program utilizes the Monte Carlo method to optimize the energy of a 3D figure formed by four points (A, B, C, D) in space. The energy calculation is based on user-defined functions for `v1(h)` and `v2(l)`.

## Overview

The goal is to find the coordinates of A, B, C, and D that minimize the energy of the 3D figure. The program uses a Monte Carlo optimization approach to explore and converge to the optimal set of coordinates.

## Functions

The energy calculation is determined by two functions:

- `v1(h)`: A user-defined function representing the energy contribution based on the height (Z-coordinate) of each point.
- `v2(l)`: A user-defined function representing the energy contribution based on the distance between pairs of points.

The provided default functions are:

- `v1(h) = 2 * h^2 - 3 * h / 2.0`
- `v2(l) = 1 - l^2` for `0 < l < 1`, and `l^2 - 1` for `l >= 1`

Users can customize these functions based on their specific requirements.

## Project Structure

The program consists of three main classes:

1. **Point3D:** Represents a point in 3D space.
2. **EnergyCalculator:** Calculates the energy of the 3D figure based on user-defined `v1(h)` and `v2(l)` functions.
3. **MonteCarloOptimizer:** Utilizes the Monte Carlo method to find the coordinates of A, B, C, and D that minimize the energy.

## Getting Started

1. Clone the repository to your local machine.
2. Open the project in your C# development environment.
3. Customize the `v1` and `v2` functions in the `EnergyCalculator` class based on your requirements.
4. Build and run the program.

## Results

The program will output the optimized coordinates of A, B, C, and D, along with the corresponding energy.

## Example Usage

```csharp
static void Main()
{
    Console.WriteLine("Starting Monte Carlo optimization...");

    MonteCarloOptimizer optimizer = new MonteCarloOptimizer();
    (Point3D A, Point3D B, Point3D C, Point3D D) bestPoints = optimizer.OptimizeEnergy();

    Console.WriteLine("Monte Carlo optimization completed.");
}
