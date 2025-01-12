# Helmet Detection & License Plate Extraction System

Real-time computer vision system for traffic monitoring and enforcement, featuring helmet detection and license plate extraction with high accuracy and performance.

## Features

- Real-time helmet detection using SSD MobileNet
- License plate extraction with OCR
- Adaptive thresholding for varying lighting conditions
- Multi-threaded processing for high performance
- 95% detection accuracy
- Sub-200ms processing time per frame

## Technical Architecture

### Detection Module
- **Model**: SSD MobileNet v2 on TensorFlow
- **Input**: Real-time video frames
- **Output**: Bounding boxes for helmets and license plates
- **Performance**: 95% accuracy in varied conditions

### License Plate Extraction
- **Preprocessing**: Adaptive thresholding
- **OCR Engine**: Tesseract with custom configuration
- **Post-processing**: Text cleaning and validation
- **Accuracy**: High consistency across different lighting conditions

### Performance Optimization
- Multi-threaded frame processing
- Batch prediction support
- Efficient memory management
- Processing time: <200ms per frame

## Requirements

```
python>=3.8
tensorflow>=2.4.0
opencv-python>=4.5.0
pytesseract>=0.3.8
numpy>=1.19.0
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/helmet-license-detection.git
cd helmet-license-detection
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Download the pre-trained model:
```bash
python scripts/download_model.py
```

## Usage

### Basic Usage
```python
from helmet_detection import DetectionSystem

# Initialize the system
detector = DetectionSystem(
    model_path='models/ssd_mobilenet_v2.pb',
    confidence_threshold=0.85
)

# Process single image
results = detector.process_image('path/to/image.jpg')

# Process video stream
detector.process_video_stream('rtsp://camera_stream_url')
```

### Advanced Configuration
```python
# Custom threading configuration
detector.set_thread_count(4)

# Adjust detection parameters
detector.configure({
    'min_detection_confidence': 0.85,
    'min_plate_size': (80, 20),
    'enable_gpu': True
})
```

## Performance Metrics

- **Detection Accuracy**: 95% on benchmark dataset
- **Processing Speed**: <200ms per frame
- **False Positive Rate**: <3%
- **License Plate Read Accuracy**: 92% in daylight conditions


## Acknowledgments

- TensorFlow team for SSD MobileNet implementation
- OpenCV community for image processing tools
- Tesseract OCR project team

----------------
