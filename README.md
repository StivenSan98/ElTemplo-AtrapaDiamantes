# El Templo - Atrapa Diamantes

## Project Title and Brief Description

**El Templo - Atrapa Diamantes** is a Virtual Reality game developed in 【entity-Unity¦canonical_name=Unity】 6.3 LTS for Meta Quest 3.

The player appears inside a temple / mine environment with dark walls, torches and floating crystals. The goal is simple: catch **4 diamond crystals in 40 seconds**.

The game starts in a main menu with the title **EL TEMPLO** and two buttons: **INICIAR** and **CRÉDITOS**. When the player presses INICIAR, the HUD appears showing the remaining time and the crystal counter (0/4, 1/4, 2/4, 3/4, 4/4). Every time the player grabs a crystal, a coin sound plays, the crystal disappears and the counter increases. If the player catches all 4 crystals before time ends, the **GANASTE / You Win** screen appears. If not, the **FIN / Game Over** screen appears. The player can restart with the REINICIAR button.

This project was developed as the final project for the course **Realidad Virtual - Code 213043**, in the program **Ingeniería de Multimedia**, at **Universidad Nacional Abierta y a Distancia - UNAD**, Colombia.

**Student:** Stiven Sanchez

## Technologies Used

- **Unity 6.3 LTS** - Main game engine
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

### Build Settings in Unity

1. Open the project in **Unity 6.3 LTS**.
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
Put on the headset, open the app **El Templo** from the library.
4. Use the controllers to point with the ray and press **INICIAR** to start.

### Controls

- **VR:** Ray + Trigger to press buttons, Grip to grab crystals
- **PC Test (Simulator):**
    - Enter = INICIAR
    - C = CRÉDITOS
    - V / Esc = VOLVER
    - R = REINICIAR when GANASTE / FIN

## Performance

- **Target Framerate:** >= 72 fps
- **Profiler test in Unity Editor:** CPU 7.5 ms, GPU 1.7 ms - within target frame time
- **Lighting:** Baked lightmaps (6 lightmaps, 1024x1024) to reduce draw calls
- **Canvas:** World Space with Rotation Y 180 to be readable and clickable in VR

## Known Issues and Future Improvements

### Known Issues

- The walls can appear pink on some devices if Vulkan is left enabled. Solution: keep only OpenGLES3 in Graphics APIs.
- If the APK is installed over an old version without uninstalling, the old Package Name can cause conflicts. Solution: uninstall v1/v2 before installing v3.
- The project was tested mainly on Meta Quest 3. Performance on Quest 2 was not tested.

### Future Improvements

- Add more levels with different temple layouts and more crystals.
- Add a difficulty system: more time on easy, less time on hard.
- Add hand tracking support as an alternative to controllers.
- Add a leaderboard and save the best time with PlayerPrefs.
- Add more sound effects and background music with volume control in settings.
- Improve textures and models of the temple to make the environment more realistic.

## AI Tools Used (Declaration Summary)

AI tools were used as **support** during development, not as replacement for the student's work:

- Used for reviewing C# code errors, console warnings and build configuration.
- Used for organizing documentation, README structure and technical writing in English.
- Used for understanding XR Interaction Toolkit setup, World Space Canvas configuration and Profiler results.

All design decisions, programming, testing, build generation and final presentation were done by the student.

## Links

- **Source Code (.zip) / Project:** https://drive.google.com/file/d/18I8Y1aFetS0qB1et60T_5vxVjte_bSFr/view?usp=sharing
- **APK:** [Add Google Drive link here - ElTemplo_v3.apk]
- **Evidence Video:** [Add YouTube / Google Drive link here]
- **Showcase (itch.io):** [Add itch.io link here]

## License

Academic project - UNAD - Realidad Virtual - 2026
