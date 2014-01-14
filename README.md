# [Demo](http://codepen.io/ajkochanowicz/pen/FDlJi)

A clever and highly useful trick to creating a modal with just one html element. It's not a library; it's a snippet.

Quick Start
-----------

### 1. Create Modal

    <div class="se-modal"></div>
	
This is really all the markup you'll need. The rest is good old fashioned HTML.
That being said, I would suggest starting with a heading element (h1, h2, h3, h4, h5), use a small &times; character, and have a button. Here's an example:
	
    <div class="se-modal">
      <h2>
      	Title
      	<small class="close">&times;</small>
      </h2>
      <p>Hello world</p>
      <a href="#" class="btn btn-primary">Save</a>
    </div>
    
### 2. Add CSS

    <link rel="stylesheet" href="se-modal.css" />

### 3. Add JavaScript (jQuery required)

    $(':not(.se-modal)').not('.se-modal *').click(function() {
      return $('.se-modal[style="display: block;"]').fadeOut('fast');
    }).children().click(function(e) {
      return false;
    });
	
	
All this will do is allow the modal to be dismissed when clicked outside.

### 4. Bind

Rather than reinvent the wheel, Just make the modal appear and disappear with jQuery. Because it's one element, you don't need the heft of a framework to create an overlay or other fanciness.
	
**HTML**
	
    <a href="#" class="btn">Show Modal</a>

    <div class="se-modal">
      <h2>
      	Title
      	<small class="close">&times;</small>
      </h2>
      <p>Hello world</p>
      <a href="#" class="btn btn-primary">Save</a>
    </div>
	
**jQuery**
	
    <script src="jquery.js"></script>
    <script>

      // Show Modal
      $('.btn').click(function() {
        $('.se-modal').fadeIn('fast');
      })

      // Hide Modal
      $('.se-modal .close, .se-modal .btn').click(function() {
        $('.se-modal').fadeOut('fast');
      })

    </script>
