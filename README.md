# swd

This is a repository based on https://github.com/koshian2/swd-pytorch for computing swd on images from different number of channels. 

Here is an example :

## Usage Example

For 5 channel images
```python

import torch
from swd import swd
torch.manual_seed(123) # fix seed
x1 = torch.rand(1024, 5, 128, 128)  # 1024 images, 5 chs, 128x128 resolution
x2 = torch.rand(1024, 5, 128, 128)
out = swd(x1, x2,channels=5, device="cuda") # Fast estimation if device="cuda"
print(out) # tensor(53.6950)

```
And in general for n channel images 

```python

import torch
from swd import swd
torch.manual_seed(123) # fix seed
channels=n
x1 = torch.rand(1024, n, 128, 128)  # 1024 images, 5 chs, 128x128 resolution
x2 = torch.rand(1024, n, 128, 128)
out = swd(x1, x2,channels=n, device="cuda") # Fast estimation if device="cuda"
print(out)

```
