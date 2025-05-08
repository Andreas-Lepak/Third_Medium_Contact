This is currently a testpage

<video id="myVideo1" width="640" height="480">
  <source src="Animations/PartialVideoFiles/k1.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<script>
  const videoElement1 = document.getElementById('myVideo1');
  videoElement1.addEventListener('click', function() {
    if (videoElement1.paused || videoElement1.ended) {
      videoElement1.play();
    } else {
      videoElement1.pause();
    }
  });
</script>

## test 0

<div style="position: relative; width: 640px; height: 480px;">
  <video id="videoElement1" width="640" height="480">
    <source src="Animations/PartialVideoFiles/k1.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <video id="videoElement2" width="640" height="480" style="position: absolute; top: 0; left: 0; display: none;" >
    <source src="Animations/PartialVideoFiles/k2.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <video id="videoElement3" width="640" height="480" style="position: absolute; top: 0; left: 0; display: none;" >
    <source src="Animations/PartialVideoFiles/k3.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<script>
  const videoElement_1 = document.getElementById('videoElement1');
  const videoElement_2 = document.getElementById('videoElement2');
  const videoElement_3 = document.getElementById('videoElement3');
  let currentVideo = videoElement_1;

  function playNextVideo() {
    if (currentVideo === videoElement_1) {
      videoElement_1.style.display = 'none';
      videoElement_2.style.display = 'block';
      currentVideo = videoElement_2;
      currentVideo.play();
    } else if (currentVideo === videoElement_2) {
      videoElement_2.style.display = 'none';
      videoElement_3.style.display = 'block';
      currentVideo = videoElement_3;
      currentVideo.play();
    } else if (currentVideo === videoElement_3) {
      // Optionally loop back to the first video or do nothing
      // videoElement_3.style.display = 'none';
      // videoElement_1.style.display = 'block';
      // currentVideo = videoElement_1;
      // currentVideo.play();
      console.log("All videos have played.");
    }
  }

  // Play/pause the current video on click
  document.addEventListener('click', function(event) {
    if (event.target === currentVideo) {
      if (currentVideo.paused || currentVideo.ended) {
        currentVideo.play();
      } else {
        currentVideo.pause();
      }
    }
  });

  // Proceed to the next video after the current one ends
  videoElement_1.addEventListener('ended', playNextVideo);
  videoElement_2.addEventListener('ended', playNextVideo);
  // We don't need an 'ended' listener for the last video unless you want to loop or trigger something else

  // Start the first video on page load
  videoElement_1.play();
</script>
