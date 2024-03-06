<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!-- <style>
  body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 20px;
  }
  h1, h2, h3 {
    color: #333;
  }
  section {
    margin-bottom: 20px;
  }
</style> -->
</head>
<body>

<h1>Software Requirements Specification (SRS)</h1>

<section>
  <h2>1. Introduction</h2>
  <p>This document serves as the Software Requirements Specification (SRS) for the Eye Blink Detection System. The purpose of this system is to detect and alert users when their eyes are closed for an extended period, indicating potential drowsiness or fatigue. The system utilizes computer vision techniques to analyze live video feed from a camera and detect the state of the user's eyes in real-time.</p>
</section>

<section>
  <h2>2. Scope</h2>
  <p>The Eye Blink Detection System is designed to be a standalone application that can be used by individuals to monitor their alertness levels while performing tasks that require sustained attention, such as driving or operating machinery. The system is implemented using Python programming language and various libraries such as OpenCV, dlib, and pygame.</p>
</section>

<section>
  <h2>3. Functional Requirements</h2>

  <h3>3.1. Eye Aspect Ratio Calculation</h3>
  <p>The system shall calculate the Eye Aspect Ratio (EAR) using the formula:<br>
    <code>EAR = (A + B) / (2.0 * C)</code><br>
    Where:<br>
    - A = Euclidean distance between two points on the eye (e.g., top and bottom)<br>
    - B = Euclidean distance between two other points on the eye (e.g., left and right)<br>
    - C = Euclidean distance between two fixed points on the eye (e.g., inner and outer corner)<br>
    The EAR calculation is performed for both the left and right eyes.</p>

  <h3>3.2. Eye Blink Detection</h3>
  <p>The system shall continuously analyze the live video feed from the camera to detect faces using the dlib library.<br>
    For each detected face, the system shall identify the landmarks of the eyes using a pre-trained shape predictor model.<br>
    Using the landmarks, the system shall calculate the EAR for each eye and compute the average EAR for both eyes.<br>
    If the average EAR falls below a predefined threshold (`thresh`), the system shall increment a counter (`flag`) to track consecutive frames where eyes are closed.<br>
    If the `flag` exceeds a specified threshold (`frame_check`), the system shall trigger an alert indicating potential drowsiness or fatigue.</p>

  <h3>3.3. Alerting Mechanism</h3>
  <p>When drowsiness is detected, the system shall display an alert message on the video feed indicating "ALERT: Wake Up".<br>
    Additionally, the system shall play an audio alert using the pygame library to further notify the user.</p>
</section>

<section>
  <h2>4. Non-Functional Requirements</h2>

  <h3>4.1. Performance</h3>
  <p>The system shall analyze video frames in real-time with minimal latency to provide timely alerts.<br>
    The system shall be optimized to run efficiently on a variety of hardware configurations.</p>

  <h3>4.2. Reliability</h3>
  <p>The system shall be robust to variations in lighting conditions, facial expressions, and head movements.<br>
    The system shall accurately detect eye blinks with high precision and minimal false positives.</p>
</section>

<section>
  <h2>5. Conclusion</h2>
  <p>The Eye Blink Detection System outlined in this document aims to provide users with a reliable tool for monitoring their alertness levels and preventing potential accidents due to drowsiness. By leveraging computer vision techniques, the system offers a non-intrusive solution for detecting signs of fatigue in real-time.</p>
</section>

</body>
</html>
