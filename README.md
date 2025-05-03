
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
