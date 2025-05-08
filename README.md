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

<video id="myVideo2" width="640" height="480">
  <source src="Animations/PartialVideoFiles/k1.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<script>
  const videoElement2 = document.getElementById('myVideo2');
  videoElement2.addEventListener('click', function() {
    if (videoElement2.paused || videoElement2.ended) {
      videoElement2.play();
    } else {
      videoElement2.pause();
    }
  });
</script>

## test 1

<video id="myVideo3" width="640" height="480">
  <source src="Animations/ContinuumPotatoes.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<script>
  const videoElement3 = document.getElementById('myVideo3');
  videoElement3.addEventListener('click', function() {
    if (videoElement3.paused || videoElement3.ended) {
      videoElement3.play();
    } else {
      videoElement3.pause();
    }
  });
</script>

## test 2
<video id="myVideo4" width="640" height="480" controls></video>

<script>
  const videoElement4 = document.getElementById('myVideo4');
  const videoSources = [
    "Animations/PartialVideoFiles/k1.mp4",
    "Animations/PartialVideoFiles/k2.mp4",
    "Animations/PartialVideoFiles/k3.mp4"
    // Add more video paths here
  ];
  let currentVideoIndex = 0;

  function loadVideo(index) {
    if (index < videoSources.length) {
      videoElement4.innerHTML = `<source src="${videoSources[index]}" type="video/mp4">`;
      videoElement4.load();
    } else {
      console.log('End of video sequence.');
      // Optionally clear the video or loop back
      // videoElement4.innerHTML = '';
      currentVideoIndex = 0; // Loop back to the first video on next click
    }
  }

  videoElement4.addEventListener('click', function() {
    if (videoElement4.paused || videoElement4.ended || videoElement4.src === "") {
      loadVideo(currentVideoIndex);
      videoElement4.play();
      currentVideoIndex++;
      if (currentVideoIndex >= videoSources.length) {
        currentVideoIndex = 0; // Reset for the next sequence
      }
    } else {
      videoElement4.pause();
    }
  });

  // Load the first video on initial page load (but don't play)
  if (videoSources.length > 0) {
    loadVideo(0);
    videoElement4.pause(); // Ensure it doesn't auto-play
  }
</script>



## Test 3 v2

<div style="position: relative; width: 640px; height: 480px;">
  <video id="baseVideo" width="640" height="480">
    <source src="Animations/PartialVideoFiles/k1.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <video id="overlayVideo" width="640" height="480" style="position: absolute; top: 0; left: 0; display: none;" >
    <source src="Animations/PartialVideoFiles/k2.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<script>
  const baseVideo = document.getElementById('baseVideo');
  const overlayVideo = document.getElementById('overlayVideo');
  let firstVideoEnded = false;

  baseVideo.addEventListener('ended', function() {
    baseVideo.style.display = 'none';
    overlayVideo.style.display = 'block';
    overlayVideo.play();
    firstVideoEnded = true;
  });

  // Control playback of the current visible video on click
  document.addEventListener('click', function(event) {
    if (event.target === baseVideo && !firstVideoEnded) {
      if (baseVideo.paused || baseVideo.ended) {
        baseVideo.play();
      } else {
        baseVideo.pause();
      }
    } else if (event.target === overlayVideo && firstVideoEnded) {
      if (overlayVideo.paused || overlayVideo.ended) {
        overlayVideo.play();
      } else {
        overlayVideo.pause();
      }
    }
  });

  // Optionally start the first video on page load
  // baseVideo.play();
</script>


## Test 4
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

  videoElement_1.addEventListener('ended', function() {
    videoElement_1.style.display = 'none';
    videoElement_2.style.display = 'block';
    videoElement_2.play();
    currentVideo = videoElement_2;
  });

  videoElement_2.addEventListener('ended', function() {
    videoElement_2.style.display = 'none';
    videoElement_3.style.display = 'block';
    videoElement_3.play();
    currentVideo = videoElement_3;
  });

  // Optional: Make the current video clickable to play/pause
  document.addEventListener('click', function(event) {
    if (event.target === currentVideo) {
      if (currentVideo.paused || currentVideo.ended) {
        currentVideo.play();
      } else {
        currentVideo.pause();
      }
    }
  });

  // Optional: Start the first video on page load
  // videoElement_1.play();
</script>
