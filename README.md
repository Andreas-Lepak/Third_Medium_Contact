# Third Medium Contact
This page aims to introduce Third Medium Contact for a broader audience


1. <video width="640" height="480" controls>
2.   <source src="Animations/ContinuumPotatoes.mp4" type="video/mp4">
3.   Your browser does not support the video tag.
4. </video>


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
