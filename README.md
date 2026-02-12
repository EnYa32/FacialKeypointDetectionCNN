---
title: FacialKeypointDetectionCNN
emoji: 🙂
colorFrom: red
colorTo: red
sdk: streamlit
app_file: src/streamlit_app.py
pinned: false
short_description: 'Predict facial keypoints from an uploaded face image '
license: mit
---

# 🙂 Facial Keypoints Detection (CNN)

This app predicts **facial keypoints** (eyes, eyebrows, nose, mouth) from a face image.

## What this project does
- Input: face image (grayscale or RGB)
- Output: 30 values (x/y coordinates for 15 facial keypoints)
- The app overlays keypoints on a **96×96** image and shows the coordinates in a table.

## Files in this repo
- `app.py` → Streamlit app
- `final_keypoints_cnn.keras` → trained Keras model
- `target_cols.json` → output column names (order of the 30 targets)
- `preprocess_config.json` → preprocessing settings (image size, normalization)

## How to run locally
```bash
pip install -r requirements.txt
streamlit run app.py
Preprocessing (same as training)
Convert to grayscale

Resize to 96×96

Normalize pixels: x / 255.0

Model predicts normalized coordinates

Convert back to pixel space: y = y * 48 + 48

Clip to valid range: [0, 96]