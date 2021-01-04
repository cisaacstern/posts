I considered [potrace](http://potrace.sourceforge.net/), which has Python bindings.

Here's the [Stack Overflow post](https://stackoverflow.com/questions/25688573/matplotlib-set-clip-path-requires-patch-to-be-plotted) where a
workaround for clipping contoured plots is described.

Otherwise, the circle clipping is sourced from the [matplotlib docs](https://matplotlib.org/3.1.1/gallery/images_contours_and_fields/image_clip_path.html#sphx-glr-gallery-images-contours-and-fields-image-clip-path-py).

```python
import matplotlib.pyplot as plt
import matplotlib.patches as patches
from scipy.ndimage import gaussian_filter

image = plt.imread('city_thumbnail.png')


def headshot(image, sigma, levels, cmap):
    fig, ax = plt.subplots()

    Z = image[:,:,2]
    Z = gaussian_filter(Z, sigma=sigma)

    cont = ax.contourf(Z, levels=levels, origin='upper', cmap=cmap)
    
    x, y = image.shape[0]/2, image.shape[0]/2
    patch = patches.Circle((x, y), radius=y-10, transform=ax.transData)
    
    for col in cont.collections:
        col.set_clip_path(patch)
    
    ax.axis('off')
    plt.axis('equal')
    
    plt.savefig("test.svg")
    
    return plt.show()
```

Before the SVG is added to material-ui with [this approach](https://material-ui.com/components/icons/#svgicon), it is optimized with [svgo](https://github.com/svg/svgo), which can also be used with Jake Archibald's [web GUI](https://jakearchibald.github.io/svgomg/).

Admittedly, it wasn't totally clear to me how to translate the svg into a usable material-ui icon, in large part because the official documentation
does not account for a multicolor icon. This [medium post](https://medium.com/blueeast/changing-a-multicolor-svg-icon-of-type-svg-into-react-component-using-materialui-svgicon-component-d7958026ef9) helped fill in some of those gaps.
