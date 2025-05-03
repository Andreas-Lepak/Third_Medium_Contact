
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


<div style="position: relative; display: inline-block;">
  <video id="myVideo" width="640" height="480" style="display: block;">
    <source src="Animations/ContinuumPotatoes.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <div id="playOverlay" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.5); color: white; font-size: 24px; display: flex; justify-content: center; align-items: center; cursor: pointer;">
    Click to start animation
  </div>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    const video = document.getElementById('myVideo');
    const playOverlay = document.getElementById('playOverlay');

    function updateOverlayVisibility() {
      if (video.paused || video.ended) {
        playOverlay.style.display = 'flex';
      } else {
        playOverlay.style.display = 'none';
      }
    }

    // Initial state on load
    updateOverlayVisibility();

    video.addEventListener('click', function() {
      if (video.paused || video.ended) {
        video.play();
      } else {
        video.pause();
      }
      updateOverlayVisibility(); // Update overlay after play/pause
    });

    video.addEventListener('play', function() {
      updateOverlayVisibility();
    });

    video.addEventListener('pause', function() {
      updateOverlayVisibility();
    });

    video.addEventListener('ended', function() {
      updateOverlayVisibility();
    });
  });
</script>
