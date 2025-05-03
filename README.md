# Third Medium Contact


<video id="myVideo" width="640" height="480">
  <source src="Animations/PartialVideoFiles/k1.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<script>
  const video = document.getElementById('myVideo');
  video.addEventListener('click', function() {
    if (video.paused || video.ended) {
      video.play();
    } else {
      video.pause();
    }
  });
</script>

## test 2
<video id="myVideo" width="640" height="480" controls></video>

<script>
  const video = document.getElementById('myVideo');
  const videoSources = [
    "Animations/PartialVideoFiles/k1.mp4",
    "Animations/PartialVideoFiles/k2.mp4",
    "Animations/PartialVideoFiles/k3.mp4"
    // Add more video paths here
  ];
  let currentVideoIndex = 0;

  function loadVideo(index) {
    if (index < videoSources.length) {
      video.innerHTML = `<source src="${videoSources[index]}" type="video/mp4">`;
      video.load();
    } else {
      console.log('End of video sequence.');
      // Optionally clear the video or loop back
      // video.innerHTML = '';
      currentVideoIndex = 0; // Loop back to the first video on next click
    }
  }

  video.addEventListener('click', function() {
    if (video.paused || video.ended || video.src === "") {
      loadVideo(currentVideoIndex);
      video.play();
      currentVideoIndex++;
      if (currentVideoIndex >= videoSources.length) {
        currentVideoIndex = 0; // Reset for the next sequence
      }
    } else {
      video.pause();
    }
  });

  // Load the first video on initial page load (but don't play)
  if (videoSources.length > 0) {
    loadVideo(0);
    video.pause(); // Ensure it doesn't auto-play
  }
</script>

## Test 3

<div style="position: relative; width: 640px; height: 480px;">
  <video id="baseVideo" width="640" height="480">
    <source src="Animations/PartialVideoFiles/k1.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <video id="overlayVideo" width="640" height="480" style="position: display: none;" >
    <source src="Animations/PartialVideoFiles/k2.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<script>
  const baseVideo = document.getElementById('baseVideo');
  const overlayVideo = document.getElementById('overlayVideo');

  baseVideo.addEventListener('ended', function() {
    overlayVideo.style.display = 'block';
    overlayVideo.play(); // Optionally start the overlay video immediately
  });

  // Optional: Make the base video clickable to play/pause
  baseVideo.addEventListener('click', function() {
    if (baseVideo.paused || baseVideo.ended) {
      baseVideo.play();
    } else {
      baseVideo.pause();
    }
  });
</script>

 
## Test 4
<div style="position: relative; width: 640px; height: 480px;">
  <video id="video1" width="640" height="480">
    <source src="Animations/PartialVideoFiles/k1.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <video id="video2" width="640" height="480" style="position: absolute; top: 0; left: 0; display: none;" >
    <source src="Animations/PartialVideoFiles/k2.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <video id="video3" width="640" height="480" style="position: absolute; top: 0; left: 0; display: none;" >
    <source src="Animations/PartialVideoFiles/k3.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<script>
  const video1 = document.getElementById('video1');
  const video2 = document.getElementById('video2');
  const video3 = document.getElementById('video3');
  let currentVideo = video1;

  video1.addEventListener('ended', function() {
    video1.style.display = 'none';
    video2.style.display = 'block';
    video2.play();
    currentVideo = video2;
  });

  video2.addEventListener('ended', function() {
    video2.style.display = 'none';
    video3.style.display = 'block';
    video3.play();
    currentVideo = video3;
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
  // video1.play();
</script>
