ABB Robot Arm Program for Shaft and Washer Placement

Overview:
This program is designed for an ABB robot arm to manage the placement of shafts and washers into designated positions, perform measurements, and sort them into different magazine paths based on the results. The robot follows a specific sequence of movements and conditions to handle the components efficiently.

Structure:
The program is divided into several main procedures and supporting targets:
1. Main Procedure (`main`): Initiates the start path.
2. Start Path (`Start_PAth`): Handles the main sequence of picking and placing the shafts and washers.
3. Done Path (`DonePath`): Handles the placement of shafts and washers into the "Done" magazine.
4. Redo Path (`RedoPath`): Handles the placement of shafts and washers into the "Redo" magazine.
5. Waste Path (`WastePath`): Handles the placement of shafts and washers into the "Waste" magazine.
Procedures:
1. `main`
- Initiates the `Start_PAth` procedure.
2. `Start_PAth`
- Loops through 6 shafts/washers.
- Moves to specific targets based on the loop counter.
- Waits for gripper to close before proceeding.
- Moves the shaft/washer to the measurement station.
- Waits for measurement result and proceeds to the appropriate path (`DonePath`, `RedoPath`, `WastePath`).
3. `DonePath`
- Moves the component to the press station and then to the "Done" magazine.
- Updates the position in the "Done" magazine based on the `Done_counter`.
4. `RedoPath`
- Moves the component to the "Redo" magazine.
- Updates the position in the "Redo" magazine based on the `Redo_counter`.
5. `WastePath`
- Moves the component to the "Waste" station.
Constants and Variables

Constants
- `robtarget` constants define the specific positions and orientations for robot movements.
- Targets are categorized for different paths (e.g., `Start_PAth`, `DonePath`, `RedoPath`, `WastePath`).

Variables
- `shaft`: Distance between the middle of shafts (50mm).
- `washer`: Distance between the middle of washers (85mm).
- `Done_distance`: Distance between places in magazines (80mm).
- `counter`: General counter for loops.
- `Done_counter`: Counter for place in the "Done" magazine.
- `Redo_counter`: Counter for place in the "Redo" magazine.

Key Movements and Conditions
- `MoveJ`: Joint move to a target position.
- `MoveL`: Linear move to a target position.
- `WaitUntil`: Waits for a condition to be met.
- `WaitTime`: Waits for a specified time period.

Usage

1. Initialization: Load the program into the ABB robot controller.
2. Execution: Run the `main` procedure.
3. Monitoring: Ensure the robot follows the correct paths and handles components based on the measurement results.
4. Adjustment: Modify constants and targets as necessary for different components or magazine configurations.

This program ensures precise and efficient handling of shafts and washers, sorting them into the appropriate magazines based on measurement results, and maintaining an organized workflow for the robot operations.
![image](https://github.com/user-attachments/assets/a2c81579-f132-4fb4-9b9f-860cd62a79d6)
![image](https://github.com/user-attachments/assets/0a955622-7805-409a-adff-c987134eab1c)
![image](https://github.com/user-attachments/assets/40038c21-5094-4b9f-93e4-306e9f30ecb9)


