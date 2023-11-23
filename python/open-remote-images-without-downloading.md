# Open remote images without downloading 

When working with Google Colab, it's nice to not have to mess with storage and pull images from remote servers for fast iteration.

This writes the image to a buffer, so that Pillow can open the image without ever writing to disk.

```py
import io
import requests
import PIL

r = requests.get('IMAGE_LINK')
img = PIL.Image.open(io.BytesIO(r.content))
``` 

[source](https://colab.research.google.com/drive/13wCM9OV2JR004zFvh7zPgUxrga8sU4d1)