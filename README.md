# Adaptive Contrast Enhancement of Grayscale Images

Enhances local contrast in grayscale images using local statistics and bilateral filtering, then scores each result with PSNR and SSIM. Final project for CSAC 225 Digital Image Processing (BSCS-2A), Camarines Sur Polytechnic Colleges, by Jave Atanacio Bacsain. The full paper is [`FP_Bacsain_BSCS2A.pdf`](FP_Bacsain_BSCS2A.pdf).

## Project Description

Global methods like histogram equalization apply the same change to the whole image, which can over-enhance some areas and lose detail in others. This project adjusts each pixel based on its neighborhood instead. The notebook `FP_Bacsain_BSCS2A.ipynb` has two versions:

- **Batch:** processes every image in `BSD100/image_SRF_2` at one alpha value, saves the results to `outputs/alpha<value>/`, and prints PSNR and SSIM per image plus the averages.
- **Single image GUI:** pick one image and adjust alpha and the bilateral filter with sliders. The original and processed images are shown side by side with live PSNR and SSIM.

## Methodology

1. Load each image with scikit-image and convert color images to 8-bit grayscale.
2. Compute the local mean and standard deviation over a 15x15 window with `cv2.blur`.
3. Enhance each pixel (values scaled to 0-1, result clipped to 0-1):
   `enhanced = local_mean + alpha * (pixel - local_mean) * (1 - local_std / max_local_std)`.
   Low variation areas get close to the full `alpha` boost. High variation areas get less.
4. Apply `cv2.bilateralFilter` (`d = 9`, `sigmaColor = 75`, `sigmaSpace = 75`) to smooth amplified noise while keeping edges.
5. Compute PSNR and SSIM (scikit-image, `data_range = 255`) between the original grayscale image and the final output.
6. Repeat the batch run at several alpha values and compare the averages.

Dataset: the `image_SRF_2` folder of [BSD100](https://figshare.com/articles/dataset/BSD100_Set5_Set14_Urban100/21586188), 100 images with an `_HR` and an `_LR` version each (200 files). The notebook processes the images as they are. It does not lower their contrast first.

## Results

The best average PSNR is 26.60 dB at alpha 3.1 and the best average SSIM is 0.8539 at alpha 3.7. Batch averages from Table 2 (page 7) of the paper:

| Alpha | Avg. PSNR (dB) | Avg. SSIM |
|---|---|---|
| 1.0 | 22.63 | 0.5730 |
| 3.1 | 26.60 | 0.8389 |
| 3.2 | 26.59 | 0.8436 |
| 3.7 | 26.02 | 0.8539 |
| 5.0 | 22.75 | 0.8133 |

The saved output of the batch cell in the notebook matches the alpha 3.2 row. It lists all 200 files and ends with `Average PSNR: 26.59 dB` and `Average SSIM: 0.8436`. The paper concludes that alpha between about 3.1 and 3.4 gives the best balance between noise suppression, edge preservation and structural fidelity. Lower alpha smooths too much and higher alpha adds visible artifacts.

Sample output at alpha 3.2 (`img_006_SRF_2_HR.png`, PSNR 29.44 dB, SSIM 0.9113):

![img_006 at alpha 3.2](outputs/alpha3.2/img_006_SRF_2_HR.png)

## How to Run

The notebook was run on Python 3.12.0. There is no `requirements.txt`. The code imports OpenCV (`cv2`), NumPy, scikit-image and tkinter (GUI only).

1. Clone the repo and open `FP_Bacsain_BSCS2A.ipynb` from the repo folder. The BSD100 images are included.
2. **Batch:** run the first code cell and enter an alpha value (for example `3.2`).
3. **GUI:** run the second code cell, choose an image, and move the sliders. Press Esc to close.

The notebook uses Windows paths (`BSD100\image_SRF_2`). On macOS or Linux, change them to forward slashes.

## License

MIT. See [`LICENSE`](LICENSE).
