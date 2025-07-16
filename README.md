# Image Steganography

A Python-based GUI application for hiding and extracting secret text messages within image files using steganography techniques.

## Overview

This application implements LSB (Least Significant Bit) steganography to hide text messages inside images. The program provides an intuitive graphical interface built with Tkinter that allows users to:

- **Encode**: Hide secret text messages within image files
- **Decode**: Extract hidden messages from steganographic images

## Features

- **User-friendly GUI**: Clean and intuitive interface built with Tkinter
- **Multiple image formats**: Supports PNG, JPEG, and JPG image files
- **LSB Steganography**: Uses Least Significant Bit technique for data hiding
- **Image preview**: Shows selected images before processing
- **Information display**: Provides details about original and processed images
- **Save functionality**: Saves encoded images with hidden messages

## Requirements

### Python Dependencies
```
tkinter (usually comes with Python)
PIL (Pillow)
```

### Installation

1. **Clone or download** this repository
2. **Install required packages**:
   ```bash
   pip install Pillow
   ```

## Usage

### Running the Application

1. **Execute the Python script**:
   ```bash
   python steganography.py
   ```
   or if using Jupyter Notebook:
   ```bash
   jupyter notebook Python\ project.ipynb
   ```

2. **Main Menu**: The application will open with two main options:
   - **Encode**: Hide text in an image
   - **Decode**: Extract hidden text from an image

### Encoding Process

1. Click **"Encode"** from the main menu
2. Click **"Select"** to choose an image file
3. Browse and select your cover image (PNG, JPEG, or JPG)
4. Enter your secret message in the text area
5. Click **"Encode"** to process
6. Choose where to save the output image
7. The encoded image will be saved as a PNG file

### Decoding Process

1. Click **"Decode"** from the main menu
2. Click **"Select"** to choose an image with hidden data
3. Browse and select the steganographic image
4. The hidden message will be automatically extracted and displayed
5. Click **"More Info"** to see image details and statistics

## How It Works

### LSB Steganography Technique

The application uses the Least Significant Bit (LSB) method:

1. **Encoding**:
   - Converts the secret message into binary format
   - Modifies the least significant bits of RGB pixel values
   - Uses 8 bits across 3 pixels (9 RGB values) to encode each character
   - Adds a delimiter to mark the end of the hidden message

2. **Decoding**:
   - Extracts the least significant bits from pixel values
   - Reconstructs the binary message
   - Converts binary back to readable text
   - Stops when the delimiter is reached

## File Structure

```
steganography/
│
├── Python project.ipynb    # Main application file (Jupyter Notebook)
├── README.md              # This file
└── encoded_images/        # Directory for saved encoded images (created automatically)
```

## Supported Image Formats

- **Input**: PNG, JPEG, JPG
- **Output**: PNG (recommended for lossless compression)

## Technical Details

### Key Components

- **GUI Framework**: Tkinter for the graphical interface
- **Image Processing**: PIL (Python Imaging Library) for image manipulation
- **Steganography Algorithm**: Custom LSB implementation
- **Data Handling**: Binary conversion and pixel manipulation

### Security Considerations

- This is a basic steganography implementation for educational purposes
- The hidden data is not encrypted, only hidden
- For sensitive applications, consider adding encryption before hiding the data
- PNG format is recommended for output to avoid compression artifacts

## Limitations

- **Image Size**: The cover image must be large enough to hold the message
- **File Format**: Best results with PNG images due to lossless compression
- **Message Length**: Limited by the number of pixels in the cover image
- **Detection**: Advanced steganalysis tools may detect the presence of hidden data

## Troubleshooting

### Common Issues

1. **"Nothing Selected" Error**: Make sure to select a valid image file
2. **Empty Message**: Ensure you enter text before encoding
3. **File Format Issues**: Use PNG images for best results
4. **Permission Errors**: Check file permissions in the save directory

### Tips

- Use high-resolution images for larger messages
- Save encoded images as PNG to preserve hidden data
- Keep original images as backup
- Test with simple messages first

## Future Enhancements

Potential improvements for this project:

- Add password protection/encryption
- Support for hiding files (not just text)
- Implement advanced steganography techniques
- Add compression for larger messages
- Include steganalysis detection features
- Support for more image formats

## Educational Purpose

This project is designed for educational purposes to demonstrate:
- Basic steganography concepts
- GUI development with Python
- Image processing techniques
- Binary data manipulation
- File handling in Python

## License

This project is open source and available for educational and non-commercial use.

## Contributing

Feel free to fork this project and submit pull requests for improvements or bug fixes.

---

**Note**: This application is for educational purposes. For production use, consider implementing additional security measures and encryption.
