# Change-Image

To fullfil 1st Automating Real-World Task with Python on Bangkit : Google IT Automation with Python Course 


*Case : To resize, rotate, and change the format from list of image then save it to new file*

Here the code that i use when working on qwiklabs virtual machine  
- First we input python3 as the programming languages that we want to use  
#!/usr/bin/env python3  
- We import some module that we need, *PIL* for image manipulation, and *os* for interacting with operating system  
import PIL  
from PIL import Image  
import os  
- Declare the current working directory where we working in by *now* variable, the directory where the first image file that we want to use is located by *before* variable, last the directory to put the new image file after we change it  
now = os.getcwd()  
before = now + '/images/'  
after = '/opt/icons/'  
- Because there were many image, we want to list it to make it easy went we iterate the images  
image_list = os.listdir(before)  
- We iterate the image inside the image list  
for image in image_list:  
- Make an exception for the file that start with "." and end with "py"  
  if not image.startwith(".") and not image.endswith("py"):  
- Last we want to convert into "RGB" color, resize the image to 128x128, rotate it 90 degrees anti-clockwise or 270 degrees clockwise, and change the format into "jpeg"  
    reimage = Image.open(before + image)  
    reimage.convert("RGB").rotate(-90).resize((128,128)).save(after + image, "jpeg")  
