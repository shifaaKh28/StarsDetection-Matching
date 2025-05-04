# 🌟 Star Matching

This project implements multiple methods for matching stars across astronomical images — both synthetic (from Stellarium) and real photographs (e.g., iPhone). It is based on affine transformations, RANSAC, and visual alignment methods.

## 🔭 Project Goals

- Automatically detect stars in night-sky images.
- Find matches between stars in different images, even under rotation or distortion.
- Evaluate matching performance with a metric.
- Visualize the matched stars with connecting lines.


## ⚙️ Features

- **Star Detection**  
  Uses OpenCV’s `HoughCircles` to detect stars and extract:  
  `(x, y, radius, brightness)`

- **Affine-Based Matching**  
  Picks 3 points from each image, computes an affine transformation, and checks how many stars match after the mapping.

- **RANSAC Line Filtering**  
  Robust line detection to filter aligned stars before attempting affine match.

- **Matching Metric**  
  Reports a **Matching Ratio**:  
  `(# of valid matched stars) / (min(#stars_img1, #stars_img2))`

- **Visualization**  
  Displays both images side by side with lines connecting matching stars.

---

## 📸 Example Workflow

### 🔍 Step 1: Star Detection  
Detecting stars using `cv2.HoughCircles`:

![image_alt](https://github.com/shifaaKh28/Bereshit_101/blob/main/6eSSp9awZ4jPd4K3MG6CrU.jpg)

---

### 🧾 Step 2: Saved Coordinates  
Textual output of detected star coordinates:

![image_alt](https://github.com/shifaaKh28/Bereshit_101/blob/main/6eSSp9awZ4jPd4K3MG6CrU.jpg)

---

### 🔗 Step 3: Star Matching  
Using affine transform + RANSAC to match stars between images:

![image_alt](https://github.com/shifaaKh28/Bereshit_101/blob/main/6eSSp9awZ4jPd4K3MG6CrU.jpg)

---

## 📄 Included Algorithm Explanation

The file `Star_Matching.pdf` describes an advanced algorithm for matching based on **relative distances between triplets of stars** (alternative to affine transform + RANSAC).  
This method can be implemented later as an enhancement.

Inside the notebook, you can:
- Load any two images (JPG, PNG, HEIC)
- Detect stars
- Match stars across images
- View matching results and accuracy

