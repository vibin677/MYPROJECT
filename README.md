# Image Steganography

This Python script implements a simple image steganography technique to hide a secret message within an image.

## Overview

The script allows you to:

1.  **Encrypt** a secret message into an image by modifying the least significant bits of the pixel values.
2.  **Decrypt** the hidden message from the encrypted image using a passcode.

## How it Works

* **Encryption:**
    * The script reads an image.
    * It takes a secret message and a passcode as input.
    * It converts each character of the message into its ASCII value.
    * It iterates through the image pixels, modifying the RGB values to store the ASCII values of the message characters.
    * The modified image is saved as `encryptedImage.jpg`.
* **Decryption:**
    * The script prompts for the passcode.
    * If the passcode matches the original passcode, it reads the `encryptedImage.jpg`.
    * It extracts the ASCII values from the modified pixels.
    * It converts the ASCII values back into characters, reconstructing the original message.
    * The decrypted message is printed.
    * If the passcode does not match, the program outputs "YOU ARE NOT auth".

## Prerequisites

* Python 3.x
* OpenCV (cv2) library: `pip install opencv-python`
* An image file (e.g., `download.jpg`).

## Usage

1.  **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2.  **Place your image file (e.g., `download.jpg`) in the same directory as the script.**

3.  **Run the script:**

    ```bash
    python your_script_name.py
    ```

4.  **Follow the prompts:**
    * Enter the secret message.
    * Enter a passcode.
    * The encrypted image will be generated and opened.
    * To decrypt, run the script again, and when prompted enter the passcode used for encryption.

## Important Notes

* This is a basic implementation and may not be suitable for high-security applications.
* The length of the message that can be hidden depends on the size of the image. Larger images can hold longer messages.
* The script uses a very simple method of steganography, and is easily detectable.
* The script is designed to open the image using the `start` command, which is specific to Windows. For other operating systems, you may need to modify the `os.system()` call.
* The script assumes that the image is a standard RGB image.
* Replace `"download.jpg"` with the correct path to your image file.
* Replace `"your_script_name.py"` with the actual filename of your python script.

## Improvements

* Implement more robust steganography techniques.
* Add error handling for invalid input.
* Support different image formats.
* Add command-line arguments for input and output files.
* Cross-platform compatibility for opening the image.
* Add a GUI.
* Increase the amount of data that can be hidden.
