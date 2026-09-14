# 🖼️ Batch Image to WebP Converter

สคริปต์ Python พื้นฐานสำหรับแปลงไฟล์รูปภาพ (JPG/PNG) เป็น WebP แบบจำนวนมาก (Batch Processing) เพื่อนำไปใช้งานในการทำ SEO On-page และเพิ่มความเร็วเว็บไซต์

## 💻 Requirements
* Python 3.x
* Pillow library (`pip install Pillow`)

## 🛠️ Script (webp_converter.py)
```python
import os
from PIL import Image

def convert_to_webp(source_folder, quality=80):
    for filename in os.listdir(source_folder):
        if filename.endswith(".jpg") or filename.endswith(".png"):
            filepath = os.path.join(source_folder, filename)
            img = Image.open(filepath)

            webp_filename = filename.rsplit('.', 1)[0] + '.webp'
            webp_filepath = os.path.join(source_folder, webp_filename)

            img.save(webp_filepath, 'webp', quality=quality)
            print(f"Converted: {filename} -> {webp_filename}")

# Example usage:
# convert_to_webp('./images')
