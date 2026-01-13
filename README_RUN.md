# Flappy Bird Unity 2D Setup Guide

This guide will help you set up and run the Flappy Bird clone in Unity.

## Prerequisites
- Unity Hub and Unity Editor (Recommended: 2021.3 LTS or newer)
- A basic understanding of the Unity Editor

## 1. Project Setup
1. Open **Unity Hub**.
2. Click **New project**.
3. Select **2D** template.
4. Name your project (e.g., `FlappyBird`) and click **Create project**.

## 2. Importing Scripts
The scripts for the game are located in the `Assets/Scripts` folder. 
1. Copy the `Assets` folder from this repository into your Unity project directory.
2. Unity will automatically compile the scripts.

## 3. Scene Setup

### Game Scene
1. Create a new scene and name it `Game`.
2. **Bird (Player):**
   - Create a 2D Sprite for the Bird.
   - Add a `Rigidbody2D` component (set `Gravity Scale` to 1.5).
   - Add a `CircleCollider2D` or `BoxCollider2D`.
   - Attach the `Bird.cs` script.
   - Set the `Tag` to `Player`.
3. **Pipes (Prefab):**
   - Create a parent empty GameObject for the Pipes.
   - Add two pipe sprites (top and bottom) with `BoxCollider2D`.
   - Add an empty GameObject in the middle with a `BoxCollider2D` (set to `Is Trigger`) and attach the `ScoreTrigger.cs` script.
   - Attach the `Pipe.cs` script to the parent GameObject.
   - Drag this GameObject into the `Assets/Prefabs` folder to create a prefab, then delete it from the scene.
4. **Pipe Spawner:**
   - Create an empty GameObject named `PipeSpawner`.
   - Attach the `PipeSpawner.cs` script.
   - Assign the Pipe prefab to the `Pipe Prefab` field.
5. **Game Manager:**
   - Create an empty GameObject named `GameManager`.
   - Attach the `GameManager.cs` script.
   - Create a UI Canvas with a Text element for the score and a "Game Over" panel with a Restart button.
   - Assign the UI elements to the fields in the `GameManager` script.

### Main Menu Scene
1. Create a new scene and name it `Menu`.
2. Create a UI Canvas with "Play" and "Quit" buttons.
3. Attach the `MainMenu.cs` script to an empty GameObject.
4. Link the button `OnClick()` events to the `PlayGame()` and `QuitGame()` methods.

## 4. Build Settings
1. Go to **File > Build Settings**.
2. Add both scenes (`Menu` and `Game`) to the **Scenes In Build** list.
3. Ensure `Menu` is at index 0 and `Game` is at index 1.

## 5. Running the Game
1. Open the `Menu` scene.
2. Press the **Play** button in the Unity Editor.
3. Use the **Left Mouse Click** or **Spacebar** to make the bird flap.

## Assets
Make sure to add your own art assets (sprites, backgrounds, sounds) in the `Assets/Sprites` and `Assets/Audio` folders and assign them to the corresponding GameObjects.
