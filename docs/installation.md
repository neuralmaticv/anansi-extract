# Installation and Usage Guide

## Requirements

### Pot(j)era Requirements
- Python 3.x
- OpenCV (cv2)
- EasyOCR
- FFmpeg
- Potera or Potjera full episodes video files

### Slagalica Requirements
- Python 3.x
- OpenCV (cv2)
- EasyOCR
- Pytesseract
- FFmpeg
- Slagalica full episodes video files

### Pytesseract on Windows
Follow this guide:
https://stackoverflow.com/a/53672281

### Pytesseract on Linux
Follow this guide:
https://stackoverflow.com/a/52231794

## Installation

1. Clone the repository:
```bash
git clone https://github.com/neuralmaticv/anansi-extract.git
cd anansi-extract
```

2. Create virtual environment (Linux/MacOS):
```bash
python -m venv venv
source venv/bin/activate
```

2. Create virtual environment (Windows):
```bash
python -m venv venv
venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Main Scripts

1. **Slagalica Batch Processing**
```bash
python slagalica-batch-video.py -srcdir "path" -o "path"
```

Example:
```bash
python slagalica-batch-video.py -srcdir "../examples/testVideoBatch" -o "results" -csv "questions.csv" -d True -showt False
```

Arguments:
- `-srcdir`, `--source`: Directory with video files (default: "../examples/testVideoBatch")
- `-o`, `--output`: Directory for csv and debug data output (default: "results")
- `-lang`, `--language`: OCR language, can be either rs_latin or rs_cyrillic (default: "rs_cyrillic")
- `-csv`, `--csvFileName`: Name for csv file (default: "questions.csv")
- `-d`, `--debugData`: Create frame image files for every image processed (default: "True")
- `-showt`, `--showtime`: Create windows and preview of everything that is happening (default: "False")

2. **Potera Batch Processing**
```bash
python potera-batch-video.py -srcdir "path" -o "path"
```

Example:
```bash
python potera-batch-video.py -srcdir "../examples/testVideoBatch" -o "results" -lang "rs_cyrillic" -csv "questions.csv" -d True
```

Arguments:
- `-srcdir`, `--source`: Directory with video files (default: "../examples/testVideoBatch")
- `-o`, `--output`: Directory for csv and debug data output (default: "results")
- `-lang`, `--language`: OCR language, can be either rs_latin or rs_cyrillic (default: "rs_cyrillic")
- `-csv`, `--csvFileName`: Name for csv file (default: "questions.csv")
- `-d`, `--debugData`: Create frame image files for every image processed (default: "True")

### Helper Scripts

1. **Single Image Processing**
   - `potera-single-image.py`: Process a single frame (debugging)
   - `slagalica-single-image.py`: Process a single frame (debugging)

2. **Single Video Processing**
   - `potera-single-video.py`: Process a single video file
   - `slagalica-single-video.py`: Process a single video file

3. **Debugging Tools**
   - `slagalica-z-image-diff-test.py`: Find differences between two images
   - `slagalica-z-threshold-finder.py`: Find correct values for global thresholding
   - `slagalica-z-file-renamer.py`: Rename batch of files with custom template matching

