# Rembglib

[![Downloads](https://pepy.tech/badge/rembg)](https://pepy.tech/project/rembg)
[![Downloads](https://pepy.tech/badge/rembg/month)](https://pepy.tech/project/rembg/month)
[![Downloads](https://pepy.tech/badge/rembg/week)](https://pepy.tech/project/rembg/week)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://img.shields.io/badge/License-MIT-blue.svg)
[![Hugging Face Spaces](https://img.shields.io/badge/🤗%20Hugging%20Face-Spaces-blue)](https://huggingface.co/spaces/KenjieDec/RemBG)

Rembglib is a tool to remove images background. That is it.

<p style="display: flex;align-items: center;justify-content: center;">
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/car-1.jpg" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/car-1.out.png" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/car-2.jpg" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/car-2.out.png" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/car-3.jpg" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/car-3.out.png" width="100" />
</p>

<p style="display: flex;align-items: center;justify-content: center;">
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/animal-1.jpg" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/animal-1.out.png" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/animal-2.jpg" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/animal-2.out.png" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/animal-3.jpg" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/animal-3.out.png" width="100" />
</p>

<p style="display: flex;align-items: center;justify-content: center;">
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/girl-1.jpg" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/girl-1.out.png" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/girl-2.jpg" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/girl-2.out.png" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/girl-3.jpg" width="100" />
  <img src="https://raw.githubusercontent.com/danielgatis/rembg/master/examples/girl-3.out.png" width="100" />
</p>

**If this project has helped you, please consider making a [donation](https://www.buymeacoffee.com/danielgatis).**


### Installation

#### **!! This library is for Python 3.9 only !!**

CPU support:
```bash
pip install rembglib
```

### Usage as a library

Input and output as bytes
```python
from rembglib import remove

input_path = 'input.png'
output_path = 'output.png'

with open(input_path, 'rb') as i:
    with open(output_path, 'wb') as o:
        input = i.read()
        output = remove(input)
        o.write(output)
```

Input and output as a PIL image
```python
from rembglib import remove
from PIL import Image

input_path = 'input.png'
output_path = 'output.png'

input = Image.open(input_path)
output = remove(input)
output.save(output_path)
```

Input and output as a numpy array
```python
from rembglib import remove
import cv2

input_path = 'input.png'
output_path = 'output.png'

input = cv2.imread(input_path)
output = remove(input)
cv2.imwrite(output_path, output)
```

### Models

All models are downloaded and saved in the user home folder in the `.u2net` directory.

The available models are:

- u2net ([download](https://drive.google.com/uc?id=1tCU5MM1LhRgGou5OpmpjBQbSrYIUoYab), [source](https://github.com/xuebinqin/U-2-Net)): A pre-trained model for general use cases.
- u2netp ([download](https://drive.google.com/uc?id=1tNuFmLv0TSNDjYIkjEdeH1IWKQdUA4HR), [source](https://github.com/xuebinqin/U-2-Net)): A lightweight version of u2net model.
- u2net_human_seg ([download](https://drive.google.com/uc?id=1ZfqwVxu-1XWC1xU1GHIP-FM_Knd_AX5j), [source](https://github.com/xuebinqin/U-2-Net)): A pre-trained model for human segmentation.
- u2net_cloth_seg ([download](https://drive.google.com/uc?id=15rKbQSXQzrKCQurUjZFg8HqzZad8bcyz), [source](https://github.com/levindabhi/cloth-segmentation)): A pre-trained model for Cloths Parsing from human portrait. Here clothes are parsed into 3 category: Upper body, Lower body and Full body.

#### How to train your own model

If You need more fine tunned models try this:
https://github.com/danielgatis/rembg/issues/193#issuecomment-1055534289

### In the cloud

Please contact me at danielgatis@gmail.com if you need help to put it on the cloud.

### References

- https://arxiv.org/pdf/2005.09007.pdf
- https://github.com/NathanUA/U-2-Net
- https://github.com/pymatting/pymatting

### Buy me a coffee
Liked some of my work? Buy me a coffee (or more likely a beer)

<a href="https://www.buymeacoffee.com/danielgatis" target="_blank"><img src="https://bmc-cdn.nyc3.digitaloceanspaces.com/BMC-button-images/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;"></a>

### License

Copyright (c) 2020-present [Daniel Gatis](https://github.com/danielgatis)

Licensed under [MIT License](./LICENSE.txt)
