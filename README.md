<!--
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
-->
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
  <video id="videoElement4" width="640" height="480" style="position: absolute; top: 0; left: 0; display: none;" >
    <source src="Animations/PartialVideoFiles/BW_stamp.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <video id="videoElement5" width="640" height="480" style="position: absolute; top: 0; left: 0; display: none;" >
    <source src="Animations/PartialVideoFiles/stamp_full.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<script>
  const videoElement_1 = document.getElementById('videoElement1');
  const videoElement_2 = document.getElementById('videoElement2');
  const videoElement_3 = document.getElementById('videoElement3');
  const videoElement_4 = document.getElementById('videoElement4');
  const videoElement_5 = document.getElementById('videoElement5');
  let currentVideo = videoElement_1;

  function transitionToNextVideo() {
    if (currentVideo === videoElement_1) {
      videoElement_1.style.display = 'none';
      videoElement_2.style.display = 'block';
      currentVideo = videoElement_2;
    } else if (currentVideo === videoElement_2) {
      videoElement_2.style.display = 'none';
      videoElement_3.style.display = 'block';
      currentVideo = videoElement_3;
    } else if (currentVideo === videoElement_3) {
      videoElement_3.style.display = 'none';
      videoElement_4.style.display = 'block';
      currentVideo = videoElement_4;
    } else if (currentVideo === videoElement_4) {
      videoElement_4.style.display = 'none';
      videoElement_5.style.display = 'block';
      currentVideo = videoElement_5;
    } else if (currentVideo === videoElement_5) {
      // Optionally loop back to the beginning
      console.log("All videos have been shown.");
      // videoElement_5.style.display = 'none';
      // videoElement_1.style.display = 'block';
      // currentVideo = videoElement_1;
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

  // Transition to the next video when the current one ends
  videoElement_1.addEventListener('ended', transitionToNextVideo);
  videoElement_2.addEventListener('ended', transitionToNextVideo);
  videoElement_3.addEventListener('ended', transitionToNextVideo);
  videoElement_4.addEventListener('ended', transitionToNextVideo);
  // No 'ended' listener needed for the last video unless you want a specific action

  // Initially play the first video
  videoElement_1.play();
</script>








































<br><br><br><br><br><br><br><br><br><br><br>
