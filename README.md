
Upload Image ] 
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
