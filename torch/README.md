# InverseRenderNet PyTorch

Pure PyTorch port of InverseRenderNet_v2 for single-image inverse rendering.

Predicts:
- **Albedo** (reflectance)
- **Surface Normals**
- **Shadow map**
- **SH Lighting coefficients** (9 coefficients × 3 RGB channels)

## Setup

```bash
pip install -r requirements.txt
```

## Download Weights

Download the pre-converted PyTorch weights from Google Drive:

**[weights.pth](https://drive.google.com/file/d/1_MardKJ3kZL89ycf0c4pPWWEOmoJXzOa/view?usp=sharing)**

Place `weights.pth` in this directory.

## Usage

Run on the demo image:
```bash
python demo.py
```

Run on custom images:
```bash
python demo.py --image path/to/image.jpg --mask path/to/mask.jpg --output results/
```

The mask should be a grayscale image where white (255) = valid pixels, black (0) = ignored.

## Output

Results are saved to the `output/` directory:
- `input.png` - Resized input
- `mask.png` - Binary mask
- `albedo.png` - Predicted reflectance (min-max normalized)
- `normal.png` - Surface normals (RGB visualization)
- `shadow.png` - Shadow/shading intensity
- `shading.png` - Albedo × Shadow
