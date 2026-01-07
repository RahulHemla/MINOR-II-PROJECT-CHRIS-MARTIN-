# ASCII Art Generator using NumPy and Matplotlib

## 📌 Project Description

This project converts an image of a famous person into **ASCII art** using Python. The image is processed by converting it into grayscale, resizing it to a small dimension, and mapping pixel intensities to ASCII characters. The final output is displayed directly in the console.

The project is implemented using **NumPy** for numerical operations and **Matplotlib** for reading the image.

---

## 🛠️ Technologies Used

* **Python**
* **NumPy** – for array and pixel processing
* **Matplotlib** – for loading the image

---

## 📂 Project Structure

```
ASCII-Art-Project/
│── chris_martin.jpg
│── ascii_art.py
│── README.md
```

---

## ▶️ How to Run the Project

1. Open **Google Colab** or any Python environment
2. Upload the image file (e.g., `chris_martin.jpg`)
3. Copy the code into a Python file or notebook
4. Run the program
5. ASCII art will be displayed in the output

---

## 💻 Code Used

```python
import numpy as np
import matplotlib.pyplot as plt

ascii_chars = np.array(list("@%#*+=-:. "))

img = plt.imread("chris_martin.jpg")

if img.ndim == 3:
    img = img.mean(axis=2)
new_width = 40
new_height = 2

h, w = img.shape
x_idx = np.linspace(0, w - 1, new_width).astype(int)
y_idx = np.linspace(0, h - 1, new_height).astype(int)
img = img[y_idx][:, x_idx]

img = img / img.max()


ascii_img = ascii_chars[(img * (len(ascii_chars) - 1)).astype(int)]


for row in ascii_img:
    print("".join(row))
```

---

## 🧠 Working Explanation

* The image is loaded using Matplotlib and stored as a NumPy array.
* Color images are converted to grayscale for simpler processing.
* The image is resized to a small width and height for compact ASCII output.
* Pixel values are normalized between 0 and 1.
* Each pixel intensity is mapped to an ASCII character based on brightness.
* The ASCII characters are printed row by row to form the final image.

---

## ✅ Features

* Small and clear ASCII output
* Uses simple and readable code
* Works in Google Colab
* Suitable for academic projects

---

## 🎯 Conclusion

This project demonstrates how basic image processing can be performed using Python to generate ASCII art. It is a simple and effective way to understand pixel manipulation using NumPy and Matplotlib.

---

## 👤 Author

**Rahul Kumar Hemla**
