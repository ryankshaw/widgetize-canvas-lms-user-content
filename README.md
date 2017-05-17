# widgetize-canvas-lms-user-content
A drop-in replacement for the functionality in Canvas LMS that makes jqueryUI widgets out of your user content

**I don't actually recommend people continue to use this going forward. I am just providing
it so all of your legacy content that might have used the magic functionality in CanvasLMS 
that makes jqueryUI widgets out of your user content continues to work exactly as it did before,
even if/when canvas removes that functionality from core canvas.**

### This comes with no warranty and is not supported by Instructure

## Installation
To turn this on for users of your institution, you just need to add the following snippet 
to your Custom JavaScript file file that you upload to the Canvas LMS Theme editor. It will
grab the actual code in this repo that does all the work from a global cdn and run it on
every page in your account. See the `index.js` file in this directory for what it actually does.

```javascript
// Add this to your Custom JavaScript file in the CanvasLMS theme editor
!function(s,d,url,e,p){
  e=d.createElement(s),p=d.getElementsByTagName(s)[0];t.async=1;e.src=url;p.parentNode.insertBefore(e,p)
}('script', document, 'https://unpkg.com/widgetize-canvas-lms-user-content')
```


## example usage
This should handle any content that you add in the RCE editor in Canvas LMS that looks like this:

```html
<a href="#myDialog">Open dialog</a>
<div title="this is the dialog title" id="myDialog" class="enhanceable_content dialog">
  this is the stuff in the dialog
</div>

<div class="enhanceable_content draggable" style="background-color: red">
  <p>Drag me around</p>
</div>

<div class="enhanceable_content resizable" style="background-color: blue">
  <h3>Resizable</h3>
</div>

<ul class="enhanceable_content sortable">
  <li>Sortable Item 1</li>
  <li>Sortable Item 2</li>
  <li>Sortable Item 3</li>
  <li>Sortable Item 4</li>
</ul>

<div class="enhanceable_content tabs">
  <ul>
    <li><a href="#tabs-1">Tab 1</a></li>
    <li><a href="#tabs-2">Tab 2</a></li>
    <li><a href="#tabs-3">Tab 3</a></li>
  </ul>
  <div id="tabs-1">
    Content for tab 1
  </div>
  <div id="tabs-2">
    Content for tab 2
  </div>
  <div id="tabs-3">
    content for tab 3
  </div>
</div>

<div class="enhanceable_content accordion">
  <h3>Section 1</h3>
  <div>
    Content for Section 1
  </div>
  <h3>Section 2</h3>
  <div>
    Content for section 2
  </div>
  <h3>Section 3</h3>
  <div>
    Content for Section Three
  </div>
  <h3>Section 4</h3>
  <div>
    Content For section 4
  </div>
</div>
```

