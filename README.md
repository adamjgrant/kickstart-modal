# [Demo](http://codepen.io/ajkochanowicz/pen/peuFE)

A clever and highly useful trick to creating a modal with just one html element.

Quick Start
-----------

### 1. Create Modal

    <div class="modal"></div>
	
This is really all the markup you'll need. The rest is good old fashioned HTML.
That being said, I would suggest starting with a heading element (h1, h2, h3, h4, h5), use a small &times; character, and have a button. Here's an example:
	
    <div class="modal">
      <h2>
      	Title
      	<small>&times;</small>
      </h2>
      <p>Hello world</p>
      <button>Save</button>
    </div>
    
### 2. Add CSS

    <link rel="stylesheet" href="sem-modal.css" />

### 3. Add JavaScript (jQuery required)

	$(':not(.modal)').not('.modal *').click(function() {
		return $('.modal[style="display: block;"]').fadeOut('fast');
	}).children().click(function(e) {
		return false;
	});
	
	
All this will do is allow the modal to be dismissed when clicked outside.

### 4. Bind

Rather than reinvent the wheel, Just make the modal appear and disappear with jQuery. Because it's one element, you don't need the heft of a framework to create an overlay or other fanciness.
	
**HTML**
	
    <button>Show Modal</button>

    <div class="modal">
      <h2>
      	Title
      	<small>&times;</small>
      </h2>
      <p>Hello world</p>
      <button>Save</button>
    </div>
	
**jQuery**
	
    <script src="jquery.js"></script>
    <script>

      // Show Modal
      $('button').click(function() {
        $('.modal').fadeIn('fast');
      })

      // Hide Modal
      $('.modal small, .modal button').click(function() {
        $('.modal').fadeOut('fast');
      })

    </script>
