<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Music Streaming & Upload</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        #player { margin-top: 20px; }
        .track-list { margin-top: 20px; }
        .track { cursor: pointer; padding: 5px; }
        .track:hover { background-color: #f0f0f0; }
    </style>
</head>
<body>
    <h1>Music Streaming & Upload</h1>
    
    <audio id="player" controls>
        <source id="audioSource" src="" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    
    <div class="track-list" id="trackList">
        <h2>Available Tracks</h2>
        <div class="track" onclick="playTrack('sample1.mp3')">🎵 Sample Track 1</div>
        <div class="track" onclick="playTrack('sample2.mp3')">🎵 Sample Track 2</div>
    </div>
    
    <h2>Upload Your Music</h2>
    <input type="file" id="fileInput" accept="audio/*">
    <button onclick="uploadFile()">Upload</button>
    
    <script>
        function playTrack(src) {
            document.getElementById("audioSource").src = src;
            document.getElementById("player").load();
            document.getElementById("player").play();
        }
        
        function uploadFile() {
            let fileInput = document.getElementById("fileInput");
            let file = fileInput.files[0];
            if (file) {
                alert("File uploaded: " + file.name);
                // In a real application, send the file to a backend server
            } else {
                alert("Please select a file first.");
            }
        }
    </script>
</body>
</html>
