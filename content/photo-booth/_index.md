---
title: "Photo Booth"
date: 2023-01-09T14:38:57-05:00
draft: false
---

<h1>Upload your picture and add some Cheems love!</h1>
<form>
  <input type="file" name="picture" accept="image/*">
  <input type="button" value="Upload" id="upload-button">
</form>
<!-- The modal -->
<div id="myModal" style="display: none; position: fixed; z-index: 1; padding-top: 100px; left: 0; top: 0; width: 100%; height: 100%; overflow: auto; background-color: rgb(0, 0, 0); background-color: rgba(0, 0, 0, 0.4);">
  <!-- The modal content -->
  <div style="background-color: #fefefe; margin: auto; padding: 20px; border: 1px solid #888; width: 80%;">
    <span style="color: #aaaaaa; float: right; font-size: 28px; font-weight: bold;" onclick="document.getElementById('myModal').style.display='none'">&times;</span>
    <canvas></canvas>
  </div>
</div>

<script type="text/javascript">
function photoshop(canvas, originalImage, cheemsImage) {
  // Get the canvas context
  const ctx = canvas.getContext('2d');

  // Set the dimensions of the canvas to the dimensions of the original image
  canvas.width = originalImage.width;
  canvas.height = originalImage.height;

  // Draw the original image on the canvas
  ctx.drawImage(originalImage, 0, 0);

  // Scale the Cheems image to the size of the original image and set its global alpha to 30%
  ctx.globalAlpha = 0.3;
  // Draw the Cheems image on the canvas
  ctx.drawImage(cheemsImage, 0, 0);
  ctx.globalAlpha = 1.0; // Reset the global alpha to 100%

  // Set the font and color for the text
  ctx.font = '36px sans-serif';
  ctx.fillStyle = 'white';

  // Set the font, color, and stroke for the text
  ctx.font = '72px Impact';
  ctx.fillStyle = 'white';
  ctx.strokeStyle = 'black';

  // Measure the width of the text
  const textWidth = ctx.measureText('cheemsloves.me').width;

  // Calculate the x coordinate for the text
  const x = (canvas.width - textWidth) / 2;

  // Draw the text on the canvas
  ctx.fillText('cheemsloves.me', x, 50);
  ctx.strokeText('cheemsloves.me', x, 50);
}

// Select the file input element and canvas element
const fileInput = document.querySelector('input[type="file"]');
const canvas = document.querySelector('canvas');
const uploadButton = document.querySelector('#upload-button');

// Load the Cheems image
const cheemsImage = new Image();
cheemsImage.src = '/cheems.png';

// When the upload button is clicked, read the selected file and photoshop it
uploadButton.addEventListener('click', () => {
  const file = fileInput.files[0];
  const reader = new FileReader();
  reader.onload = () => {
    const originalImage = new Image();
    originalImage.src = reader.result;
    originalImage.onload = () => {
      photoshop(canvas, originalImage, cheemsImage);

      // Open the photoshopped image in a new window
      const windowFeatures = 'menubar=no,location=no,resizable=yes,scrollbars=yes,status=no';
      const windowName = 'Photoshopped Image';
      const windowUrl = canvas.toDataURL();
      window.open(windowUrl, windowName, windowFeatures);
    };
  };
  reader.readAsDataURL(file);
});
</script>