
# 🟦 OpenGL Shape Playground

### Interactive 2D Shape Generation & Management

A simple yet interactive **C++ / OpenGL 3.3** application that generates geometric shapes, places them randomly on the screen, prevents overlapping, and allows users to manage them using keyboard controls.

![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![OpenGL](https://img.shields.io/badge/OpenGL-3.3-blue?style=flat-square)
![Visual Studio](https://img.shields.io/badge/Visual%20Studio-Windows%20x64-purple?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-success?style=flat-square)

---

## 🎬 Project Demo

Watch the application in action!

<img width="540" height="558" alt="preview" src="https://github.com/user-attachments/assets/2b2411b1-c185-454d-9be8-4ada8c96ebca" />

The demonstration shows random shape generation, collision prevention, and model deletion using keyboard controls.

---

## ✨ Features

- 🎲 **Random Shape Generation** — Generates one of four predefined geometric models.
- 📍 **Random Positioning** — Places shapes at randomly selected coordinates.
- 🧩 **Collision Prevention** — Ensures shapes do not overlap.
- 🔢 **Three-Shape Limit** — Displays a maximum of three models simultaneously.
- 🗑️ **FIFO Deletion** — Deletes the oldest model first.
- ⚡ **Real-Time Rendering** — Updates the display immediately after each action.
- 🎮 **Keyboard Interaction** — Simple and intuitive controls.

---

## 🎮 Keyboard Controls

| Key | Action |
|:---:|---|
| **S** | Generate and add a random shape |
| **D** | Delete the oldest existing shape |
| **Q** | Quit the application |

> **Note:** A maximum of three shapes can be displayed at once. After deleting a shape, a new one can be added by pressing **S**.

---

## 🟨 Available Shape Models

The application supports four different models, each constructed from unit squares.

| Model | Description | Squares |
|:---:|---|:---:|
| **A** | Single square | 1 |
| **B** | Two horizontal squares | 2 |
| **C** | Three vertical squares | 3 |
| **D** | L-shaped configuration | 3 |

Each square consists of **two triangles**, rendered using OpenGL.

<img width="537" height="215" alt="image" src="https://github.com/user-attachments/assets/fc8144f9-c67e-4778-93ed-b4f7de12c616" />


---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| **C++** | Main programming language |
| **OpenGL 3.3** | 2D graphics rendering |
| **GLFW** | Window creation and keyboard input |
| **GLEW** | OpenGL extension management |
| **GLM** | Graphics mathematics |
| **GLSL** | Vertex and fragment shaders |
| **Microsoft Visual Studio** | Development environment |
| **Windows x64** | Development platform |

---

## 🚀 Getting Started

### Prerequisites

Before running the application, make sure you have:

- Microsoft Visual Studio with C++ support
- OpenGL 3.3 compatible graphics drivers
- GLFW, GLEW, and GLM libraries
- Windows with x64 project configuration

### Installation & Execution

**1. Create or open a C++ project in Visual Studio.**

**2. Configure the required libraries:**

- GLFW
- GLEW
- GLM

**3. Add the source file to your project:**

`Source-1A.cpp`

**4. Make sure the shader files are accessible from the application's working directory:**

- `ProjectVertexShader.vertexshader`
- `ProjectFragmentShader.fragmentshader`

**5. Build and run the application.**

A **900 × 900** window with a dark-blue background will appear.

Use **S**, **D**, and **Q** to interact with the program.

> This repository contains the source files and shaders. The OpenGL libraries and Visual Studio project configuration must be set up separately.

---

## 🧠 How It Works

### 1. Shape Creation

When the user presses **S**, the application:

1. Checks whether fewer than three models exist.
2. Randomly selects one of the four models.
3. Generates random coordinates.
4. Constructs the model using unit squares.
5. Checks whether the new model overlaps an existing one.
6. Repeats positioning until a valid location is found.
7. Adds the model to the scene.

### 2. Collision Detection

The `overlap()` function compares the positions of the unit squares belonging to different models.

If an overlap is detected, the application generates new coordinates before adding the model.

### 3. Shape Deletion

When **D** is pressed, the oldest model is removed using:

`models.erase(models.begin());`

This implements a **First-In, First-Out (FIFO)** deletion mechanism.

### 4. Rendering

The vertices of all active models are combined into a single vertex array.

The application then updates the OpenGL vertex buffer and renders the models using:

- `glBufferData()`
- `glVertexAttribPointer()`
- `glDrawArrays()`

---

## 📂 Project Structure

```text
OpenGL-Shape-Playground/
│
├── README.md
├── Source-1A.cpp
│
├── ProjectVertexShader.vertexshader
├── ProjectFragmentShader.fragmentshader
│
└── demo/
    ├── demo.mp4
    └── preview.gif
```

---

## 🔧 Troubleshooting

### Greek Characters in the Window Title

If Greek characters appear as question marks in the window title, check the file encoding and the Visual Studio compiler settings.

One possible solution is to enable UTF-8 compilation:

**Project → Properties → C/C++ → Command Line → Additional Options**

Add:

`/utf-8`

Then rebuild the solution.

For more information, see the [GLFW Window Title Documentation](https://www.glfw.org/docs/3.3/window_guide.html#window_title).

---

## 🎓 About the Project

This project was developed as part of a university **Computer Graphics / OpenGL programming assignment**.

The objective was to explore fundamental graphics programming concepts, including:

- Geometric modeling
- Vertex-based rendering
- Random object positioning
- Collision detection
- Keyboard event handling
- Dynamic object management

The original starter code and GLSL shader files were provided as course materials.

---

### ⭐ Built with C++ and OpenGL

*A small interactive graphics project demonstrating shape generation, collision detection, and dynamic model management.*
