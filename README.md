# Theia Sticky Sidebar

A JavaScript library that glues your website's sidebars (or any vertical column for that matter), making them permanently visible when scrolling up and down. Useful when a sidebar is too tall or too short compared to the rest of the content. Works with virtually any design and supports multiple sidebars.

## Examples

[3 columns example](http://theia-sticky-sidebar.wecodepixels.com/examples/3-columns.html)

[4 columns example](http://theia-sticky-sidebar.wecodepixels.com/examples/4-columns.html)

[Bootstrap 4 example](http://theia-sticky-sidebar.wecodepixels.com/examples/bootstrap-v4.html)

[Foundation example](http://theia-sticky-sidebar.wecodepixels.com/examples/foundation.html)


## Usage
Include "dist/theia-sticky-sidebar.min.js" in your HTML document.

Your website's HTML structure has to be similar to this in order to work:

```html
<div class="wrapper">
  <div class="content">
    <div class="theiaStickySidebar">
    ...
    </div>
  </div>
  <div class="sidebar">
    <div class="theiaStickySidebar">
    ...
    </div>
  </div>
</div>
```

Note that the inner "theiaStickySidebar" divs are optional, but highly recommended.
If you don't supply them yourself, the script will create them for you, but this can be problematic
if you're using ads or iframes, since they will be moved around in the DOM and as a result will get reloaded.

**Note:** Make sure to use `<!DOCTYPE html>` in your page, otherwise you might run into weird issues.

For the above example, you can use the following JavaScript:

```html
<script type="text/javascript" src="http://code.jquery.com/jquery.min.js"></script>
<script type="text/javascript" src="dist/ResizeSensor.min.js"></script>
<script type="text/javascript" src="dist/theia-sticky-sidebar.min.js"></script>
		
<script type="text/javascript">
  jQuery(document).ready(function() {
    jQuery('.content, .sidebar').theiaStickySidebar({
      // Settings
      additionalMarginTop: 30
    });
  });
</script>
```

### ResizeSensor

Theia Sticky Sidebar uses the [CSS Element Queries](https://github.com/marcj/css-element-queries) library to detect when your sidebars change height, so that it can recalculate their positions. This can happen if you are using an [accordion](http://v4-alpha.getbootstrap.com/components/collapse/#accordion-example), for example.

You can choose **not** to include the `ResizeSensor.min.js` script in your page, in which case Theia Sticky Sidebar will continue to function (possibly even a bit smoother) but will not automatically detect height changes.

## Settings

### containerSelector

The sidebar's container element. If not specified, it defaults to the sidebar's parent.

### additionalMarginTop

An additional top margin in pixels. Defaults to **0**.

### additionalMarginBottom

An additional bottom margin in pixels. Defaults to **0**.

### updateSidebarHeight

Updates the sidebar's height. Use this if the background isn't showing properly, for example. Defaults to **true**.

### minWidth

The sidebar returns to normal if its width is below this value. Useful for responsive designs. Defaults to **0**.

### disableOnResponsiveLayouts

Try to detect responsive layouts automatically and disable the sticky functionality on smaller screens. More exactly, it detects when the container and the sidebar are moved one on top of the other, instead of showing up side-by-side. Defaults to **true**.

### defaultPosition

The sidebar must have a non-static `position`, as the inner sticky-sidebar uses `position: absolute`. Defaults to **relative**.

### namespace

Events are binded using a namespace, so that you may unbind them later on without affecting others. Defaults to **TSS**.


## Credits

### Original Creator
- [Original Creator's Name](link-to-original-profile) - [Link to Original Repository](link-to-original-repository)

### Acknowledgements
- Special thanks to WeCodePixels team for creating the original repository and allowing me to fork it.
- I would like to express my gratitude to WeCodePixels for their contributions to the project.
- Thanks to the contributors of the original repository https://github.com/WeCodePixels/theia-sticky-sidebar for their valuable work and inspiration.

Stock photos courtesy of [Unsplash.com](https://unsplash.com/)
