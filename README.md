# Airport Runway Simulation

This project simulates an airport runway system, managing the departure of planes and monitoring their fuel levels. The simulation includes planes with unique identifiers, a queue for departing planes, a separate queue for planes that have departed, and a queue for planes that lack sufficient fuel to take off.

## Project Structure

- **Plane**: Represents an individual plane, with properties for unique identification, fuel amount, and time spent in the departure queue.
- **Airport**: Manages the planes, runway, fuel, and simulation parameters. It contains methods to add new planes to the queue, check the runway status, process plane departures, and print simulation results.

### Class Descriptions

1. **Plane Class**
    - **Attributes**:
        - `id`: Unique identifier of the plane.
        - `fuel`: Amount of fuel for the plane.
        - `queueTime`: Time spent in the departure queue.
    - **Methods**:
        - `getFuelAmount()`: Returns the plane's current fuel.
        - `getId()`: Returns the plane's ID.
        - `getQueueTime()`: Returns the time spent in the queue.
        - `decrementFuel()`: Reduces the fuel by 1 unit.
        - `incrementQueueTime()`: Increases the queue time by 1 unit.

2. **Airport Class**
    - **Attributes**:
        - `departing`: Queue of planes waiting to depart.
        - `departed`: Queue of planes that have successfully departed.
        - `notEnoughFuel`: Queue of planes with insufficient fuel.
        - `fuelNeededForFlight`: Constant fuel threshold required for a plane to depart.
        - `simulationTime`: Total time for the simulation.
    - **Methods**:
        - `startNewPlane(int id)`: Adds a new plane to the departing queue.
        - `isRunwayEmpty()`: Checks if the runway is empty.
        - `removePlaneFromRunway()`: Clears the current plane from the runway.
        - `decrementFuelOfAllPlanes()`: Decreases fuel for all planes in the queue.
        - `processDepartingQueue()`: Manages planes in the queue, moving them to the runway or insufficient fuel queue.
        - `processDepartingPlane()`: Updates the status of the plane on the runway.
        - `processRunway()`: Runs the main process, including fuel decrement, queue processing, and plane departure.
        - `printSimulationInfo()`: Outputs overall simulation results.
        - `printDepartedQueue()`: Displays planes that have departed.
        - `printNotEnoughFuelQueue()`: Displays planes with insufficient fuel.

## How to Use

1. **Compile and Run**:
   - Compile: `javac Airport.java`
   - Run: `java Airport`

2. **Simulation Parameters**:
   - `fuelNeededForFlight` is set to 100 units, representing the fuel required for a successful takeoff.
   - `simulationTime` is set to 50, representing the total time the simulation will run.

## Example Output

The program outputs information about the planes, including:
- Total planes in the simulation.
- Number of planes that departed.
- Planes that didn’t have enough fuel.
- Status of the departing queue.

```plaintext
Simulation time: 50
Total Planes: X
Planes that departed: Y
Planes that don't have enough fuel: Z
Planes still on the runway: W

Planes departed queue:
[ID, Fuel]-> ...

Planes not enough fuel queue:
[ID, Fuel]-> ...
