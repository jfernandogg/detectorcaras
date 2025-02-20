# AI-Powered Human Detection for Rack Security Monitoring

## Overview
This project implements **real-time human detection** using a Hikvision camera to monitor IT rack access. It enhances security by identifying unauthorized personnel and capturing evidence.

## Features
- **Real-time video streaming** from a Hikvision camera using RTSP.
- **Face detection** using a pre-trained Caffe model.
- **Bounding box visualization** for detected faces.
- **Automated image capture** when a face is detected.
- **Live monitoring interface** with a manual exit option.

## Technology Stack
- **Programming Language:** Python 2.7
- **Machine Learning Framework:** OpenCV Deep Neural Networks (DNN)
- **Model:** `res10_300x300_ssd_iter_140000.caffemodel`
- **Hardware:** Hikvision IP Camera (RTSP stream)
- **Libraries:** OpenCV, NumPy, Imutils

## Installation
### Prerequisites
Ensure you have Python 2.7 and the required dependencies installed:

```sh
pip install numpy opencv-python imutils
```

### Clone the Repository
```sh
git clone https://github.com/yourusername/rack-security-monitoring.git
cd rack-security-monitoring
```

### Running the Script
```sh
python detect_faces_video.py --prototxt deploy.prototxt.txt --model res10_300x300_ssd_iter_140000.caffemodel --confidence 0.5
python2 ./scanrtsp.py -p deploy.prototxt.txt -c 0.3 -m res10_300x300_ssd_iter_140000.caffemodel
```

## Usage
- The script connects to the RTSP camera stream and starts real-time monitoring.
- If a human face is detected, a bounding box is drawn around it.
- The first detected frame is saved as an image for security records.
- Press **'q'** to exit the monitoring session.

## Customization
- Adjust the **confidence threshold** using the `--confidence` flag.
- Modify the **RTSP stream URL** in `cv2.VideoCapture("rtsp://user:password@camera-ip/")`.
- Extend the project to send real-time alerts via email or messaging services.

## Future Enhancements
- Implement a **notification system** for real-time alerts.
- Add support for **multi-camera monitoring**.
- Integrate with **cloud storage** for evidence retention.
- Edit code to change RTSP url and user password authentication

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contributing
Pull requests are welcome! Feel free to open an issue for feature requests or bug reports.

## Author
[Juan F Gallego](https://github.com/jfernandogg)
