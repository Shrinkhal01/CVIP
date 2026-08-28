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
       
