# El Templo - Atrapa Diamantes

## Project Title and Brief Description

**El Templo - Atrapa Diamantes** is a Virtual Reality game developed in 【entity-Unity¦canonical_name=Unity】 6.3 LTS for Meta Quest 3.

The player appears inside a temple / mine environment with dark walls, torches and floating crystals. The goal is simple: catch **4 diamond crystals in 40 seconds**.

The game starts in a main menu with the title **EL TEMPLO** and two buttons: **INICIAR** and **CRÉDITOS**. When the player presses INICIAR, the HUD appears showing the remaining time and the crystal counter (0/4, 1/4, 2/4, 3/4, 4/4). Every time the player grabs a crystal, a coin sound plays, the crystal disappears and the counter increases. If the player catches all 4 crystals before time ends, the **GANASTE / You Win** screen appears. If not, the **FIN / Game Over** screen appears. The player can restart with the REINICIAR button.

This project was developed as the final project for the course **Realidad Virtual - Code 213043**, in the program **Ingeniería de Multimedia**, at **Universidad Nacional Abierta y a Distancia - UNAD**, Colombia.

**Student:** Stiven Sanchez

## Technologies Used

- **【entity-Unity 6¦canonical_name=Unity】.3 LTS** - Main game engine
- **XR Interaction Toolkit** - VR interactions, ray interactor, grab interactable
- **OpenXR** - Open standard for VR runtime
- **Meta Quest SDK** - Deployment and testing on Meta Quest 3
- **C#** - Game logic (GameManager.cs, ROTADOR_CRISTAL.cs)
- **Visual Studio** - C# code editor
- **Android SDK, JDK, NDK** - Android build tools
- **Baked Lightmaps** - Lighting optimization for stable framerate
- **OBS Studio** - Screen recording for evidence video

## Project Structure

- `Assets/Scenes/DemoScene_BACKUP_FASE3.unity` - Main scene
- `Assets/Scripts/GameManager.cs` - Main game logic: timer, counter, menu, Game Over / You Win
- `Assets/Scripts/ROTADOR_CRISTAL.cs` - Crystal floating and rotation
- `Assets/Audio/coin.wav` - Sound when a crystal is collected
- `Assets/Prefabs/ROTADOR_CRISTAL` - Crystal prefabs (4 in total)

## How to Build and Install the APK

### Build Settings in 【entity-Unity¦canonical_name=Unity】

1. Open the project in **【entity-Unity 6¦canonical_name=Unity】.3 LTS**.
2. Open the scene `DemoScene_BACKUP_FASE3`.
3. Go to **File > Build Profiles > Android**.
4. Verify in **Player Settings**:
      - **Company Name:** UNAD / Stiven Sanchez
      - **Product Name:** El Templo
      - **Package Name:** `com.unad.sanchez.eltemplo`
      - **Version:** 1.1
      - **Minimum API Level:** Android 10.0 (API Level 29)
      - **Target API Level:** 34
      - **Scripting Backend:** IL2CPP
      - **Target Architecture:** ARM64
      - **Texture Compression:** ASTC
      - **Graphics APIs:** OpenGLES3 only (remove Vulkan)

5. Click **Build** and save the file as `ElTemplo_v3.apk`.

### Install on Meta Quest

1. Uninstall any previous version (v1, v2) from the Quest to avoid conflicts.
2. Connect the Quest to PC via USB or use SideQuest / ADB:
