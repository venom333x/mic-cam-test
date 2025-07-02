<!DOCTYPE html>
<html>
<head>
  <title>Camera & Mic Access Test</title>
  <style>
    body {
      font-family: Arial;
      text-align: center;
      padding: 20px;
    }
    video {
      border: 2px solid black;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Camera & Microphone Test</h1>
  <p>Allow permissions when prompted to see your camera here:</p>
  <video id="video" width="640" height="480" autoplay muted></video>

  <script>
    async function startCam() {
      try {
        const stream = await navigator.mediaDevices.getUserMedia({ video: true, audio: true });
        const videoElement = document.getElementById('video');
        videoElement.srcObject = stream;
      } catch (err) {
        alert("Permission denied or device not available.");
        console.error(err);
      }
    }

    startCam();
  </script>
</body>
</html>
