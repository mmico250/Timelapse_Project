# Timelapse_Project
Python program that captures image, creates a folder and saves it at that folder in the location where program is run from. The goal of the project is to automate the process using the windows task scheduler to call it at regular time intervals. The resulting images can then be compiled into a timelapse
Steps
1. Install Python: If you don't have Python installed on your computer, download and install the latest version from the official Python website (https://www.python.org/downloads/). Make sure to select the option to add Python to your system's PATH during the installation process.
2. Install OpenCV: Open a command prompt or terminal and run the following command to install the OpenCV library using pip, the Python package installer:
py -m pip install opencv-python
3. Create a Python script: Open a text editor or an integrated development environment (IDE) and create a new Python script, for example, capture_image.py.
4. Import necessary libraries: Add the following lines at the beginning of your script to import the required libraries:
import cv2 
import datetime 
5. Set up the webcam: Add the following code to initialize the webcam:
webcam = cv2.VideoCapture(0) 
6. This assumes that your webcam is connected to your computer and recognized as device 0. If you have multiple cameras, you may need to adjust this value accordingly.
7. Capture and save an image: Use the following code to capture an image using the webcam and save it with a timestamp:
ret, frame = webcam.read()
if ret: timestamp = datetime.datetime.now().strftime("%Y%m%d%H%M%S") image_path = f"image_{timestamp}.jpg" cv2.imwrite(image_path, frame) 
8. This code captures a frame from the webcam, generates a timestamp using the current date and time, and saves the image as a JPG file with a unique filename.
9. Schedule the script: To run this script once every day, you can use the built-in task scheduler or a cron job depending on your operating system. Configure the scheduler to execute the Python script at a specific time each day.
10. Make sure to save the Python script and run it at least once manually to test if the webcam captures an image and saves it successfully.
11. Download the code as a name.py file



NOTES ON USING COMMAND PROMPT.

1. Verify python install using command:
py --version or python --version
2. Verify pip install using command:
py -m pip --version or pip --version
3. Generating a .exe file from a .py file
Depending on the path result from the above code, use this command:
    "C:\Users\mmico\AppData\Local\Programs\Python\Python311\Scripts\pyinstaller.exe" --onefile --name_of_exe_file timelapse name.py
Or
pyinstaller --onefile pythonScriptName.py


