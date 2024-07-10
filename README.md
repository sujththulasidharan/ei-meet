# ei-meet
meet 
<!DOCTYPE html>
<html>
<head>
    <title>Screen Sharing</title>
    <style>
        #videos {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        video {
            width: 80%;
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <h1>Screen Sharing Demo</h1>
    <button id="startButton">Start Screen Sharing</button>
    <div id="videos">
        <video id="localVideo" autoplay playsinline></video>
    </div>

    <script>
        const startButton = document.getElementById('startButton');
        const localVideo = document.getElementById('localVideo');

        startButton.addEventListener('click', async () => {
            try {
                const stream = await navigator.mediaDevices.getDisplayMedia({
                    video: true
                });
                localVideo.srcObject = stream;
            } catch (err) {
                console.error("Error: " + err);
            }
        });
    </script>
</body>
</html>
