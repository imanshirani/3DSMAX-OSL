# OSL-SDF for 3ds Max

A powerful collection of **OSL (Open Shading Language)** nodes for creating complex **2D/3D shapes, patterns, and textures** directly within the 3ds Max Slate Material Editor.  

This toolkit brings the power of **Signed Distance Fields (SDFs)** and procedural modeling into a user-friendly, node-based workflow for artists and designers.

---

## 📖 About The Project

This project was born from the desire to have a flexible, renderer-agnostic procedural modeling and texturing system inside 3ds Max.  

Instead of relying on specific renderer features or complex plugins, this toolkit uses the power of **OSL** to generate and manipulate shapes mathematically.

✨ The workflow is entirely **non-destructive** and allows for:
- Infinite resolution
- Endless creative possibilities
- From intricate hard-surface details to organic patterns

---

## 🚀 Key Features

- **Modular Node-Based Workflow**: Every function is a separate, easy-to-understand node. Combine them to create limitless complexity.  
- **Rich Library of Primitives**: Spheres, boxes, sharp stars, polygons, and more.  
- **Powerful Transformers**: Position, rotate, and scale shapes in 2D space with intuitive controls.  
- **Advanced Combiners**: Add, subtract, or smoothly blend shapes together.  
- **Procedural Tiling & Repetition**: Build infinite patterns with arrays and radial repeaters.  
- **Surface Detailing**: Procedural noise, displacement, and outlines.  
 

---

## 📦 Getting Started

### ✅ Prerequisites
- Autodesk **3ds Max 2019+** (best OSL support)
- Modern render engine that supports **OSL** & **displacement** (Octane, Arnold, V-Ray, Corona)

### 🔧 Installation
1. **Download the OSL Files**  
   - Save all `.osl` files from this repository.  
2. **Set Up OSL Path**  
   - Copy all files to the Autodesk 3ds Max path at:  
     `C:\Program Files\Autodesk\3ds Max 20XX\OSL\SDF`   
3. **Load the Material Library**  
   -  
   - In **Slate Material Editor**:  
     - Open the Material/Map Browser  
     1 - Right-Click `Maps>OSL>SDF` and `Maps>OSL>SDF Primitives`
     - All nodes are now ready to use!  

---

## 🧩 Basic Workflow Example: *Creating a Drilled Sphere*

This example shows how to subtract a cylinder from a sphere.

### 1. Drag Nodes from the Library
- **SDF Sphere**  
- **SDF Cylinder**  
- **SDF Boolean**  
- **SDF to Mask**

### 2. Set Parameters
- `SDF Sphere`: Radius = `1.0`  
- `SDF Cylinder`: Radius = `0.3`, Height = `3.0`

### 3. Connect the Nodes
```text
Sphere (SDF_Out)  --->  Boolean (SDF_A)
Cylinder (SDF_Out) --->  Boolean (SDF_B)
Boolean (SDF_Out) --->  SDF to Mask (SDF_In)
```
### 3. 4. Finalize the Material

In SDF Boolean, set operation = Subtract

Connect Mask_Out → Base Color + Displacement inputs of your main material

✅ You now have a procedurally created sphere with a hole through it!

📚 Node Library Overview

🔷 Primitives

SDF Sphere

SDF Box

SDF Cylinder

SDF Torus

SDF Sharp Star

SDF NGon

SDF Rectangle

SDF Ellipse

SDF Egg

🔧 Transformers (2D)
SDF Translate 2D

SDF Rotate 2D

SDF Scale 2D

🔀 Combiners

SDF Boolean (Union / Subtract / Intersect)

SDF Smooth Union

♻️ Repeaters

SDF Array 2D

SDF Repeat Radial Advanced

🎨 Detailers

SDF Noise Advanced

SDF Displace

SDF Shell

🛠 Utilities

SDF to Mask

Util Color by Value

📜 License

This project is licensed under the MIT License.
