# Unity Grid-Based Movement with Pathfinding

This project implements a 10x10 grid in Unity with player and enemy units. The player can move to any selected tile while avoiding obstacles, and the enemy moves towards the player using a grid-based pathfinding algorithm. The project also includes animations for the player unit.

## Features

- **Grid Generation**: Generates a 10x10 grid of tiles.
- **Obstacle Placement**: Allows toggling obstacles on the grid using a custom editor tool.
- **Pathfinding**: Implements a grid-based pathfinding algorithm to navigate the grid.
- **Player Movement**: The player can move to any selected tile on the grid, avoiding obstacles.
- **Enemy AI**: The enemy unit moves towards the player and stops adjacent to the player.
- **Animations**: Includes idle and walking animations for the player unit.

## Setup

1. **Clone the repository**:
    ```sh
    git clone https://github.com/your-username/unity-grid-based-movement.git
    ```
2. **Open the project in Unity**:
    - Ensure you have Unity installed.
    - Open the project in the Unity Editor.

3. **Setup Animations**:
    - Create idle and walking animations for the player and save them in the `Animations` folder.
    - Create an Animator Controller named `PlayerAnimatorController` and set up animation states and transitions.

4. **Assign Animator Controller**:
    - Select the player unit in the scene.
    - In the Animator component, assign the `PlayerAnimatorController` to the Controller field.

## Usage

### Grid and Obstacles

- **Grid Generation**:
    - Attach the `GridManager` script to an empty GameObject named `GridManager`.
    - Assign the cube prefab to the `cubePrefab` field in the `GridManager` script.

- **Obstacle Placement**:
    - Create a ScriptableObject for obstacles: `Create -> ScriptableObjects -> ObstacleData`.
    - Open the Grid Editor: `Window -> Grid Editor`.
    - Assign the `ObstacleData` ScriptableObject to the Grid Editor window and toggle obstacles on the grid.

- **Obstacle Manager**:
    - Attach the `ObstacleManager` script to an empty GameObject named `ObstacleManager`.
    - Assign the `ObstacleData` ScriptableObject and the red sphere prefab to the `obstacleData` and `obstaclePrefab` fields respectively.

### Player and Enemy Movement

- **Player Movement**:
    - Attach the `PlayerController` script to the player unit.
    - Assign the necessary animations and the `PlayerAnimatorController`.

- **Enemy AI**:
    - Attach the `EnemyAI` script to the enemy unit.
    - Assign the `Pathfinding` script, `ObstacleData` ScriptableObject, and `PlayerController` script to the appropriate fields in the `EnemyAI` script.

- **Mouse Input**:
    - Attach the `MouseRaycaster` script to the Main Camera.
    - Assign the `PlayerController`, `EnemyAI`, `Pathfinding`, and `ObstacleData` fields in the `MouseRaycaster` script.

### Playing the Game

- **Start the Game**:
    - Press Play in the Unity Editor.
    - Click on tiles to move the player unit. The player should avoid obstacles and move to the selected tile.
    - The enemy unit will move towards the player, stopping adjacent to the player.

## Scripts Overview

- **GridManager.cs**: Generates the 10x10 grid.
- **TileInfo.cs**: Stores information about each tile.
- **MouseRaycaster.cs**: Handles mouse input and raycasting.
- **Pathfinding.cs**: Implements grid-based pathfinding.
- **PlayerController.cs**: Controls the player movement and animations.
- **EnemyAI.cs**: Controls the enemy movement towards the player.
- **ObstacleManager.cs**: Generates obstacles on the grid based on the ScriptableObject.
- **IAI.cs**: Interface for AI movement.

## Contributing

1. Fork the repository.
2. Create a new branch: `git checkout -b my-feature-branch`.
3. Make your changes and commit them: `git commit -m 'Add some feature'`.
4. Push to the branch: `git push origin my-feature-branch`.
5. Submit a pull request.

## License

This project is licensed under the MIT License.

---

Feel free to modify and extend this project. Contributions are welcome!

