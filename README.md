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

## test

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

  function playCurrentVideo() {
    video.innerHTML = `<source src="${videoSources[currentVideoIndex]}" type="video/mp4">`;
    video.load(); // Important: Reload the video element to apply the new source
    video.play();
  }

  video.addEventListener('ended', function() {
    currentVideoIndex++;
    if (currentVideoIndex < videoSources.length) {
      playCurrentVideo();
    } else {
      // Optionally handle what happens after the last video
      console.log('All videos played!');
    }
  });

  video.addEventListener('click', function() {
    if (video.paused || video.ended) {
      playCurrentVideo();
    } else {
      video.pause();
    }
  });

  // Play the first video on initial load if you want
  // playCurrentVideo();
</script>
