# WorkShop 3: Canny Edge Detection
## Name: Ramkumar G
## Reg No: 212223220084

# Program
```

import cv2
import matplotlib.pyplot as plt

# Step 1: Read an image (replace with your own)
image_path = "Lion king.jpg"  # You can use any sample image
image = cv2.imread(image_path)

if image is None:
    raise FileNotFoundError("Image not found! Please check your path or filename.")

# Step 2: Convert to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Step 3: Apply Gaussian Blur to remove noise
blurred = cv2.GaussianBlur(gray, (5, 5), 1.4)

# Step 4: Apply Canny Edge Detection with varying thresholds
edges_low = cv2.Canny(blurred, 50, 100)    # Detects more edges (including weak)
edges_medium = cv2.Canny(blurred, 100, 200) # Balanced detection
edges_high = cv2.Canny(blurred, 150, 250)   # Detects fewer, stronger edges

# Step 5: Display results
plt.figure(figsize=(14, 8))

plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis("off")

plt.subplot(2, 2, 2)
plt.imshow(edges_low, cmap='gray')
plt.title("Edges (Thresholds: 50–100)")
plt.axis("off")

plt.subplot(2, 2, 3)
plt.imshow(edges_medium, cmap='gray')
plt.title("Edges (Thresholds: 100–200)")
plt.axis("off")

plt.subplot(2, 2, 4)
plt.imshow(edges_high, cmap='gray')
plt.title("Edges (Thresholds: 150–250)")
plt.axis("off")
plt.tight_layout()
plt.show()

```
# Output
<img width="1283" height="790" alt="download" src="https://github.com/user-attachments/assets/b964a479-1a0f-49ae-90d7-b67d7bb886d1" />

