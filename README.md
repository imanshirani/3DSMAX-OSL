# OSL-SDF for 3ds Max

A powerful collection of **OSL (Open Shading Language)** nodes for creating complex **2D/3D shapes, patterns, and textures** directly within the 3ds Max Slate Material Editor.  

This toolkit brings the power of **Signed Distance Fields (SDFs)** and procedural modeling into a user-friendly, node-based workflow for artists and designers.

![screenshot](SignedDistanceFields(SDFs).png)

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

> **New Update:** Complete restructuring with proper categories, new 2D primitives, domain operators, and utility nodes for 3ds Max workflow.

## 📂 Categories & Features

The library is organized into the following categories in the 3ds Max Map Browser:

### 1. Primitives (Shapes)
Basic building blocks. All 2D shapes include a `Corner Radius` parameter for rounding edges.

* **Shapes:**
* `SDF_Box` (Standard Box)
* `SDF_Sphere`
* `SDF_Torus`
* `SDF_Cylinder`
* `SDF_Capsule` (Line with radius)
* `SDF_Plane` (Infinite Plane)
* `ImageToSDF` (Generate 3D height field from images)
* `SDF_Rectangle` / `SDF_Box_4Corner` (Advanced Box with independent corners)
* `SDF_Line`
* `SDF_NGon` (Regular Polygon)
* `SDF_Ellipse` / `SDF_Egg`
* `SDF_Shape_Triangle` (Free-form)
* `SDF_Shape_Triangle_Equilateral`
* `SDF_Shape_Triangle_Isosceles`
* `SDF_Shape_Rhombus`
* `SDF_Shape_Trapezoid`
* `SDF_Shape_Parallelogram`
* `SDF_Shape_Arc`
* `SDF_Shape_Pie`
* `SDF_Shape_Vesica` (Eye/Leaf shape)
* `SDF_Star` / `SDF_Star_2` / `SDF_Star_3` / `SDF_Star_outline`
* `SDF_Shape_Heart`
* `SDF_Shape_CoolS`
* `SDF_Shape_Cross` *(New)*
* `SDF_Shape_RoundedX` *(New)*
* `SDF_Shape_Stairs` *(New)*
* `SDF_Shape_CutDisk` *(New)*
* `SDF_Shape_CircleWave` *(New)*

### 2. Domain (Space Manipulation)
Modify the space *before* creating a shape to create twists, repetitions, and deformations.

* `SDF_Transform` (Move, Rotate, Scale)
* `SDF_Repeat_Grid` (Infinite repetition in X/Y/Z with Cell ID output)
* `SDF_Repeat_Radial` (Circular repetition)
* `SDF_Mirror` (Symmetry along axis)
* `SDF_Twist` (Twist geometry along axis)
* `SDF_Elongate` (Stretch shapes without distorting corners)
* `SDF_Repeat_2D`
* `SDF_Array_2D`
* `SDF_Rotate`
* `SDF_Scale`
* `SDF_Transform`
* `SDF_Transform_2D`

### 3. Operators (Boolean Logic)
Combine multiple SDF shapes.

* `SDF_Boolean` (Union, Subtraction, Intersection)
* `SDF_Smooth_Boolean` (Blob-like organic blending)
* `SDF_Smooth_Difference` (Smooth subtraction/carving)

### 4. Modifiers (Shape Alteration)
Modify the resulting SDF field.

* `SDF_Round` (Round edges of any shape)
* `SDF_Displace` (Add noise or texture displacement)
* `SDF_Shell`
* `SDF_Noise_Advanced`

### 5. Utils (Helper Nodes)
Essential tools for the 3ds Max workflow.

* `SDF_UV_Setup` (**Crucial**: Maps UV coordinates 0-1 to SDF coordinates -1 to 1. Use this first for 2D shapes on planes).
* `SDF_to_Normal` (Converts SDF to Normal Map for lighting details).
* `SDF_Preview_3D` (Fake 3D lighting visualization on 2D planes).
* `Util_Color_by_Value`

---

📜 License

This project is licensed under the MIT License.
