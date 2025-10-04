## Dream 2050 – Team Titan

*"Dream has no fear. Space is not out of reach."*

Dream 2050 is an ambitious **Virtual Reality (VR) simulation** created to celebrate the **25th Anniversary of the International Space Station (ISS)**.
Our vision extends to **2050**, promoting global participation in space exploration by bringing the authentic astronaut experience directly to everyone.

The project bridges the gap between **limited ISS access** and **seamless global access**, powered by:

* **Blender** (3D modeling)
* **Unity** (game engine, C# scripting)
* **NASA Open Data**
* **Gemini AI API** (intelligent assistance and contextual guidance)

---

## Project Demonstration
Our VR simulation offers an authentic astronaut experience through the Cupola Photography Mode (linked to real NASA climate data) and a Weightless Mission Mode that replicates NBL training.
The Gemini AI Astro Bot Assistant provides real-time, data-backed guidance, transforming passive viewing into an active journey of skill development and planetary awareness.

[Watch on YouTube](https://youtu.be/jWjH_fgH-UA?si=-G1NtQi7OCT6Zw5t)


---

## UnityAndGeminiV3.cs - AI Astrobot Integration

This script integrates Google's **Gemini AI** with Unity for:

- Conversational AI  
- Image generation  
- Multimedia analysis capabilities  

### How to Run Locally

1. **Get a Gemini API key**, then create a `gemini_api.json` file in your Unity project's `Assets/Resources` folder with the format:  
   ```json
   { "key": "YOUR_API_KEY" }
2. Add the `UnityAndGeminiV3.cs` script to an empty GameObject in your scene.
3. Assign the JSON file to the script's JSON API field in the Inspector.
4. For chat functionality:
* Create TextMeshPro Input Field and Text components.
* Assign them to the script's Input Field and UI Text fields in the Inspector.
5. (Optional configurations):
* Bot Instructions → Customize AI behavior.
* Image Prompt → Generate skyboxes.
* Media File Path & Media Prompt → Analyze videos, audio, PDFs, or images (max 20MB).
6. Press Play ▶ to start interacting with the AI.


<p align="center"> <img src="./astrobot.png" alt="Astrobot Screenshot" width="500"/><br/> <strong>Astrobot Conversational UI</strong> </p>

---

## ISS Unity (Project & Standalone)

This repository contains a Unity project and a Windows standalone build inside the `ISS Unity` folder. The section below explains what you'll find there and provides clear, safe steps to run or open the project in the Unity Editor.

### What you'll find

- `ISS Unity/ISS Unity/Asset Test.exe` — a Windows standalone build (executable) paired with its `*_Data` folder. This is a pre-built player you can run directly on Windows.
- `ISS Unity/ISS Unity/Asset Test_Data/Managed/` — managed assemblies from the build. If the repository also contains `Assets/` and `ProjectSettings/` under the `ISS Unity` folder, that means the full Unity project is present; otherwise the folder may only contain the built player.

### Quick start — run the built player (Windows)

1. Open the Explorer and navigate to `ISS Unity/ISS Unity/`.
2. Double-click `Asset Test.exe` to launch the standalone player. Ensure the `Asset Test_Data` folder remains next to the `.exe` file — they must be together.
3. If Windows blocks execution, right-click the `.exe`, choose "Properties" and click "Unblock" (if present), then run it. If it still won't start, see Troubleshooting below.

### PC Configuration & Quick Run (short)

Minimum recommended PC (for the built player):

- OS: Windows 10 / 11 (64-bit)
- CPU: Quad-core (or better)
- RAM: 8 GB (16 GB recommended)
- GPU: DirectX 11 compatible GPU with 2+ GB VRAM
- Disk: 1 GB free next to the `.exe` (more for assets)

Quick one-line PowerShell to unblock and run the player (run from the folder containing `Asset Test.exe`):

```powershell
# Unblock the exe (if blocked) and start it
Unblock-File -Path .\"Asset Test.exe"; Start-Process -FilePath .\"Asset Test.exe"
```

If you use VR, ensure your headset runtime (SteamVR, Oculus/Meta, etc.) is installed and running before launching the player.

### Open the project in Unity Editor (recommended for development)

1. Install Unity Hub and a recent LTS Editor. Recommended starting points: Unity 2021.3 LTS or Unity 2022.3 LTS. If you know which Unity version the project was created with, prefer that version.
2. In Unity Hub: "Add" and select the folder `ISS Unity/` or `ISS Unity/ISS Unity` (whichever contains `Assets/` and `ProjectSettings/`).
3. Open the project in the Editor. Unity may prompt to upgrade project files if you open it with a different Editor version — review the prompt and back up the project if needed.
4. To test in Editor, open the desired scene from `Assets/Scenes` (or the Scenes folder used by the project) and press the Play button.

Recommended Editor modules and packages (may be needed depending on the project configuration):

- Windows Build Support (IL2CPP or Mono, depending on project)
- XR Plugin Management / OpenXR (if the project uses VR)
- Universal Render Pipeline (URP) or Built-in Render Pipeline packages the project expects

If any package is missing, the Unity Package Manager will show errors or prompts when the project loads.

### Build from source (create a fresh player)

1. Open the project in the Editor (see "Open the project in Unity Editor").
2. File -> Build Settings: choose the target platform (Windows) and ensure required scenes are listed in the Scenes In Build section.
3. Configure Player Settings (company/product name, resolution, API compatibility level) as required.
4. Click "Build" and choose a folder. Unity will produce an `.exe` and a matching `_Data` folder.

### Integration notes (Gemini AI / API keys)

This repository also contains scripts (for example `UnityAndGeminiV3.cs`) that integrate the Gemini API. If you plan to run or develop features that use the Gemini integration inside the Unity project:

- Create a `gemini_api.json` with the format `{ "key": "YOUR_API_KEY" }` and place it in `Assets/Resources/` so the runtime can read it (see the "UnityAndGeminiV3.cs" section earlier in this README).
- Follow the script's Inspector fields: assign UI components and any reference assets required.

### Troubleshooting

- Player crashes on startup: Verify the `.exe` and `_Data` folder remain together. Install the Visual C++ Redistributable for Visual Studio 2015-2019 (x64) — many Unity players require it.
- Editor opens but scripts show errors: Open Window -> Package Manager and install/update missing packages listed as errors; ensure the Editor version is compatible with the project.
- XR / VR errors: Make sure OpenXR or the relevant XR plugin is enabled in Project Settings -> XR Plug-in Management and that required runtime (e.g., Oculus/Meta, SteamVR) is installed on your machine.
- Asset/Test scenes missing: If you only have the built player (no `Assets/` or `ProjectSettings/`), you won't be able to build from source — ask the repository owner for the full project files.

### Notes

- Running the built `Asset Test.exe` is the fastest way to preview the experience on Windows. Editing or rebuilding requires the Unity project files and a compatible Unity Editor installation.
- Always back up the project folder before opening/upgrading with a different Unity version.

---


## Project Summary

Dream 2050 goes beyond passive viewing — it is an **active astronaut journey** that:

* Simulates **Cupola Earth photography** linked to real NASA data.
* Recreates **Neutral Buoyancy Lab (NBL) training** with physics-based microgravity drift.
* Integrates the **AI Astro Bot Assistant**, which serves as a multilingual (Bangla & English) mission control guide.

Through these immersive experiences, users learn **problem-solving, teamwork, planetary care**, and the real significance of space exploration for life on Earth.

---

## Core Components

### 1. Cupola Photography Mode (Earth Observation)

* Sit inside the ISS Cupola.
* Capture images of Earth (storms, climate markers, coastlines, forests).
* Each photo dynamically links to **real NASA data**, teaching its role in disaster response, climate monitoring, and Earth studies.

### 2. Weightless Mission Mode (NBL Training)

* Physics-based **microgravity drift simulation**.
* Perform astronaut tasks: solar panel repair, plant growth experiments, and emergency response.
* Inspired by NASA’s **Neutral Buoyancy Lab training**.

### 3. AI Astro Bot Assistant

* Powered by **Gemini AI API**.
* Functions as a **personal mission control** in the user’s ear.
* Provides **data-backed guidance** and **Q&A support** on ISS, space science, and NASA initiatives.
* Supports **Bangla & English** for inclusive access.

---

## Benefits of Our Solution

* **Authentic Immersion**: Users live the astronaut life, not just watch it.
* **Skill Development**: Learn teamwork, problem-solving, patience, and planetary care.
* **Data-Driven Learning**: Links actions (like photography) to **real-world scientific impact**.
* **Accessibility & Inclusion**: Future updates will add **cross-platform support** and classroom-friendly versions.

---

## Our Goal

Our goal is to transform the **passive consumption of space content** into **active engagement**.
By combining **VR, physics simulation, and AI guidance**, Dream 2050 shows that:

* Space is **not out of reach**.
* The skills astronauts need are the same skills we need on Earth.
* Every mission connects directly to **planetary care**.

We aim to inspire **global contribution to space exploration by 2050**.

---

## Tools & Technologies

* **Unity (C#)** – game engine & scripting
* **Blender** – 3D modeling
* **NASA Open Data** – real datasets & imagery
* **Gemini AI API** – contextual guidance & intelligent assistant

---

## Use of AI

* ChatGPT
* Gemini
* Canva
* Veo3

---

## Challenges

* Realism vs. Accessibility – Making the ISS & NBL experience scientifically accurate yet lightweight and device-friendly.
* Data & Asset Integration – Curating massive NASA imagery/video into optimized, interactive formats.
* Interactivity & Engagement – Balancing astronaut training realism with fun, short missions for students.
* Multi-Mode Design – Seamlessly linking Cupola visuals with NBL weightlessness without breaking immersion.

---

## Solution

Team Titan from Bangladesh created Dream 2050: ISS VR + AI Experience, an immersive simulation that transforms astronaut experiences into an interactive learning journey.

* Cupola Mode lets users look through ISS windows, capture Earth photos, and link them to real NASA datasets on storms, forests, cities, and climate change.
* Weightless Mission Mode recreates microgravity, where users float, repair solar panels, unload cargo, grow plants, and handle emergencies as astronauts train in the NBL.
* AI Astro Bot Assistant acts as mission control—guiding users, answering questions with real NASA data, and turning the VR simulation into an educational companion.


---

## Impact

* Educational Access: Makes astronaut experiences available to students, classrooms, and the public—breaking geographic and resource barriers.
* Earth Connection: Shows how Cupola photography aids disaster response and climate research, and how NBL-style teamwork applies to hospitals, factories, and schools.
* STEM Inspiration: Sparks curiosity about science, technology, and space exploration—encouraging future scientists and innovators.
* Emotional Resonance: Builds empathy for Earth by letting people feel the silence, fragility, and awe of space.
---


## References

* [NASA Open Data Portal](https://data.nasa.gov/dataset/?q=International+Space+Station+&sort=score+desc%2C+metadata_modified+desc)
* [NASA Image and Video Library](https://images.nasa.gov/search?q=international%20space%20station&page=1&media=image&yearStart=1920&yearEnd=2025)
* [International Space Station - NASA](https://www.nasa.gov/reference/international-space-station/)
* [Growing Plants in Space - NASA](https://www.nasa.gov/exploration-research-and-technology/growing-plants-in-space/)
* [Virtual and Augmented Reality Technologies - NASA](https://www.nasa.gov/centers-and-facilities/armstrong/virtual-and-augmented-reality-techs/)
* [Unity](https://docs.unity3d.com/Packages/com.unity.ugui@2.0/manual/HOWTO-UIWorldSpace.html)

---

## Acknowledgments

Thanks to **NASA Space Apps Challenge 2025**, open-source communities, and all contributors for inspiring innovation.

---
