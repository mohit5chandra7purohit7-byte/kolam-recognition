# Kolam Recognition

## 📚 Prerequisites & Core Concepts

### 🔄 The Simplified Pipeline
Here is how our Kolam recognition system flows from start to finish:
* **Upload & Extraction:** We upload an image and extract the dot grid and strokes.
* **Conversion:** We convert those extracted dots and strokes into a mathematical graph (nodes and edges).
* **Generation:** We generate a new Kolam design based on the mathematical rules we found.
* **Display:** We display the final generated Kolam on a web interface.

### ⚙️ Important Git Files
* **`.gitignore`:** This file acts as a bouncer for our repository. It explicitly tells Git which files and folders to completely ignore (like our heavy `venv/` environment folder and large image datasets) so they don't get uploaded to GitHub.
* **`.gitkeep`:** [To be added...]

---

## 🚀 Setup Instructions

1. **Create virtual environment**
   ```cmd
   python -m venv venv
   ```
2. **Activate virtual environment**
   ```cmd
   .\venv\Scripts\activate
   ```
3. **Install strictly required libraries**
   ```cmd
   pip install -r requirements.txt
   ```

---

## 🔄 System Architecture & Pipeline

```text
       [ Upload Image ] 
              │
              ▼
1. Preprocessing (OpenCV / scikit-image / NumPy)
   ➔ Detects dot grid coordinates & isolates stroke paths
              │
              ▼
2. Graph & Symmetry Analysis (NetworkX / Shapely)
   ➔ Maps dots to nodes & strokes to edges
   ➔ Identifies mathematical rules (symmetry type, repetition)
              │
              ▼
3. Generative Engine (svgwrite / L-systems)
   ➔ Generates complete vector (SVG) patterns based on detected rules
              │
              ▼
4. User Interface (Streamlit)
   ➔ Displays detected rules & renders generated SVG output
```

---

## 👥 Team Roles & Responsibilities

| Team Pair | Pipeline Phase | Folders They Own | What They Actually Do |
|-----------|----------------|------------------|-----------------------|
| **You (Mohit P.) & Bhaskar** | Upload & Extraction | `data/` and `src/preprocessing/` | You will put raw images into `data/raw/`. Inside `src/preprocessing/`, you will write OpenCV scripts to extract the dots and strokes from those images. |
| **Avani & Priya** | Conversion (Dots to Graphs) | `src/graph_analysis/` | They will write scripts to take your extracted coordinates and use NetworkX to find the symmetry rules. |
| **Riya & Mohit J. (Lead)** | Generation & Display | `src/generation/` and `app/` | Riya writes the SVG drawing code inside `src/generation/`. Mohit J. builds the Streamlit website inside the `app/` folder to display the final result. |
