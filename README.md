# PlaceholderImage



Use this module in templates to generate placeholder images. It doesn't create a physical image but a base64 data uri string to use as the src of image tag. You can get the base64 code or the complete img tag for convenience.

Example chained call:

```
$base64 = $modules->PlaceholderImage->width(640)->height(480)->background('DDDDDD')->render();
```

Then insert the string as the src like:
```
<img src="<?php echo $base64?>">
```

Or pass true to render() to get a complete <img> tag

```
$imgTag = $modules->PlaceholderImage->width(640)->height(480)->render(true);
```

Or static calls for convenience:

```
$base64 = PlaceholderImage::image(150,100);
$base64 = PlaceholderImage::image(150, 100, 'FF0000', 'FFFFFF', 'Custom text');
$imgTag = PlaceholderImage::imagetag(150, 100, 'FF0000', 'FFFFFF', 'Custom text');
```

## Requirements:

- GD PHP lib installed in your server.