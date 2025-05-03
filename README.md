# Third Medium Contact


<video id="myVideo" width="640" height="480">
  <source src="Animations/ContinuumPotatoes.mp4" type="video/mp4">
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
