# INFORMATION ON VARIOUS COMPUTER VISION CONCEPTS
- Before an image is fed into an AI model (like a neural network), it almost always undergoes Preprocessing.
- Three core OpenCV techniques :
  1. Resizing (Normalization for Neural Networks)AI models require all input images to be the exact same size (e.g., 224 × 224 for ResNet).
      ```
          # Resize to a specific width and height
          resized_img = cv2.resize(img, (224, 224))
      ```
  2. Thresholding (Binarization)This turns a grayscale image into a pure Black and White image (no grays). It is used to separate objects from the background.
       ```
       # Any pixel above 127 becomes 255 (white), below becomes 0 (black)
        _, binary_img = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)
       ```
  3. Image Normalization (For Deep Learning)Neural networks hate large numbers like 255 because they cause exploding gradients. We scale the pixels down to a range of 0.0 to 1.0.
       ```
       # Convert integer values (0-255) to float values (0.0 - 1.0)
        normalized_img = img.astype("float32") / 255.0
       ```

## Understanding Image Structure in RAM
- ran ```print("Data Type:", img.dtype )```, it printed ```uint8```.
- What it <b>means</b>: uint8 stands for Unsigned Integer (8-bit).
- The Math: 8 bits can store 2⁸ = 256 possible values.
- Because it is unsigned (no negative numbers), the values range from 0 to 255.
- How pixels work : In the gray image, each pixel is a single number from 0 (pure black) to 255 (pure white).
- In the ```img (color)``` image, each pixel is a list of 3 numbers [B, G, R], each ranging from 0 to 255.

- OpenCV speaks "BGR language".Matplotlib speaks "RGB language".
- Back when OpenCV was created in 1999, the standard format for digital cameras and Windows graphics software was BGR (Blue, Green, Red).
- OpenCV adopted this standard and kept it to avoid breaking millions of existing codebases.
