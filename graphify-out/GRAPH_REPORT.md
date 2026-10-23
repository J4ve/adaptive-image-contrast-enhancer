# Graph Report - adaptive-image-contrast-enhancer  (2026-10-23)

## Corpus Check
- Large corpus: 500 files · ~680,437 words. Semantic extraction will be expensive (many Claude tokens). Consider running on a subfolder.

## Summary
- 36 nodes · 49 edges · 6 communities (4 shown, 2 thin omitted)
- Extraction: 92% EXTRACTED · 8% INFERRED · 0% AMBIGUOUS · INFERRED: 4 edges (avg confidence: 0.9)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- FP_Bacsain_BSCS2A.pdf - Adaptive Contrast
- Adaptive Contrast Enhancement via
- Global Contrast Factor alpha
- Bilateral Filtering (edge-preserving noise
- adaptive_contrast_enhancement()
- main() [GUI cell]

## God Nodes (most connected - your core abstractions)
1. `FP_Bacsain_BSCS2A.pdf - Adaptive Contrast Enhancement of Grayscale Images (paper)` - 10 edges
2. `Adaptive Contrast Enhancement via Local Statistics` - 7 edges
3. `Bilateral Filtering (edge-preserving noise reduction)` - 7 edges
4. `adaptive_contrast_enhancement()` - 6 edges
5. `process_image() [batch cell]` - 6 edges
6. `Global Contrast Factor alpha` - 5 edges
7. `15x15 Local Statistics Window` - 4 edges
8. `PSNR (Peak Signal-to-Noise Ratio)` - 4 edges
9. `SSIM (Structural Similarity Index Measure)` - 4 edges
10. `Batch Implementation Variant (whole-dataset PSNR/SSIM)` - 4 edges

## Surprising Connections (you probably didn't know these)
- `adaptive_contrast_enhancement()` --references--> `Global Contrast Factor alpha`  [INFERRED]
  FP_Bacsain_BSCS2A.ipynb.md → FP_Bacsain_BSCS2A.pdf
- `FP_Bacsain_BSCS2A.ipynb (adaptive contrast enhancement notebook)` --references--> `FP_Bacsain_BSCS2A.pdf - Adaptive Contrast Enhancement of Grayscale Images (paper)`  [EXTRACTED]
  FP_Bacsain_BSCS2A.ipynb.md → FP_Bacsain_BSCS2A.pdf
- `adaptive_contrast_enhancement()` --implements--> `Adaptive Contrast Enhancement via Local Statistics`  [EXTRACTED]
  FP_Bacsain_BSCS2A.ipynb.md → FP_Bacsain_BSCS2A.pdf
- `process_image() [GUI cell]` --implements--> `Bilateral Filtering (edge-preserving noise reduction)`  [EXTRACTED]
  FP_Bacsain_BSCS2A.ipynb.md → FP_Bacsain_BSCS2A.pdf
- `adaptive_contrast_enhancement()` --references--> `15x15 Local Statistics Window`  [EXTRACTED]
  FP_Bacsain_BSCS2A.ipynb.md → FP_Bacsain_BSCS2A.pdf

## Import Cycles
- None detected.

## Hyperedges (group relationships)
- **Enhance -> bilateral filter -> PSNR/SSIM evaluation pipeline** — adaptive_image_contrast_enhancer_fp_bacsain_bscs2a_ipynb_local_stats, adaptive_image_contrast_enhancer_fp_bacsain_bscs2a_ipynb_adaptive_contrast_enhancement, adaptive_image_contrast_enhancer_fp_bacsain_bscs2a_ipynb_process_image, adaptive_image_contrast_enhancer_fp_bacsain_bscs2a_bilateral_filtering, adaptive_image_contrast_enhancer_fp_bacsain_bscs2a_psnr, adaptive_image_contrast_enhancer_fp_bacsain_bscs2a_ssim [EXTRACTED 1.00]

## Communities (6 total, 2 thin omitted)

### Community 0 - "FP_Bacsain_BSCS2A.pdf - Adaptive Contrast"
Cohesion: 0.22
Nodes (9): FP_Bacsain_BSCS2A.pdf - Adaptive Contrast Enhancement of Grayscale Images (paper), Camarines Sur Polytechnic Colleges - College of Computer Studies, CSAC 225 - Digital Image Processing (course), Huang et al. (2019) Hybrid Image Enhancement with Progressive Laplacian Enhancing Unit, FP_Bacsain_BSCS2A.ipynb (adaptive contrast enhancement notebook), Jave Atanacio Bacsain (author), Lee et al. (2023) Deep Learning Image Enhancement in OCT, Ramiz & Quazi (2017) Hybrid Technique for Image Enhancement (+1 more)

### Community 1 - "Adaptive Contrast Enhancement via"
Cohesion: 0.25
Nodes (8): Adaptive Contrast Enhancement via Local Statistics, Adaptive Histogram Equalization (AHE), Global Histogram Equalization (GHE), Kountchev et al. (2022) Local Contrast Enhancement of Endoscopic Images, Kuran & Kuran (2021) Parameter Selection for CLAHE via Cuckoo Search, 15x15 Local Statistics Window, Pizer et al. (1987) Adaptive Histogram Equalization and Its Variations, Song, Li & Cao (2016) Improved Local Adaptive Enhancement Based on Lee Algorithm

### Community 2 - "Global Contrast Factor alpha"
Cohesion: 0.32
Nodes (8): Global Contrast Factor alpha, Batch Implementation Variant (whole-dataset PSNR/SSIM), BSD100 Dataset (image_SRF_2 subset), Gonzalez & Woods (2018) Digital Image Processing, main() [batch cell], PSNR (Peak Signal-to-Noise Ratio), SSIM (Structural Similarity Index Measure), Wang et al. (2004) Image Quality Assessment: From Error Visibility to Structural Similarity

### Community 3 - "Bilateral Filtering (edge-preserving noise"
Cohesion: 0.50
Nodes (5): Bilateral Filtering (edge-preserving noise reduction), process_image() [batch cell], Kumari, Chaurasia & Kumar (2016) A Survey on Noise Reduction in Images, OpenCV Docs: Smoothing Images (bilateralFilter defaults), Tomasi & Manduchi (1998) Bilateral Filtering for Gray and Color Images

## Knowledge Gaps
- **15 isolated node(s):** `Pizer et al. (1987) Adaptive Histogram Equalization and Its Variations`, `Song, Li & Cao (2016) Improved Local Adaptive Enhancement Based on Lee Algorithm`, `Kumari, Chaurasia & Kumar (2016) A Survey on Noise Reduction in Images`, `Wang et al. (2004) Image Quality Assessment: From Error Visibility to Structural Similarity`, `Tomasi & Manduchi (1998) Bilateral Filtering for Gray and Color Images` (+10 more)
  These have ≤1 connection - possible missing edges or undocumented components. (Counts symbols only; 17 node(s) total have ≤1 connection when file, concept and rationale nodes are included.)
- **2 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Adaptive Contrast Enhancement via Local Statistics` connect `Adaptive Contrast Enhancement via` to `FP_Bacsain_BSCS2A.pdf - Adaptive Contrast`, `Global Contrast Factor alpha`, `Bilateral Filtering (edge-preserving noise`, `adaptive_contrast_enhancement()`?**
  _High betweenness centrality (0.500) - this node is a cross-community bridge._
- **Why does `FP_Bacsain_BSCS2A.pdf - Adaptive Contrast Enhancement of Grayscale Images (paper)` connect `FP_Bacsain_BSCS2A.pdf - Adaptive Contrast` to `Adaptive Contrast Enhancement via`, `Global Contrast Factor alpha`?**
  _High betweenness centrality (0.435) - this node is a cross-community bridge._
- **Why does `Bilateral Filtering (edge-preserving noise reduction)` connect `Bilateral Filtering (edge-preserving noise` to `Adaptive Contrast Enhancement via`, `adaptive_contrast_enhancement()`, `main() [GUI cell]`?**
  _High betweenness centrality (0.220) - this node is a cross-community bridge._
- **What connects `Pizer et al. (1987) Adaptive Histogram Equalization and Its Variations`, `Song, Li & Cao (2016) Improved Local Adaptive Enhancement Based on Lee Algorithm`, `Kumari, Chaurasia & Kumar (2016) A Survey on Noise Reduction in Images` to the rest of the system?**
  _15 weakly-connected nodes found - possible documentation gaps or missing edges._