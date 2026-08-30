## OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
Anaconda - Python 3.7
OpenCV
## Algorithm:
Step1:
Import the necessary packages

Step2:
Create the Text using cv2.putText

Step3:
Create the structuring element

Step4:
Use Opening operation

Step5:
Use Closing Operation

## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = np.zeros((500, 500, 3), dtype=np.uint8)
# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Iam Iron Man', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)
# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)
# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')
# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')
# Closing is dilation followed by erosion
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
closed_rgb = cv2.cvtColor(closed_image, cv2.COLOR_BGR2RGB)
plt.subplot(1,3,3)
plt.imshow(closed_rgb)
plt.title("Closing Operation")
plt.axis('off')
```
## Output:
<img width="713" height="548" alt="image" src="https://github.com/user-attachments/assets/563d1a74-e2e0-42cd-9acb-987efd511205" />
<img width="687" height="545" alt="image" src="https://github.com/user-attachments/assets/5c887fd2-8ae7-42c8-9f54-1550e65255f3" />
<img width="707" height="262" alt="image" src="https://github.com/user-attachments/assets/da14d31b-010f-4ae9-9a9a-f6a8a78be0e7" />

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
